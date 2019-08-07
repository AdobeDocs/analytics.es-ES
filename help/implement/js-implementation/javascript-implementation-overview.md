---
description: Para comenzar a utilizar Analytics, los datos deben enviarse a un grupo de informes para que se muestren en los informes.
keywords: Implementación de Analytics; javascript; implementación de javascript; appmeasurement; descargar appmeasurement; Servicio de identidad; visitorapi. js; almacenamiento en caché; appmeasurement compression
seo-description: Para comenzar a utilizar Analytics, los datos deben enviarse a un grupo de informes para que se muestren en los informes.
seo-title: Descripción general de la implementación de JavaScript
solution: Analytics
title: Descripción general de la implementación de JavaScript
topic: Desarrollador e implementación
uuid: bb 661 d 8 c-faf 9-4454-ac 3 c -0 c 1 a 4 c 0 a 9336
translation-type: tm+mt
source-git-commit: 883eb12c6c0f9b566dd485227d19cee16d9cfadc

---


# Descripción general de la implementación de JavaScript

Para comenzar a utilizar Analytics, los datos deben enviarse a un grupo de informes para que se muestren en los informes.

The easiest and recommended way to send data to [!DNL Analytics] is by using [Launch](/help/implement/implement-with-launch/create-analytics-property.md). Sin embargo, en algunos casos tal vez prefiera implementar Analytics utilizando el método JavaScript, más antiguo.

>[!NOTE]
>
>Esta sección describe el método heredado de implementación de Analytics. All Analytics customers have access to [Launch](/help/implement/implement-with-launch/create-analytics-property.md), which is the standard method to deploy Experience Cloud tags.

## Pasos de la implementación {#section_73961BAD5BB4430A95E073DE5C026277}

A la hora de implementar correctamente una página con código de recopilación de datos, debe disponer de acceso a los servidores de alojamiento para cargar contenido nuevo en el sitio web. También resulta útil contar con un sitio existente en el que implementar el código.

A continuación se muestran los pasos de una implementación básica de Analytics.

| Tarea | Descripción |
|--- |--- |
| 1. Descargue appmeasurement para JavaScript y el servicio de ID. | Inicie sesión en Analytics a través de Experience Cloud. El archivo de descarga está disponible en Analytics &gt; Administración &gt; Administrador de códigos. Este zip de descarga contiene varios archivos.  AppMeasurement.js y VisitorAPI.js son los archivos relevantes para la implementación de Analytics. |
| 2. Configure el servicio de identidad. (anteriormente servicio ID de visitante) | Consulte [Configuración del servicio de identidad para Analytics](https://docs.adobe.com/content/help/en/id-service/using/home.html) |
| Actualización `AppMeasurement.js`. | Copy the [example AppMeasurement.js code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_4351543F2D6049218E18B48769D471E2) and paste it at the beginning of your `AppMeasurement.js` file. Como mínimo, actualice las siguientes variables:<ul><li>s.account="INSERT-RSID-HERE"</li><li>s.trackingServer="INSERT-TRACKING-SERVER-HERE"</li><li>s.visitorNamespace = "INSERT-NAMESPACE-HERE"</li><li>s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE")</li></ul><br>Consulte [Rellenar correctamente la variable trackingserver y trackingserversecure](https://helpx.adobe.com/analytics/kb/determining-data-center.html) o póngase en contacto con Clientcare si no está seguro de ninguno de estos valores. Si no están correctamente configurados, su implementación no recopilará los datos.</br> |
| 3. Host `AppMeasurement.js` y `VisitorAPI.js`. | Estos archivos JavaScript principales deben alojarse en un servidor web al que se pueda acceder desde todas las páginas del sitio. En el siguiente paso necesitará la ruta a estos archivos. |
| 4. Reference `AppMeasurement.js` and `VisitorAPI.js`  on all site pages. | <ul><li>Include the Visitor ID Service by adding the following line of code in the `head` or `body` tag on each page. `VisitorAPI.js` antes `AppMeasurement.js`de:`script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"`</li><li>Include AppMeasurement for JavaScript by adding the following line of code in the `head` or `body` tag on each page: `script language="JavaScript" type="text/javascript"  src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"`</li></ul> |
| 5. Actualizar e implementar el código de página. | Copy the [Example Page Code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7) and paste it just after the opening `body` tag on each page you want to track. Como mínimo, actualice las siguientes variables:<ul><li>var s=s_gi("INSERT-RSID-HERE")</li><li>s. pagename = "INSERT-NAME-HERE" (por ejemplo, s. pagename = document. title)</li></ul> |
| 6. Use Experience Cloud Debugger para verificar que se están enviando los datos. | Install the [Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html#concept_B26FFE005EDD4E0FACB3117AE3E95AA2). A continuación, cargue una página en la que haya implementado el código de página y abra el depurador. El depurador mostrará los detalles sobre los datos de recopilación que se han enviado. |

## Almacenamiento en caché {#section_4E2D1D962DF046418134C43CFC49AD4A}

El archivo JavaScript se almacena en caché en el explorador del visitante cuando se carga por primera vez y, por lo general, solo se descarga una vez por sesión. El archivo no se descarga en cada página, aunque lo usen todas las páginas del sitio. El cálculo promedio indica que, en la mayoría de sitios web, se registran varias vistas de página por sesión por usuario. De este modo, si se transfieren a este archivo los elementos JavaScript que se usan varias veces, se pueden reducir los datos que se descargan de forma general.

## Compresión de AppMeasurement para JavaScript {#section_C10BBC84C81C414088F97363D29E021B}

Si le preocupa el tamaño de página del código H (AppMeasurement para JavaScript 1.0 ya viene comprimido), Adobe recomienda considerar la posibilidad de comprimir el archivo con GZIP. Todos los exploradores principales admiten GZIP, que ofrece un mejor rendimiento que la compresión de JavaScript para comprimir y descomprimir el archivo JavaScript [!DNL s_code.js] principal.

Los siguientes vínculos explican cómo usar la funcionalidad GZIP en el sitio para gestionar la compresión del código JavaScript de [!DNL s_code.js]:

[Módulo mod_deflate de Apache](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Habilitar la compresión gzip con Tomcat y Flex](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
