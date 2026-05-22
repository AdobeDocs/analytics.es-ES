---
title: Migrar a AppMeasurement para JavaScript
description: Determine lo que necesita para migrar la implementación fuera del código H.
feature: Implementation Basics
exl-id: ed606ab4-bd7d-4871-baa1-77e30fdd419e
role: Developer
TQID: 'https://experienceleague.adobe.com/Ml3fp170Ggn8-lpJCvDOAMBMF1izsmrG0BAnWcS-BUo'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 297
ht-degree: 90%

---

# Migrar a AppMeasurement para JavaScript

Si la implementación todavía utiliza el código H, Adobe le recomienda migrar a la versión más reciente de AppMeasurement. Se recomienda implementar Analytics mediante [etiquetas en Adobe Experience Platform](../launch/overview.md), aunque se puede utilizar una implementación de JavaScript actualizada.

Los siguientes cambios importantes están presentes en AppMeasurement en comparación con el código H:

* De 3 a 7 veces más rápido que el código H.
* Sus 21 kb sin comprimir hacen que sea más rápido que el código H, que es de 33 kb sin comprimir.
* El código de la página y la biblioteca se puede implementar dentro de la etiqueta `<head>`.
* El código H de nivel de página existente es compatible con AppMeasurement.
* La biblioteca proporciona utilidades nativas para obtener parámetros de consulta, leer y escribir cookies y realizar un seguimiento de vínculos avanzado.
* La biblioteca no admite variables de configuración de cuentas dinámicas (incluidas `dynamicAccountSelection`, `dynamicAccountMatch` y `dynamicAccountList`).

Los siguientes pasos describen un flujo de trabajo de migración habitual.

1. **Descargue el nuevo archivo de AppMeasurement**: Para acceder al nuevo archivo, inicie sesión en Adobe Analytics y, a continuación, vaya a Administración > Todos los administradores > Administrador de códigos. El archivo comprimido descargado contiene un archivo `AppMeasurement.js` minimizado, junto con los módulos Media e Integrate.
1. **Copie las personalizaciones de `s_code.js` a`AppMeasurement.js`**: Mueva todo el código antes de la sección `DO NOT ALTER ANYTHING BELOW THIS LINE` en `s_code.js` al principio de `AppMeasurement.js`.
1. **Actualizar todos los complementos**: Asegúrese de utilizar la versión más reciente de cada complemento enumerado en el archivo `s_code.js`. Este paso incluye los módulos Media e Integrate.
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
made when instructed to do so by your Adobe Account Team.*/
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
