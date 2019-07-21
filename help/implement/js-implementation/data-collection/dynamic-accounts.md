---
description: El archivo .js se puede configurar para que seleccione automáticamente un ID de grupo de informes.
keywords: Implementación de Analytics
seo-description: El archivo .js se puede configurar para que seleccione automáticamente un ID de grupo de informes.
seo-title: 'ID de grupos de informes: cuentas dinámicas'
solution: Analytics
title: 'ID de grupos de informes: cuentas dinámicas'
topic: Desarrollador e implementación
uuid: 763 a 9741-309 d -4795-8819-6543866047 d 5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID de grupos de informes: cuentas dinámicas

El archivo .js se puede configurar para que seleccione automáticamente un ID de grupo de informes. El archivo .js envía automáticamente la solicitud de imagen al grupo de informes en función de la URL. Por ejemplo: si la dirección URL es `www.mysite.com`, la solicitud de imagen se envía automáticamente al grupo de informes A. Si la dirección URL es `www.mysite1.com`, la solicitud de imagen se envía automáticamente al grupo de informes B.

Estas cadenas se pueden encontrar en cualquiera de los siguientes elementos:

* Host/dominio (configuración predeterminada)
* Ruta
* Cadena de consulta
* Host/dominio y ruta
* Ruta y cadena de consulta
* Dirección URL completa

Para obtener más información sobre cómo configurar [!DNL Analytics] para que seleccione automáticamente una [!UICONTROL ID de grupo de informes], póngase en contacto con el Soporte en línea de Adobe.

## Definición del segmento URL de correspondencia {#section_8099162F75F641CFBE46FD814450EF36}

Si tomamos el siguiente ejemplo de dirección URL, las partes de la dirección URL se muestran a continuación, junto con la variable `s.dynamicAccountMatch` que se debe configurar. (El comportamiento predeterminado, si `s.dynamicAccountMatch` no está definida, es buscar solo en el nombre de host/dominio).
URL de ejemplo: `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321`

| Parte | Ejemplo (anterior) |
|---|---|
| Nombre de host/dominio | `www.client.com` |
| Ruta | `directory1/directory2/filename.html` |
| Cadena de consulta | `param1=1234&param2=4321` |
| Host/dominio y ruta | `www.client.com/directory1/directory2/filename.html` |
| Ruta y cadena de consulta | `directory1/directory2/filename.html?param1=1234&param2=4321` |
| URL | `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321` |
| Parte | `s.dynamicAccountmatch` |
| Nombre de host/dominio | Indefinido |
| Ruta | `window.location.pathname` |
| Cadena de consulta | `(window.location.search?window.location.search:"?")` |
| Host/dominio y ruta | `window.location.host+window.location.pathname` |
| Ruta y cadena de consulta | `window.location.pathname+(window.location.search?window.location.search:"?")` |
| URL | `window.location.href` |

Consideremos el siguiente ejemplo:

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite2=clientdirectory;reportsuite1=client.com"`
* `s.dynamicAccountMatch=window.location.host+window.location.pathname`

## Múltiples reglas {#section_163FED1C1FA74C48BCB78B0D67EF36AE}

Si se seleccionan múltiples reglas (vea el ejemplo anterior), las reglas se ejecutan de izquierda a derecha. Las reglas se detienen tan pronto como se produce una coincidencia, como se muestra a continuación (con el conjunto de reglas especificado).

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com"`

The code first checks to determine if `qa.client.com` exists within the Host/Domain Name. If so, the report suite `devreportsuite1` is selected, and the match stops. Separe las reglas con punto y coma.

## Grupo de informes predeterminado {#section_0360D724929348B0B211708B5BA15647}

The `s_account` variable can be set first, and acts as a default value in case any of the specified strings cannot be found. A continuación verá un ejemplo:

```javascript
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

In the case above, if the host/domain name did not contain either `qa.client.com` or `client.com`, the report suite *defaultreportsuiteid* would be used.
