---
title: Implementación con Artículos instantáneos de Facebook
description: Implementar Adobe Analytics en páginas de Artículos instantáneos de Facebook.
feature: Implementation Basics
exl-id: 2189f70d-32f0-4137-9d53-7acab0f15e6c
role: Developer
TQID: 'https://experienceleague.adobe.com/S2ljH7WOuX6qvYplo-6k-MXw6FKG-vhk78EiGQFiImg'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 468
ht-degree: 94%

---

# Implementación con Artículos instantáneos de Facebook

Artículos instantáneos de Facebook permiten a los editores crear artículos interactivos y rápidos en Facebook. Artículos Instantáneos puede cargar contenido hasta 10 veces más rápido que la Web móvil.

Puede incrustar Adobe Analytics en Artículos instantáneos de Facebook para realizar un seguimiento del comportamiento de los visitantes. Ya que el contenido del editor se encuentra dentro de la aplicación de Facebook y no en los sitios web del editor, el método de etiquetado es levemente distinto a una implementación estándar de Analytics.

## Flujo de trabajo

El flujo de trabajo general para implementar Adobe Analytics es el siguiente:

1. Cree una página `stats.html`. Codifique esta página para extraer parámetros de cadena de consulta de la dirección URL y asignar cada parámetro a una variable de Analytics
1. Aloje la página `stats.html` en el servidor web
1. Implemente Analytics en el artículo instantáneo de Facebook haciendo referencia al archivo `stats.html` en un iframe
1. Incluya parámetros de cadena de consulta en el atributo iframe `src`

### Paso 1: Crear una página `stats.html`

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
      var s_account = "examplersid1,examplersid2";
      var s_trackingServer = "example.data.adobedc.net";
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

### Paso 2: Alojar la página `stats.html` en el servidor web

Adobe recomienda alojar su página `stats.html` junto con la última versión de `AppMeasurement.js` y `VisitorAPI.js`. Trabaje con los equipos de ingeniería adecuados de su organización para alojar este archivo en la ubicación correcta.

### Paso 3: Hacer referencia a `stats.html` en cada página de Artículos instantáneos de Facebook

Al crear contenido de Artículos instantáneos de Facebook, puede incrustar el contenido HTML de análisis dentro de un iFrame. Por ejemplo:

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### Paso 4: Establecer variable y seguimiento de evento personalizados

Las variables y los eventos personalizados pueden seguirse desde la HTML de análisis a través de dos métodos diferentes:

* Incluya valores de variables y eventos directamente en la página `stats.html`. Las variables definidas aquí serían mejores para valores que normalmente son iguales para todos los Artículos instantáneos de Facebook.
* Incluya valores de variables como parte de una cadena de consulta que haga referencia al iframe. Este método le permite enviar valores de variables desde el Artículo instantáneo de Facebook al iframe que aloja el código de Analytics.

El siguiente ejemplo muestra varias variables personalizadas incluidas en una cadena de consulta. El JavaScript que se encuentra dentro de `stats.html` comprobaría la cadena de consulta mediante `s.Util.getQueryParam()`.

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

>[!NOTE]
>
>La dimensión Referente no se rastrea automáticamente debido a la naturaleza de los iFrames. Asegúrese de incluir esta dimensión como parte de la cadena de consulta si desea rastrearla.

## Artículos instantáneos y privacidad de Facebook

Siempre y cuando la página HTML de Analytics esté alojada en su servidor web, Adobe admite la política de privacidad existente en todos los Artículos instantáneos de Facebook. Si un usuario decide excluirse del seguimiento en su sitio principal, también se excluye del seguimiento en todos sus Artículos instantáneos de Facebook. La página de utilidades también admite el servicio de ID de visitante para que pueda integrar datos de Artículos instantáneos de Facebook con el resto de CX Enterprise.
