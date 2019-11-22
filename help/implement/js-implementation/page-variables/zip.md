---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# zip

Las variables y son variables de conversión.


<!-- 

zip.xml

 -->

Son similares a las eVars en cuando a que capturan eventos pero, a diferencia de estas, no persisten. La variable *`zip`* y *`state`* son como las eVars, que caducan inmediatamente.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 50 bytes | zip | Conversión &gt; Perfil del visitante &gt; Códigos postales | "" |

Since the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. Por ejemplo: si está utilizando *`zip`* para comparar las tasas de conversión por código postal, debe rellenar la variable *`zip`* en cada página del proceso de cierre de compra. Adobe recomienda usar la dirección de facturación como fuente del código postal. Puede elegir usar la dirección de envío, siempre que solo haya una en el pedido. Un sitio multimedia puede elegir usar *`zip`* y *`state`* para el registro o seguimiento de pulsaciones.

**Sintaxis y valores posibles** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

La variable *`zip`* no impone ningún valor especial ni restricciones de formato. No existen limitaciones de *`zip`* además de las limitaciones estándar de las variables.

**Ejemplos** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**Parámetros de configuración** {#section_7987084EECC34DD38B643B94F82385CA}

Ninguna

**Problemas, preguntas y consejos** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* Rellene [!UICONTROL zip] en todas las páginas en las que se activó un evento relevante (todas las páginas del proceso de cierre de compra).
* Las variables *`zip`* y *`state`* actúan como eVars que caducan en la vista de las páginas.

