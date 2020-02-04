---
title: Implementación con Artículos Instantáneos de Facebook
description: Implementar Adobe Analytics en páginas de Artículos Instantáneos de Facebook.
translation-type: tm+mt
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# Implementación con Artículos Instantáneos de Facebook

Artículos Instantáneos de Facebook permiten a los editores crear artículos interactivos y rápidos en Facebook. Artículos Instantáneos puede cargar contenido hasta 10 veces más rápido que la Web móvil.

Puede incrustar Adobe Analytics en Artículos Instantáneos de Facebook para realizar un seguimiento del comportamiento de los visitantes. Dado que el contenido del editor se encuentra dentro de la aplicación de Facebook y no en los sitios web del editor, el método de etiquetado es ligeramente diferente al de una implementación estándar de Analytics.

## Flujo de trabajo

El flujo de trabajo general para implementar Adobe Analytics es el siguiente:

1. Cree una `stats.html` página. Codifique esta página para extraer parámetros de cadena de consulta de la dirección URL y asignar cada parámetro a una variable de Analytics
1. Alojar la `stats.html` página en el servidor web
1. Implementar Analytics en el artículo instantáneo de Facebook haciendo referencia al `stats.html` archivo en un iframe
1. Incluir parámetros de cadena de consulta en el atributo iframe `src`

### Paso 1: Crear una `stats.html` página

El HTML de muestra se puede usar para capturar estadísticas de los artículos instantáneos. Este archivo generalmente estaría alojado en uno de los servidores web de la empresa. Cada vez que se carga un artículo instantáneo, carga el archivo en un iframe, lo que activa el envío de datos a Adobe.

```html
<html>
  <head>
    <title>Facebook Stats</title>
      <script language="javaScript" type="text/javascript" src="VisitorAPI.js"></script>
      <script language="javaScript" type="text/javascript" src="AppMeasurement.js"></script>
  </head>
  <body>
    <script>
      var v_orgId = "INSERT-ORG-ID-HERE";
      var s_account = "examplersid";
      var s_trackingServer = "example.sc.omtrdc.net";
      var visitor = Visitor.getInstance(v_orgId);
      visitor.trackingServer = s_trackingServer;

      var s = s_gi(s_account);
      s.account = s_account;
      s.trackingServer = s_trackingServer;
      s.visitor = visitor;

      s.pageName = s.Util.getQueryParam("pageName");
      s.pageURL = document.referrer; // The referrer to the utility page is the parent frame
      s.campaign = s.Util.getQueryParam("cmpId");
      s.eVar1 = "Facebook Instant Article";
      s.eVar2 = s.Util.getQueryParam("eVar2");

      s.t();
    </script>
  </body>
</html>
```

### Paso 2:Alojar la `stats.html` página en el servidor web

Adobe recomienda alojar su `stats.html` página junto con la última versión de `AppMeasurement.js` y `VisitorAPI.js`. Trabaje con los equipos de ingeniería adecuados de su organización para alojar este archivo en la ubicación correcta.

### Paso 3: Referencia `stats.html` en cada página de Artículos Instantáneos de Facebook

Al crear contenido de Artículos Instantáneos de Facebook, incruste el contenido HTML de análisis en un iframe. Por ejemplo:

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### Paso 4: Establecer variable personalizada y seguimiento de eventos

Las variables y los eventos personalizados se pueden rastrear dentro del HTML de análisis mediante dos enfoques diferentes:

* Incluya valores de variables y eventos directamente en la `stats.html` página. Las variables definidas aquí serían mejores para valores que normalmente son iguales para todos los Artículos Instantáneos de Facebook.
* Incluya valores de variables como parte de una cadena de consulta que haga referencia al iframe. Este método le permite enviar valores de variables desde el artículo Instantáneo de Facebook al iframe que aloja el código de Analytics.

El siguiente ejemplo muestra varias variables personalizadas incluidas en una cadena de consulta. El JavaScript que se encuentra dentro `stats.html` comprobaría la cadena de consulta mediante `s.Util.getQueryParam()`.

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

> [!NOTE] La dimensión Referente no se rastrea automáticamente debido a la naturaleza de los iframes. Asegúrese de incluir esta dimensión como parte de la cadena de consulta si desea rastrearla.

## Artículos Instantáneos y privacidad de Facebook

Siempre que la página HTML de Analytics esté alojada en su servidor web, Adobe admite la política de privacidad existente en todos los Artículos Instantáneos de Facebook. Si un usuario no realiza el seguimiento en su sitio principal, también excluye el seguimiento en todos sus Artículos Instantáneos de Facebook. La página de utilidades también admite el servicio de identidad de Adobe Experience Cloud para que pueda integrar datos de Artículos Instantáneos de Facebook con el resto de Experience Cloud.
