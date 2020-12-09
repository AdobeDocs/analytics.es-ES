---
title: Migrar a AppMeasurement para JavaScript
description: Determine lo que necesita para migrar la implementación fuera del código H.
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 100%

---


# Migrar a AppMeasurement para JavaScript

Si la implementación todavía utiliza el código H, Adobe le recomienda migrar a la versión más reciente de AppMeasurement. Se recomienda implementar Analytics mediante [Adobe Experience Platform Launch](../launch/overview.md), aunque se puede utilizar una implementación de JavaScript actualizada.

Los siguientes cambios importantes están presentes en AppMeasurement en comparación con el código H:

* De 3 a 7 veces más rápido que el código H.
* Sus 21 kb sin comprimir hacen que sea más rápido que el código H, que es de 33 kb sin comprimir.
* El código de la página y la biblioteca se puede implementar dentro de la etiqueta `<head>`.
* El código H de nivel de página existente es compatible con AppMeasurement.
* La biblioteca proporciona utilidades nativas para obtener parámetros de consulta, leer y escribir cookies y realizar un seguimiento de vínculos avanzado.
* La biblioteca no admite variables de configuración de cuentas dinámicas (incluidas `dynamicAccountSelection`, `dynamicAccountMatch` y `dynamicAccountList`).

Los siguientes pasos describen un flujo de trabajo de migración habitual.

1. **Descargue el nuevo archivo de AppMeasurement**: Para acceder al nuevo archivo, inicie sesión en Adobe Analytics y, a continuación, vaya a Administración > Administrador de códigos. El archivo comprimido descargado contiene un archivo `AppMeasurement.js` minimizado, junto con los módulos Media e Integrate.
1. **Copie las personalizaciones de `s_code.js` a`AppMeasurement.js`**: Mueva todo el código antes de la sección `DO NOT ALTER ANYTHING BELOW THIS LINE` en `s_code.js` al principio de `AppMeasurement.js`.
1. **Actualizar todos los complementos**: Compruebe que está utilizando la versión más reciente de cada complemento enumerado en el archivo `s_code.js`. Esto incluye los módulos Media e Integrate.
1. **Implementar el archivo AppMeasurement.js**: Cargue el archivo `AppMeasurement.js` en el servidor web.
1. **Actualizar referencias de secuencias de comandos para que dirijan a`AppMeasurement.js`**: Compruebe que todas las páginas hagan referencia a `AppMeasurement.js` en lugar de `s_code.js`.

## Ejemplo de código de Appmeasurement

Un archivo típico de `AppMeasurement.js`. Compruebe que las variables de configuración se establecen por encima de la función `doPlugins`.

```js
// Initialize AppMeasurement
var s = s_gi("examplersid");

/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/;
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE");

/************************** CONFIG SECTION **************************/;
/* You may add or alter any code config here. */
s.trackDownloadLinks = true;
s.trackExternalLinks = true;
s.trackInlineStats = true;
s.linkDownloadFileTypes = "exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx";
s.linkInternalFilters = "javascript:,example.com";

s.usePlugins = true;
function s_doPlugins(s) {

// Use implementation plug-ins that are defined below in this section

}
s.doPlugins = s_doPlugins;

/* WARNING: Changing any of the below variables will cause drastic
changes to how your visitor data is collected.  Changes should only be
made when instructed to do so by your account manager.*/
s.trackingServer="example.data.adobedc.net";

/************************** PLUGINS SECTION *************************/

// Copy and paste implementation plug-ins here. Plug-ins can then be used in the s_doPlugins(s) function above

/****************************** MODULES *****************************/

// Copy and paste implementation modules (Media, Integrate) here.

/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  */
```

## Ejemplo de código de página

Código típico que se carga en cada página.

```html
<script src="AppMeasurement.js"></script>
<script language="JavaScript" type="text/javascript">
s.pageName = "Example page name";
s.eVar1 = "Example eVar value";
s.events = "event1";
s.t();
</script>
```

Asegúrese de incluir también en cada página una referencia a `AppMeasurement.js` y `VisitorAPI.js`. Consulte [Implementación de JavaScript](/help/implement/js/overview.md) para obtener más información.
