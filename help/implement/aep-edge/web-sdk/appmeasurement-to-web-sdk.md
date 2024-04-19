---
title: Migración del AppMeasurement al SDK web
description: Actualice la implementación de Adobe Analytics de la biblioteca JavaScript de AppMeasurement a la biblioteca JavaScript del SDK web.
exl-id: c90246e8-0f04-4655-9204-33c0ef611b13
source-git-commit: 7bd4a188e5a2171260f1f0696d8bebad854dba4a
workflow-type: tm+mt
source-wordcount: '1334'
ht-degree: 0%

---

# Migración del AppMeasurement al SDK web

Esta ruta de implementación implica un enfoque de migración metódico para pasar de una implementación de AppMeasurement a una implementación de biblioteca JavaScript del SDK web. Otras rutas de implementación se tratan en páginas independientes:

* [Extensión de Analytics a SDK web](analytics-extension-to-web-sdk.md): Adopte un enfoque suave y metódico para pasar de la extensión de etiquetas de Adobe Analytics a la extensión de etiquetas del SDK web. Este método suprime la necesidad de utilizar XDM hasta que su organización esté lista para utilizar los servicios de Adobe Experience Platform, como Customer Journey Analytics. Utilice el `data` en lugar del objeto `xdm` objeto para enviar datos al Adobe.
* [Biblioteca JavaScript del SDK web](web-sdk-javascript-library.md): una instalación nueva del SDK web mediante la biblioteca JavaScript del SDK web (`alloy.js`). Administre la implementación usted mismo en lugar de utilizar la interfaz de usuario de etiquetas. Requiere el grupo de campos Adobe Analytics ExperienceEvent, que incluye variables típicas de Analytics que se deben incluir en el esquema XDM.
* [Extensión de etiqueta de SDK web](web-sdk-tag-extension.md): una instalación nueva del SDK web en la que se administra la implementación mediante etiquetas en la recopilación de datos de Adobe Experience Platform. Requiere el grupo de campos Adobe Analytics ExperienceEvent, que incluye variables típicas de Analytics que se deben incluir en el esquema XDM.

## Ventajas y desventajas de esta ruta de implementación

El uso de este enfoque de migración tiene ventajas y desventajas. Valore cuidadosamente cada opción para decidir qué enfoque es el mejor para su organización.

| Ventajas | Desventajas |
| --- | --- |
| <ul><li>**Utiliza la implementación existente**: Aunque este enfoque requiere algunos cambios de implementación, no requiere una implementación completamente nueva desde cero. Puede utilizar la capa de datos y el código existentes con cambios mínimos en la lógica de implementación.</li><li>**No requiere un esquema**: para esta fase de migración al SDK web, no necesita un esquema XDM. En su lugar, puede rellenar la variable `data` que envía datos directamente a Adobe Analytics. Una vez completada la migración al SDK web, puede crear un esquema para su organización y utilizar la asignación de flujos de datos para rellenar los campos XDM aplicables. Si se requiere un esquema en esta fase del proceso de migración, su organización se vería obligada a utilizar un esquema XDM de Adobe Analytics. El uso de este esquema dificulta que su organización utilice su propio esquema en el futuro.</li></ul> | <ul><li>**Los cambios de implementación requieren la intervención del desarrollador**: Si desea realizar cambios en la implementación del SDK web, debe trabajar con el equipo de desarrollo para editar el código en el sitio. El enfoque que [migra a la extensión de etiqueta del SDK web](analytics-extension-to-web-sdk.md) evita esta desventaja.</li><li>**Deuda técnica de ejecución**: Dado que este método utiliza una forma modificada de la implementación existente, puede resultar más difícil rastrear la lógica de implementación y realizar cambios en el futuro cuando sea necesario.</li><li>**Requiere asignación para enviar datos a Platform**: Cuando su organización esté lista para utilizar Customer Journey Analytics, debe enviar datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que todos los campos del `data` El objeto debe ser una entrada en la herramienta de asignación de flujos de datos que lo asigne a un campo de esquema XDM. La asignación solo debe realizarse una vez para este flujo de trabajo y no implica realizar cambios de implementación. Sin embargo, es un paso adicional que no es necesario al enviar datos en un objeto XDM.</li></ul> |

El Adobe recomienda seguir esta ruta de implementación en los siguientes casos:

* Tiene una implementación existente de mediante la biblioteca JavaScript del AppMeasurement de Adobe Analytics. Si tiene una implementación con la extensión de etiquetas de Adobe Analytics, siga [Migración de la extensión de etiqueta de Adobe Analytics a la extensión de etiqueta del SDK web](analytics-extension-to-web-sdk.md) en su lugar.
* Tiene intención de utilizar Customer Journey Analytics en el futuro, pero no desea reemplazar la implementación de Analytics con una implementación de SDK web desde cero. Reemplazar la implementación desde cero en el SDK web requiere el mayor esfuerzo, pero también ofrece la arquitectura de implementación a largo plazo más viable. Si su organización desea realizar el esfuerzo de una implementación limpia del SDK web, consulte [Ingesta de datos mediante el SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) en la guía del usuario del Customer Journey Analytics.

## Pasos necesarios para migrar al SDK web

Las siguientes medidas contienen objetivos concretos para alcanzar. Haga clic en cada paso para obtener instrucciones detalladas sobre cómo hacerlo.

+++**1. Creación y configuración de una secuencia de datos**

Cree una secuencia de datos en la recopilación de datos de Adobe Experience Platform. Cuando envía datos a este conjunto de datos, estos se reenvían a Adobe Analytics. En el futuro, este mismo conjunto de datos reenviará datos a Customer Journey Analytics.

1. Vaya a [experience.adobe.com](https://experience.adobe.com) e inicie sesión con sus credenciales.
1. Utilice la página de inicio o el selector de productos en la parte superior derecha para desplazarse a **[!UICONTROL Recopilación de datos]**.
1. En el panel de navegación izquierdo, seleccione **[!UICONTROL Datastreams]**.
1. Seleccione **[!UICONTROL Nueva secuencia de datos]**.
1. Introduzca el nombre que desee y seleccione **[!UICONTROL Guardar]**.
1. Una vez creada la secuencia de datos, seleccione **[!UICONTROL Añadir servicio]**.
1. En el menú desplegable del servicio, seleccione **[!UICONTROL Adobe Analytics]**.
1. Introduzca el mismo ID de grupo de informes que el sitio al que envía actualmente los datos de análisis. Haga clic en **[!UICONTROL Guardar]**.

![Añadir servicio de Adobe Analytics](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

El conjunto de datos ya está listo para recibir y pasar datos a Adobe Analytics. Tenga en cuenta el ID de la secuencia de datos, ya que este ID es necesario al configurar el SDK web en código.

+++

+++**2. Instalación de la biblioteca JavaScript del SDK web**

Consulte la última versión de `alloy.js` por lo tanto, se pueden utilizar sus llamadas al método. Consulte [Instalación del SDK web mediante la biblioteca JavaScript de](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) para obtener detalles y bloques de código que utilizar.

+++

+++**3. Configuración del SDK web**

Configure la implementación para que apunte al conjunto de datos creado en el paso anterior mediante el SDK web [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) comando. El `configure` El comando debe configurarse en cada página para que pueda incluirse junto con el código de instalación de la biblioteca.

Utilice el [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) y [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) propiedades dentro del SDK web `configure` comando:

* Configure las variables `edgeConfigId` al ID de la secuencia de datos recuperado del paso anterior.
* Configure las variables `orgId` a la organización de IMS de su organización.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Si lo desea, puede definir otras propiedades en la variable [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) en función de los requisitos de implementación de su organización.

+++

+++**4. Actualizar la lógica de código para utilizar una carga útil JSON**

Cambie la implementación de Analytics para que no dependa de lo siguiente `AppMeasurement.js` o el `s` objeto. En su lugar, establezca variables en un objeto JavaScript con formato correcto, que se convierte en un objeto JSON cuando se envía al Adobe. Tener un [Capa de datos](../../prepare/data-layer.md) en su sitio ayuda enormemente a la hora de configurar valores, ya que puede seguir haciendo referencia a esos mismos valores.

Para enviar datos a Adobe Analytics, la carga útil del SDK web debe utilizar `data.__adobe.analytics` con todas las variables de analytics establecidas dentro de este objeto. Las variables de este objeto comparten nombres y formatos idénticos a los de sus equivalentes de variables de AppMeasurement. Por ejemplo, si establece la variable `products` , no lo divida en objetos individuales como lo haría con XDM. En su lugar, inclúyala como una cadena exactamente como es si establece el valor `s.products` variable:

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

En última instancia, esta carga útil contiene todos los valores deseados y todas las referencias a `s` en la implementación se han eliminado. Puede utilizar cualquiera de los recursos que proporciona JavaScript para establecer este objeto de carga útil, incluida la notación de puntos para establecer valores individuales.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {analytics: {}}}};
dataObj.data.__adobe.analytics.pageName = window.document.title;
dataObj.data.__adobe.analytics.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{analytics:{...a}}}};
```

+++

+++**5. Actualizar las llamadas de método para utilizar el SDK web**

Actualice todas las instancias en las que llame a [`s.t()`](../../vars/functions/t-method.md) y [`s.tl()`](../../vars/functions/tl-method.md), sustituyéndolos por el [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) comando. Hay tres escenarios a considerar:

* **Seguimiento de vista de página**: Reemplace la llamada de seguimiento de vista de página con el SDK web `sendEvent` comando:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Seguimiento automático de vínculos**: La [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) La propiedad de configuración de está habilitada de forma predeterminada. Establece automáticamente las variables de seguimiento de vínculos correctas para enviar datos a Adobe Analytics. Si desea deshabilitar el seguimiento automático de vínculos, establezca esta propiedad como `false` dentro de [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) comando.

* **Seguimiento manual de vínculos**: el SDK web no tiene comandos independientes entre las llamadas a la vista de página y a las que no son de vista de página. Proporcione esa distinción dentro del objeto de carga útil.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.analytics.linkName = "Example custom link";
  dataObj.data.__adobe.analytics.linkType = "o";
  dataObj.data.__adobe.analytics.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. Validación y publicación de cambios**

Una vez que haya eliminado todas las referencias a AppMeasurement y a `s` , publique los cambios en el entorno de desarrollo para validar que la nueva implementación funciona. Una vez que haya validado que todo funciona correctamente, puede publicar las actualizaciones en producción.

Si se migra correctamente, `AppMeasurement.js` ya no es necesaria en el sitio y se pueden eliminar todas las referencias a esta secuencia de comandos.

+++

En este punto, la implementación de Analytics está completamente basada en el SDK web y está preparada para pasar a Customer Journey Analytics en el futuro.
