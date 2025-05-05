---
title: Migración del AppMeasurement al SDK web
description: Actualice la implementación de Adobe Analytics de la biblioteca JavaScript de AppMeasurement a la biblioteca JavaScript del SDK web.
exl-id: c90246e8-0f04-4655-9204-33c0ef611b13
source-git-commit: 05690cc8c1ea0364cbab86f35666df1cc1b13e69
workflow-type: tm+mt
source-wordcount: '1334'
ht-degree: 7%

---

# Migración del AppMeasurement al SDK web

Esta ruta de implementación implica un enfoque de migración metódico para pasar de una implementación de AppMeasurement a una implementación de biblioteca JavaScript de SDK web. Otras rutas de implementación se tratan en páginas independientes:

* [Extensión de Analytics a la extensión de SDK web](analytics-extension-to-web-sdk.md): adopte un enfoque suave y metódico para pasar de la extensión de etiquetas de Adobe Analytics a la extensión de etiquetas de SDK web. Este método suprime la necesidad de utilizar XDM hasta que su organización esté lista para utilizar los servicios de Adobe Experience Platform, como Customer Journey Analytics. Utilice el objeto `data` en lugar del objeto `xdm` para enviar datos al Adobe.
* [Biblioteca JavaScript de SDK web](web-sdk-javascript-library.md): Una instalación nueva del SDK web mediante la biblioteca JavaScript de SDK web (`alloy.js`). Administre la implementación usted mismo en lugar de utilizar la interfaz de usuario de etiquetas. Requiere el grupo de campos Adobe Analytics ExperienceEvent, que incluye variables típicas de Analytics que se deben incluir en el esquema XDM.
* [Extensión de etiquetas de SDK web](web-sdk-tag-extension.md): Una instalación nueva del SDK web en la que administra la implementación mediante etiquetas en la recopilación de datos de Adobe Experience Platform. Requiere el grupo de campos Adobe Analytics ExperienceEvent, que incluye variables típicas de Analytics que se deben incluir en el esquema XDM.

## Ventajas y desventajas de esta ruta de implementación

El uso de este enfoque de migración tiene ventajas y desventajas. Valore cuidadosamente cada opción para decidir qué enfoque es el mejor para su organización.

| Ventajas | Desventajas |
| --- | --- |
| <ul><li>**Utiliza la implementación existente**: aunque este enfoque requiere algunos cambios de implementación, no requiere una implementación completamente nueva desde cero. Puede utilizar la capa de datos y el código existentes con cambios mínimos en la lógica de implementación.</li><li>**No requiere un esquema**: Para esta fase de migración al SDK web, no necesita un esquema XDM. En su lugar, puede rellenar el objeto `data`, que envía datos directamente a Adobe Analytics. Una vez completada la migración al SDK web, puede crear un esquema para su organización y utilizar la asignación de flujos de datos para rellenar los campos XDM aplicables. Si se requiere un esquema en esta fase del proceso de migración, su organización se vería obligada a utilizar un esquema XDM de Adobe Analytics. El uso de este esquema dificulta que su organización utilice su propio esquema en el futuro.</li></ul> | <ul><li>**Los cambios de implementación requieren la intervención del desarrollador**: Si desea realizar cambios en la implementación del SDK web, debe trabajar con el equipo de desarrollo para editar el código del sitio. El método que [migra a la extensión de etiquetas del SDK web](analytics-extension-to-web-sdk.md) evita esta desventaja.</li><li>**Deuda técnica de la implementación**: dado que este método usa una forma modificada de la implementación existente, puede ser más difícil rastrear la lógica de la implementación y realizar cambios en el futuro cuando sea necesario.</li><li>**Requiere asignación para enviar datos a Platform**: cuando su organización esté lista para utilizar Customer Journey Analytics, debe enviar los datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que cada campo del objeto `data` sea una entrada en la herramienta de asignación de secuencia de datos que lo asigne a un campo de esquema XDM. La asignación solo debe realizarse una vez para este flujo de trabajo y no implica realizar cambios de implementación. Sin embargo, es un paso adicional que no es necesario cuando se envían datos en un objeto XDM.</li></ul> |

El Adobe recomienda seguir esta ruta de implementación en los siguientes casos:

* Tiene una implementación existente de mediante la biblioteca JavaScript de AppMeasurement de Adobe Analytics. Si tiene una implementación con la extensión de etiquetas de Adobe Analytics, siga [Migrar de la extensión de etiquetas de Adobe Analytics a la extensión de etiquetas del SDK web](analytics-extension-to-web-sdk.md) en su lugar.
* Tiene intención de utilizar Customer Journey Analytics en el futuro, pero no desea reemplazar la implementación de Analytics con una implementación de SDK web desde cero. Reemplazar la implementación desde cero en el SDK web requiere el mayor esfuerzo, pero también ofrece la arquitectura de implementación a largo plazo más viable. Si su organización desea realizar el esfuerzo de una implementación limpia del SDK web, consulte [Ingesta de datos mediante el SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) en la guía del usuario del Customer Journey Analytics.

## Pasos necesarios para migrar al SDK web

Las siguientes medidas contienen objetivos concretos para alcanzar. Haga clic en cada paso para obtener instrucciones detalladas sobre cómo hacerlo.

+++**1. Crear y configurar una secuencia de datos**

Cree una secuencia de datos en la recopilación de datos de Adobe Experience Platform. Cuando envía datos a este conjunto de datos, estos se reenvían a Adobe Analytics. En el futuro, este mismo conjunto de datos reenviará datos a Customer Journey Analytics.

1. Vaya a [experience.adobe.com](https://experience.adobe.com) e inicie sesión con sus credenciales.
1. Utilice la página de inicio o el selector de producto en la esquina superior derecha para navegar a **[!UICONTROL Recopilación de datos]**.
1. En el panel de navegación izquierdo, seleccione **[!UICONTROL Datastreams]**.
1. Seleccione **[!UICONTROL Nueva secuencia de datos]**.
1. Escriba el nombre que desee y luego seleccione **[!UICONTROL Guardar]**.
1. Una vez creada la secuencia de datos, seleccione **[!UICONTROL Agregar servicio]**.
1. En el menú desplegable del servicio, seleccione **[!UICONTROL Adobe Analytics]**.
1. Introduzca el mismo ID de grupo de informes que el sitio al que envía actualmente los datos de análisis. Haga clic en **[!UICONTROL Guardar]**.

![Agregar servicio de Adobe Analytics](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

El conjunto de datos ya está listo para recibir y pasar datos a Adobe Analytics. Tenga en cuenta el ID de la secuencia de datos, ya que este ID es necesario al configurar el SDK web en código.

+++

+++**2. Instale la biblioteca JavaScript del SDK web**

Hacer referencia a la última versión de `alloy.js` para que se puedan usar sus llamadas al método. Consulte [Instalar el SDK web mediante la biblioteca JavaScript](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/install/library) para obtener información detallada y bloques de código que utilizar.

+++

+++**3. Configurar el SDK web**

Configure la implementación para que apunte a la secuencia de datos creada en el paso anterior mediante el comando del SDK web [`configure`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/overview). El comando `configure` debe estar establecido en todas las páginas para que pueda incluirlo junto con el código de instalación de la biblioteca.

Use las propiedades [`datastreamId`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/datastreamid) y [`orgId`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/orgid) en el comando `configure` del SDK web:

* Establezca `datastreamId` en el ID de secuencia de datos recuperado del paso anterior.
* Establezca `orgId` en la organización de IMS de su organización.

```js
alloy("configure", {
    datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
    orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Opcionalmente, puede establecer otras propiedades en el comando [`configure`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/overview) en función de los requisitos de implementación de su organización.

+++

+++**4. Actualizar lógica de código para utilizar una carga útil JSON**

Cambie la implementación de Analytics para que no dependa de `AppMeasurement.js` ni del objeto `s`. En su lugar, establezca variables en un objeto JavaScript con formato correcto, que se convierte en un objeto JSON cuando se envía al Adobe. Tener una [capa de datos](../../prepare/data-layer.md) en el sitio ayuda enormemente a la hora de establecer valores, ya que puede seguir haciendo referencia a esos mismos valores.

Para enviar datos a Adobe Analytics, la carga del SDK web debe usar `data.__adobe.analytics` con todas las variables de análisis establecidas dentro de este objeto. Las variables de este objeto comparten nombres y formatos idénticos a los de sus equivalentes de variables de AppMeasurement. Por ejemplo, si establece la variable `products`, no la divida en objetos individuales como lo haría con XDM. En su lugar, inclúyala como una cadena exactamente como es si establece la variable `s.products`:

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

En última instancia, esta carga útil contiene todos los valores deseados y todas las referencias al objeto `s` en su implementación se eliminan. Puede utilizar cualquiera de los recursos que proporciona JavaScript para establecer este objeto de carga útil, incluida la notación de puntos para establecer valores individuales.

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

Actualice todas las instancias en las que llame a [`s.t()`](../../vars/functions/t-method.md) y a [`s.tl()`](../../vars/functions/tl-method.md), reemplazándolas por el comando [`sendEvent`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/sendevent/overview). Hay tres escenarios a considerar:

* **Seguimiento de vista de página**: reemplace la llamada de seguimiento de vista de página con el comando `sendEvent` del SDK web:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Seguimiento automático de vínculos**: La propiedad de configuración [`clickCollectionEnabled`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) está habilitada de manera predeterminada. Establece automáticamente las variables de seguimiento de vínculos correctas para enviar datos a Adobe Analytics. Si desea deshabilitar el seguimiento automático de vínculos, establezca esta propiedad en `false` dentro del comando [`configure`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/overview).

* **Seguimiento manual de vínculos**: el SDK web no tiene comandos independientes entre las llamadas a pageview y a las que no son a pageview. Proporcione esa distinción dentro del objeto de carga útil.

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

+++**6. Validar y publicar cambios**

Una vez que haya quitado todas las referencias al AppMeasurement y al objeto `s`, publique los cambios en su entorno de desarrollo para validar que la nueva implementación funciona. Una vez que haya validado que todo funciona correctamente, puede publicar las actualizaciones en producción.

Si se migra correctamente, `AppMeasurement.js` ya no será necesario en el sitio y se podrán eliminar todas las referencias a este script.

+++

En este punto, la implementación de Analytics está completamente basada en el SDK web y está preparada para pasar a Customer Journey Analytics en el futuro.
