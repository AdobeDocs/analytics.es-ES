---
description: En las siguientes secciones se describen los errores más comunes de las cuentas dinámicas.
keywords: Implementación de Analytics
seo-description: En las siguientes secciones se describen los errores más comunes de las cuentas dinámicas.
seo-title: Errores comunes
solution: Analytics
subtopic: Resolución de problemas
title: Errores comunes
topic: Desarrollador e implementación
uuid: 04345355-60 cc -4678-81 c 3-390 c 86752 df 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Errores comunes

En las siguientes secciones se describen los errores más comunes de las cuentas dinámicas.

## Cuenta codificada de forma rígida {#section_FB6F89BF317F45D387C00986ACA690BC}

Si lo que se desea es enviar siempre los datos a un grupo de informes específico, establezca [!UICONTROL s_dynamicAccountSelection] en false (también se pueden quitar todas las variables al mismo tiempo:

```js
var s_account="defaultreportsuiteid" 
REMOVE: s.dynamicAccountSelection=true 
REMOVE: s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

En el caso anterior, defaultreportsuiteid siempre se usa después de que se hayan quitado las otras dos líneas.

## Colocación del código {#section_05375CB2EF5A414794BC8209C906AEEB}

Defining *`s_account`* after the lines of code does not override the dynamic account selection, as shown below.

```js
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
s_account="anotherreportsuiteid" 
```

En el ejemplo anterior, la cuenta "anotherreportsuiteid" invalida "defaultreportsuiteid", pero no las coincidencias que se producen en [!UICONTROL s.dynamicAccountList]. La función que evalúa [!UICONTROL s.dynamicAccountList] se ejecuta en realidad mucho más adelante en el archivo .JS.

## Etiquetado de grupos múltiples {#section_6C014FA9B87D4622B483BCDE4281D2A9}

El etiquetado de grupos múltiples se puede usar junto con la selección de cuentas dinámicas, tal y como se muestra a continuación.

```js
s.dynamicAccountSelection=true 
s.dynamicAccountList="suiteid1,suiteid2=client.com" 
```

## Coincidencia de cuentas dinámicas {#section_647AB47B38D640D6BCC853FDA4E4342D}

No escriba las variables de [!UICONTROL coincidencia de cuentas dinámicas] entre comillas. A continuación se muestran las opciones.

| Nombre de host/dominio | Ninguno. |
|---|---|
| Cadena de consulta | s.dynamicAccountMatch=(window.location.search?window.location.search:"?") |
| Host/dominio y ruta | s.dynamicAccountMatch=window.location.host+window.lcation.pathname |
| Ruta y cadena de consulta | s.dynamicAccountMatch=window.location.pathname+(window.location.search?window.location.search""?") |
| Dirección URL completa | s.dynamicAccountMatch=window.location.href |

