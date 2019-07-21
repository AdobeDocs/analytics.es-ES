---
description: Cómo implementar Analytics en Artículos Instantáneos de Facebook.
keywords: Implementación de Analytics; embed; custom variable; custom event; seguimiento de visitantes; tracking; limitaciones
seo-description: Cómo implementar Analytics en Artículos Instantáneos de Facebook.
seo-title: Artículos Instantáneos de Facebook
solution: Analytics
title: Artículos Instantáneos de Facebook
topic: Desarrollador e implementación
uuid: 04 b 6366 b -7 c 52-4 dae-b 2 dd-bb 6 b 78 fd 409 c
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Artículos Instantáneos de Facebook

Cómo implementar Analytics en Artículos Instantáneos de Facebook.

Artículos Instantáneos de Facebook es un nuevo método que los editores pueden usar para generar artículos en Facebook de forma rápida e interactiva. Artículos Instantáneos puede cargar contenido hasta 10 veces más rápido que la Web móvil.

Adobe Analytics puede incrustarse dentro de Artículos Instantáneos de Facebook para realizar un seguimiento del comportamiento del visitante mientras interactúa con el contenido. Como el contenido del editor se encuentra dentro de la aplicación de Facebook y no en los sitios web del editor, el método de etiquetado es levemente distinto a una implementación estándar de Analytics.

## Paso 1. Incruste una página HTML de Analytics {#section_0DF847F8BA624CF8A239C10003A39E59}

Al crear contenido de Artículos Instantáneos de Facebook, puede incrustar el contenido HTML de análisis dentro de un iFrame. Por ejemplo:

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html" height="0"></iframe>
```

## Paso 2: Modifique el HTML de Analytics {#section_76707B51D63A47FF833C2D3FFF8412B4}

El HTML de muestra se puede usar para capturar estadísticas de los artículos instantáneos. Este archivo generalmente estaría alojado en uno de los servidores web de la empresa. Cada vez que se carga un Artículo Instantáneo, carga el archivo en un iframe como se describe en el paso uno, que activa el envío de los datos de análisis a Adobe.

```
<html> 
    <head> 
        <title>Facebook Stats</title> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/VisitorAPI.js"></script> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/AppMeasurement.js"></script> 
    </head> 
    <body> 
        <script> 
            //Standard Variable Configuration 
   var v_orgId = "[your-marketing-cloud-org-id]@AdobeOrg"; 
   var s_account = "[your-report-suite-id]"; 
   var s_trackingServer = "[your-tracking-server]"; 
   var s_visitorNamespace = "[your-namespace]"; 
     
   //Instantiation 
   var visitor = Visitor.getInstance(v_orgId); 
   visitor.trackingServer = s_trackingServer; 
     
   var s = s_gi(s_account); 
   s.account = s_account; 
   s.trackingServer = s_trackingServer; 
   s.visitorNamespace = s_visitorNamespace; 
   s.visitor = visitor; 
     
   //Custom Variables 
   s.pageName = s.Util.getQueryParam("pageName"); 
   s.prop10 = "Facebook Instant Article"; 
       
   //Page View Image Request Call 
   s.t(); 
        </script> 
    </body> 
</html> 
```

**Para modificar este HTML de muestra para la implementación específica**

1. Se recomienda alojar las copias más recientes de versiones sin modificar del VisitorAPI.js y AppMeasurement.js en un directorio común en los servidores web de la empresa.

   Estos archivos también se pueden descargar desde el Administrador de códigos en la interfaz de usuario de Analytics, si es necesario.

1. Incluya las variables de configuración estándar de implementación de Analytics:

   1. Su ID de organización de Experience Cloud.
   1. El ID del grupo de informes donde se capturará el tráfico de Artículos Instantáneos de Facebook.
   1. El dominio del servidor de seguimiento de la empresa.
   1. La variable namespace del visitante. **Nota:** Muchos de estos valores pueden encontrarse dentro de su implementación estándar de Analytics. El Servicio de atención al cliente o la Consultoría de Adobe pueden ayudarlo a proporcionar los valores adecuados si es necesario.

1. [Establezca variable y seguimiento de evento personalizados](../../implement/js-implementation/analytics-facebook-instant-articles.md#section_932C41BD21154C25B99389299BDF3E0B).
1. Incluya la sintaxis de solicitud de imagen para la vista de página `( s.t())`.

## Paso 3. Establezca variable y seguimiento de evento personalizados {#section_932C41BD21154C25B99389299BDF3E0B}

Las variables y los eventos personalizados pueden seguirse desde la HTML de análisis por medio de dos métodos diferentes. El primer método es incluir la lógica de JavaScript en la configuración personalizada, similar a lo que haría con una implementación estándar de Analytics. Por ejemplo, para establecer el valor de una prop, simplemente use la misma sintaxis que usaría en una implementación normal:

```
s.prop10 = "Facebook Instant Article";
```

También se pueden enviar variables de forma dinámica al iframe mediante parámetros de cadena de consulta en el atributo `src` del iframe. Por ejemplo:

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html?prop1=dynamic%20article%20title&eVar1=facebook%20page%20name&pageName=your%20page%20name%20here&cmpId=your%20campaignID%20here" height="0"></iframe>
```

Estos parámetros de cadena de consulta pueden establecerse luego en la sección de variables personalizadas del JavaScript HTML de análisis mediante la función `Util.getQueryParam`[!DNL AppMeasurement] dentro de la biblioteca predeterminada de la siguiente manera:

```
s.pageName = s.Util.getQueryParam("pageName"); 
s.campaign = s.Util.getQueryParam("cmpId"); 
s.eVar1 = s.Util.getQueryParam("eVar1"); 
s.prop1 = s.Util.getQueryParam("prop1"); 
```

## Seguimiento de visitantes {#section_60F0C77659534949831E85B5FD9AE81E}

Siempre y cuando la página HTML de Analytics esté alojada en su servidor web, Adobe puede admitir la política de privacidad existente en todos los Artículos Instantáneos de Facebook. Esto significa que si un usuario final no ha optado por el seguimiento en el sitio primario, tampoco habrá optado por el seguimiento en todos los Artículos Instantáneos de Facebook, sin que se requieran pasos adicionales. Utilizar esta página de utilidad también implica que el servicio de identidad (ID de visitante) es compatible para poder integrar las métricas y variables capturadas en Artículos Instantáneos de Facebook con el resto de Experience Cloud. (An example is for targeted advertising using [!DNL Adobe Audience Manager]).

## Limitaciones de seguimiento {#section_1EE1BB069A3148DB9446371AFE196567}

Existen algunos problemas que deberían mencionarse con este método. No se podrán recuperar en el iframe para seguimiento los valores DOM que generalmente están accesibles solamente mediante JavaScript en el Artículo Instantáneo de Facebook (como el referente). Sin embargo, los informes de tecnología estándar, como explorador, dispositivo, tamaño o resolución de pantalla, deberían funcionar normalmente. Es más, la pageURL puede obtenerse haciendo referencia a [!DNL document.referrer] desde la página de la utilidad.

## What's Next? {#section_A170A10E2A3642A784DF720195DA8B38}

En [!DNL Adobe Analytics] hay satisfacción por asociarse con Facebook, y nuestros editores están igualmente satisfechos de proporcionar funciones de análisis que son líderes en la industria a editores en la Web móvil para una experiencia de usuario increíblemente veloz. Estamos comprometidos con construir la mejor solución a largo plazo para responder las cambiantes necesidades de análisis que tienen nuestros clientes.

El proyecto Artículos Instantáneos de Facebook se mueve rápidamente y surgen cambios todo el tiempo. Por lo tanto, vuelva a consultar con regularidad si hay nuevas actualizaciones. Se esperan cambios a medida que continuamos mejorando nuestras integraciones y a medida que más editores adoptan Artículos Instantáneos de Facebook en el futuro.

Si tiene preguntas o problemas, comuníquese con el consultor o el servicio de atención al cliente de Adobe.
