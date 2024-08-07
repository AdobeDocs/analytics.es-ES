---
title: Migración de la extensión de etiqueta de Adobe Analytics a la extensión de etiqueta del SDK web
description: Actualice la implementación de Analytics en las etiquetas de recopilación de datos de Adobe Experience Platform para utilizar la extensión del SDK web.
exl-id: 691c29ca-d169-4ef8-9f91-d0375166796d
source-git-commit: 7bd4a188e5a2171260f1f0696d8bebad854dba4a
workflow-type: tm+mt
source-wordcount: '1706'
ht-degree: 5%

---

# Migración de la extensión de etiqueta de Adobe Analytics a la extensión de etiqueta del SDK web

Esta ruta de implementación implica un método de migración metódico para pasar de la extensión de etiquetas de Adobe Analytics a la extensión de etiquetas del SDK web. Otras rutas de implementación se tratan en páginas independientes:

* [AppMeasurement a la biblioteca JavaScript del SDK web](appmeasurement-to-web-sdk.md): Un enfoque sencillo y metódico para migrar al SDK web, excepto que no utiliza etiquetas. En su lugar, quite manualmente la biblioteca de recopilación de datos de Adobe Analytics (`AppMeasurement.js`) y reemplácela por la biblioteca de JavaScript del SDK web (`alloy.js`).
* [Extensión de etiquetas de SDK web](web-sdk-tag-extension.md): Una instalación nueva del SDK web en la que administra la implementación mediante etiquetas en la recopilación de datos de Adobe Experience Platform. Requiere el grupo de campos Adobe Analytics ExperienceEvent, que incluye variables típicas de Analytics que se deben incluir en el esquema XDM.
* [Biblioteca JavaScript de SDK web](web-sdk-javascript-library.md): Una instalación nueva del SDK web mediante la biblioteca JavaScript de SDK web (`alloy.js`). Administre la implementación usted mismo en lugar de utilizar la interfaz de usuario de etiquetas. Requiere el grupo de campos Adobe Analytics ExperienceEvent, que incluye variables típicas de Analytics que se deben incluir en el esquema XDM.

## Ventajas y desventajas de esta ruta de implementación

El uso de este enfoque de migración tiene ventajas y desventajas. Valore cuidadosamente cada opción para decidir qué enfoque es el mejor para su organización.

| Ventajas | Desventajas |
| --- | --- |
| <ul><li>**No hay cambios de código en su sitio**: Debido a que su implementación ya tiene etiquetas instaladas, todas las actualizaciones de migración se pueden realizar en la interfaz de etiquetas.</li><li>**Utiliza su implementación existente**: Este enfoque no requiere una implementación nueva. Aunque sí requiere nuevas acciones de regla, puede reutilizar los elementos de datos y las condiciones de regla existentes con cambios mínimos.</li><li>**No requiere un esquema**: Para esta fase de migración al SDK web, no necesita un esquema XDM. En su lugar, puede rellenar el objeto `data`, que envía datos directamente a Adobe Analytics. Una vez completada la migración al SDK web, puede crear un esquema para su organización y utilizar la asignación de flujos de datos para rellenar los campos XDM aplicables. Si se requiere un esquema en esta fase del proceso de migración, su organización se vería obligada a utilizar un esquema XDM de Adobe Analytics. El uso de este esquema dificulta que su organización utilice su propio esquema en el futuro.</li></ul> | <ul><li>**Deuda técnica de la implementación**: dado que este método usa una forma modificada de la implementación existente, puede ser más difícil rastrear la lógica de la implementación y realizar cambios cuando sea necesario. El código personalizado puede ser especialmente difícil de depurar.</li><li>**Requiere asignación para enviar datos a Platform**: cuando su organización esté lista para utilizar Customer Journey Analytics, debe enviar los datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que cada campo del objeto `data` sea una entrada en la herramienta de asignación de secuencia de datos que lo asigne a un campo de esquema XDM. La asignación solo debe realizarse una vez para este flujo de trabajo y no implica realizar cambios de implementación. Sin embargo, es un paso adicional que no es necesario cuando se envían datos en un objeto XDM.</li></ul> |

El Adobe recomienda seguir esta ruta de implementación en los siguientes casos:

* Tiene una implementación existente de con la extensión de etiquetas de Adobe Analytics. Si tiene una implementación con el AppMeasurement, siga [Migrar del AppMeasurement al SDK web](appmeasurement-to-web-sdk.md) en su lugar.
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

El conjunto de datos ya está listo para recibir y pasar datos a Adobe Analytics.

+++

+++**2. Agregue la extensión del SDK web a la propiedad de etiquetas**

Esta sección prepara la etiqueta para el grueso del esfuerzo de migración que se produce en el siguiente paso.

1. Haga clic en el icono de hamburguesa en la parte superior izquierda de la interfaz de Adobe Experience Platform y, a continuación, seleccione **[!UICONTROL Etiquetas]**.
1. Seleccione la propiedad de etiquetas que desee.
1. En el panel de navegación izquierdo de la propiedad de etiquetas, seleccione **[!UICONTROL Extensiones]**.
1. Seleccione **[!UICONTROL Catálogo]** cerca de la parte superior para ver una lista de todas las extensiones disponibles.
1. Busque y seleccione la extensión **[!UICONTROL Adobe Experience Platform Web SDK]** y, a continuación, haga clic en **[!UICONTROL Instalar]** a la derecha.

   ![Catálogo](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Aparecerán los ajustes de configuración de la extensión. Busque la sección Flujos de datos y seleccione el flujo de datos que creó en el paso anterior.

   ![Selección de secuencia de datos](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Seleccione **[!UICONTROL Guardar]**.

La propiedad de etiquetas ahora tiene instalado el SDK web.

+++

+++**3. Crear un elemento de datos de objeto de datos**

El elemento de datos del objeto de datos proporciona un marco de trabajo intuitivo para configurar una carga útil que el SDK web utiliza para enviar a un conjunto de datos. La mayoría de las reglas que actualiza en el siguiente paso interactúan con este elemento de datos.

1. En la navegación izquierda de la interfaz de etiquetas, seleccione **[!UICONTROL Elementos de datos]**.
1. Seleccionar **[!UICONTROL Agregar elemento de datos]**
1. Asigne al elemento de datos la siguiente configuración:
   * [!UICONTROL Nombre]: Cualquier cosa que desee, como &quot;Capa de datos&quot; u &quot;Objeto de datos&quot;
   * [!UICONTROL Extensión]: [!UICONTROL SDK web de Adobe Experience Platform]
   * [!UICONTROL Tipo de elemento de datos]: [!UICONTROL Variable]
   * Las casillas de verificación pueden permanecer tal cual
1. A la derecha, seleccione la siguiente configuración:
   * Botón de opción Propiedad: [!UICONTROL Datos]
   * Solución: [!UICONTROL Adobe Analytics]
1. Seleccione **[!UICONTROL Guardar]**.

![Crear elemento de datos](assets/create-data-element.png) {style="border:1px solid lightslategray"}

La propiedad de etiquetas ahora tiene todo lo necesario para actualizar cada regla.

+++

+++**4. Actualice las reglas para utilizar la extensión del SDK web en lugar de la extensión de Analytics**

Este paso supone la mayor parte del esfuerzo necesario para migrar al SDK web y requiere conocer cómo funciona la implementación. A continuación se proporciona un ejemplo de cómo editar una regla de etiqueta típica. Actualice todas las reglas de etiquetas de la implementación para reemplazar todas las referencias a la extensión de Adobe Analytics con la extensión del SDK web.

1. En la navegación izquierda de la interfaz de etiquetas, seleccione **[!UICONTROL Reglas]**.
1. Seleccione una regla para editarla.
1. Seleccione la acción **[!UICONTROL Adobe Analytics - Set Variables]**
1. Tenga en cuenta todas las variables de Analytics configuradas dentro de esta regla. Incluya ambas variables establecidas en los menús desplegables y las variables establecidas dentro del código personalizado.
1. Cambie [!UICONTROL Action Configuration] por la siguiente configuración:
   * [!UICONTROL Extensión]: [!UICONTROL SDK web de Adobe Experience Platform]
   * [!UICONTROL Tipo de acción]: Actualizar variable
1. Asegúrese de que el objeto de datos esté seleccionado en la lista desplegable de la derecha.
1. Establezca las variables de Analytics en sus mismos valores respectivos, ya que se configuraron en la extensión de Analytics.
   * Las variables configuradas dentro de la interfaz de etiquetas pueden traducirse directamente a los mismos valores.
   * Las variables de cadena configuradas en el código personalizado requieren ajustes mínimos. En lugar de usar el objeto `s`, use `data.__adobe.analytics`. Por ejemplo, `s.eVar1` se traduciría a `data.__adobe.analytics.eVar1`.
   * Las variables de configuración de Analytics y las llamadas a métodos en el código personalizado pueden requerir la modificación de la lógica de implementación. Consulte cada [variable](/help/implement/vars/overview.md) correspondiente para determinar cómo lograr su equivalente mediante el SDK web.
1. Una vez replicada toda la lógica de reglas mediante la extensión del SDK web, seleccione **[!UICONTROL Conservar cambios]**.
1. Repita estos pasos para cada configuración de acción que utilice la extensión de Adobe Analytics para establecer valores. Este paso incluye ambas variables configuradas mediante la interfaz de etiquetas y las variables configuradas mediante código personalizado. Los bloques de código personalizado no pueden hacer referencia al objeto `s` en ninguna parte.

Los pasos anteriores solo se aplican a las reglas que establecen valores. Los pasos siguientes reemplazan todas las acciones que usan la [!UICONTROL Configuración de la acción] [!UICONTROL Enviar señalización].

1. Seleccione una regla que envíe una señalización.
1. Seleccione la acción **[!UICONTROL Adobe Analytics - Send Beacon]**.
1. Observe el valor actual del botón de opción [!UICONTROL Tracking] a la derecha ([`s.t()`](../../vars/functions/t-method.md) o [`s.tl()`](../../vars/functions/tl-method.md)).
1. Cambie [!UICONTROL Action Configuration] por la siguiente configuración:
   * [!UICONTROL Extensión]: [!UICONTROL SDK web de Adobe Experience Platform]
   * [!UICONTROL Tipo de acción]: [!UICONTROL Enviar evento]
1. A la derecha, cambie la configuración de la acción a lo siguiente:
   * [!UICONTROL Tipo]: Para `s.t()`, use **[!UICONTROL Vistas de página de detalles de páginas web]**. Para `s.tl()`, use **[!UICONTROL Clics en vínculos de interacción web]**. Si usa [`s.tl()`](../../vars/functions/tl-method.md), también debe incluir los campos siguientes en el objeto de datos. Estos campos se enumeran en [!UICONTROL Propiedades adicionales] al realizar la configuración de la acción [!UICONTROL Actualizar variable]:
      * [Nombre de la vinculación](../../vars/functions/tl-method.md)
      * [Tipo de vínculo](../../vars/functions/tl-method.md)
      * [URL de vínculo](../../vars/config-vars/linkurl.md)
1. Seleccione **[!UICONTROL Conservar cambios]**.
1. Repita estos pasos para cada configuración de acción que utilice Adobe Analytics para enviar una señalización.

+++

+++**5. Publish actualizó las reglas**

La publicación de reglas actualizadas sigue el mismo flujo de trabajo que cualquier otro cambio en la configuración de las etiquetas.

1. En la navegación izquierda de la interfaz de etiquetas, seleccione **[!UICONTROL Flujo de publicación]**.
1. Seleccione **[!UICONTROL Agregar biblioteca]**.
1. Asigne un nombre a esta confirmación de etiqueta, como &quot;Actualizar al SDK web&quot;.
1. Seleccione **[!UICONTROL Agregar todos los recursos modificados]**.
1. Seleccione **[!UICONTROL Guardar]**.
1. El flujo de trabajo de publicación muestra un punto naranja que indica que se está generando. Una vez que el punto se vuelva verde, los cambios estarán disponibles en el entorno de desarrollo.
1. Pruebe los cambios en el entorno de desarrollo para asegurarse de que todas las reglas se activan correctamente y de que el objeto de datos se rellena con los valores esperados.
1. Cuando esté listo, envíe la biblioteca para su aprobación, créela al entorno de ensayo y, finalmente, apruebe y publique en producción.

![Flujo de publicación](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Deshabilitar extensión de Analytics**

Una vez que la implementación de etiquetas esté completamente en el SDK web, puede desactivar la extensión de Adobe Analytics.

1. En la navegación izquierda de la interfaz de etiquetas, seleccione **[!UICONTROL Extensiones]**.
1. Busque y seleccione la extensión [!UICONTROL Adobe Analytics]. A la derecha, seleccione **[!UICONTROL Deshabilitar]**.
1. Siga el mismo flujo de trabajo de publicación anterior para publicar la eliminación de la extensión [!UICONTROL Adobe Analytics].
1. Una vez que la extensión esté desactivada en producción, puede desinstalarla por completo. Seleccione la extensión, seleccione el menú de tres puntos de la derecha y, a continuación, seleccione **[!UICONTROL Desinstalar]**.
1. Siga el mismo flujo de trabajo de publicación anterior para publicar esos cambios en producción.

+++

En este punto, la implementación de Analytics está completamente basada en el SDK web y está preparada para pasar a Customer Journey Analytics en el futuro.
