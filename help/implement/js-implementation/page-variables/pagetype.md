---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# pageType

La variable solo se usa para designar una página de error 404 Página no encontrada.


<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 20 bytes </td> 
   <td> pageType </td> 
   <td> Rutas &gt; Páginas &gt; Páginas <p>No encontrado </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

The *`pageType`* variable captures the errant URL when a 404 Error page is displayed, which allows you to quickly find broken links and paths that are no longer valid on the custom site. Configure la variable *`pageType`* en la página de error exactamente como se muestra a continuación.

No utilice la variable del nombre de página en las páginas de error 404. La variable *`pageType`* se utiliza solamente para la página de error 404.

En la mayoría de los casos, la página de error 404 es una página estática codificada. En estos casos, es importante que la referencia al archivo .JS se configure en un directorio/ruta global o relativo apropiado.

**Sintaxis y valores posibles** {#section_C1C59968226446559B05F6EE7374D525}

El único valor permitido de *`pageType`* es “errorPage”, como se muestra a continuación.

```js
s.pageType="errorPage"
```

**Ejemplos** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**Parámetros de configuración** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

Ninguna

**Problemas, preguntas y consejos** {#section_943681AB01FE47BEAC72E93CB60C53C8}

Para capturar otros errores del lado del servidor (como los errores ), use una prop para captar el mensaje de error y ponga `500 Error: <URL>` donde `<URL>` es la dirección URL solicitada, en la variable *`pageName`*. Este procedimiento permite usar informes de [!UICONTROL control de rutas] para ver qué rutas provocaron que los usuarios generaran errores 500. La prop explica qué mensaje de error proporciona el servidor.

