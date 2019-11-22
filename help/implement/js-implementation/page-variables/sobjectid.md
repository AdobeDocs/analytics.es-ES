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


# s_objectID

La variable es una variable global que debe configurarse en el evento [!UICONTROL onClick] de un vínculo.


<!-- 

s_objectID.xml

 -->

Si crea un ID de objeto único para un vínculo o una ubicación de vínculo en una página, se puede mejorar el seguimiento de actividades de visitante, o bien utilizar [!UICONTROL Activity Map] para informar sobre un tipo o una ubicación de vínculo en lugar de la URL del vínculo.

> [!NOTE] Se requiere un punto y coma (;) final al usar s_objectID con [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | OID | [!UICONTROL Activity Map], [!UICONTROL ClickMap] | La dirección URL absoluta de un vínculo donde se hizo clic |

Existen tres razones comunes para utilizar *`s_objectID`*:

* Para agregar actividad de visitante que cambia a menudo durante un día.
* Para separar la actividad de vínculo que el [!UICONTROL Activity Map] combina.
* Para mejorar la precisión de los informes de datos del [!UICONTROL Activity Map].

**Agregar clics en vínculos muy dinámicos** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

Si el sitio es muy dinámico y los vínculos de algunas páginas cambian a lo largo del día, *`s_objectID`* puede utilizarse para identificar la ubicación de un vínculo en la página. Si *`s_objectID`* se configura como “top left 1” o “top left 2”, que representa el primer vínculo en la parte superior izquierda de la página, por ejemplo, todos los vínculos que aparezcan en esa ubicación (o que tengan *`s_objectID`* configurado con el mismo valor) se incluyen en el mismo informe con el mapa de clics de visitantes. Si no usa *`s_objectID`*, verá el número de veces que se hizo clic en un vínculo determinado pero perderá perspectiva sobre cómo los visitantes del sitio utilizaron todos los demás vínculos de esa ubicación.

**Separar clics combinados** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

Si la variable *`pageName`* del sitio se utiliza para mostrar la sección o plantilla que está viendo un visitante, en lugar de la página específica que el visitante está viendo, puede que desee utilizar *`s_objectID`* para separar los vínculos que aparecen en varias versiones de esa plantilla de página. Por ejemplo, si tiene una página de plantilla para todos los productos del sitio, es muy probable que en todas las páginas haya un vínculo a la página de inicio y a un cuadro de búsqueda desde esa plantilla. Si desea ver cómo se utilizan esos vínculos por producto individual (en vez de por plantilla), puede rellenar *`s_objectID`* con un valor específico de un producto, por ejemplo, "prod 123789 home page" o "prod 123789 search". Una vez finalizado, el [!UICONTROL Activity Map] informará sobre esos vínculos por producto individual.

**Mejorar la precisión de[!UICONTROL Activity Map]**{#section_08B3406821294DCCABEEB99C90CF5C52}

En algunas ocasiones, los exploradores que no sean Internet Explorer, Firefox, Netscape, Opera y Safari no se incluyen en los informes. Aunque esto suponga un porcentaje reducido, cuenta para algunos clics y otras métricas. Use *`s_objectID`* en vínculos para identificar las direcciones de los problemas de informes del navegador. A continuación se incluye un ejemplo sobre cómo actualizar los vínculos para utilizar *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**Sintaxis y valores posibles** {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID puede contener cualquier identificador de texto.

```js
s_objectID="unique_id" 
```

No existen limitaciones de *`s_objectID`* además de las limitaciones estándar de las variables.

**Ejemplos** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**Parámetros de configuración** {#section_95396657D55B41ECB66B83D0534EA827}

Ninguna
