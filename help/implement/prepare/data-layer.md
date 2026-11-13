---
title: Creación de una capa de datos
description: Descubra cómo una capa de datos es compatible con su implementación de Analytics, por qué Adobe recomienda la capa de datos del cliente de Adobe y cómo leer los valores de la capa de datos con cada método de implementación.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/JmxM3-AVA5--7Xt4kuES35KFtYbicdGO9JZXsygzuuE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '1063'
ht-degree: 7%
---
# Creación de una capa de datos

Una capa de datos es una estructura de JavaScript del sitio que expone los datos que recopila la implementación de Analytics, como nombres de páginas, detalles de productos e ID de pedidos. El código del sitio escribe en la capa de datos y la implementación lee de ella para establecer variables de Analytics. Dado que la implementación no depende del HTML de la página, puede rediseñar el sitio sin interrumpir la recopilación de datos.

## Requisitos previos

[Crear un documento de diseño de solución](solution-design.md): Es importante que su organización se alinee en los requisitos de seguimiento. Asegúrese de estar listo con un documento de diseño de solución antes de ponerse en contacto con los equipos de desarrollo de su organización. Los datos que requiere el diseño de la solución determinan qué contiene la capa de datos.

## Elija una especificación de capa de datos {#specifications}

Adobe recomienda la [capa de datos del cliente de Adobe](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/overview) (ACDL) para implementaciones nuevas o reestructuradas. ACDL es una biblioteca JavaScript de código abierto que ofrece al sitio una forma estándar de insertar datos y eventos en una matriz `adobeDataLayer` global. Las etiquetas, el SDK web y AppMeasurement pueden leer de él, y los componentes principales de Adobe Experience Manager pueden rellenarlo automáticamente.

Su organización puede usar otras especificaciones, como [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) (CEDDL), que almacena datos en un objeto `digitalData` global, o una especificación personalizada. Lo más importante es que su organización se ajuste a una especificación que satisfaga sus necesidades.

En la tabla siguiente se compara ACDL con capas de datos basadas en objetos como CEDDL:

| | Capa de datos del cliente de Adobe (`adobeDataLayer`) | Capa de datos basada en objetos, como CEDDL (`digitalData`) |
| --- | --- | --- |
| Cómo escribe los datos el código del sitio | Inserta objetos: `adobeDataLayer.push({ page: { name: "Home" } })` | Establece propiedades: `digitalData.page.pageInfo.pageName = "Home"` |
| Cómo lee un valor su implementación | `adobeDataLayer.getState("page.name")` o un elemento de datos **Estado calculado de la capa de datos** de la extensión de etiquetas de capa de datos del cliente de Adobe | `digitalData.page.pageInfo.pageName` o un elemento de datos **Variable JavaScript** de la extensión de etiquetas Core |
| Cómo sabe la implementación que los datos están listos | El código del sitio inserta un evento, como `{ event: "page view" }`, y la implementación lo escucha. Los oyentes también se ejecutan para eventos insertados antes de agregarse. | La implementación debe leer el objeto una vez que el código del sitio termina de rellenarlo, por ejemplo, utilizando una regla Direct Call. |

## Capa de datos de ejemplo {#example}

ACDL no requiere una estructura de datos específica. Diseñe la estructura alrededor del documento de diseño de la solución y documéntela para todos los que escriban en la capa de datos o lean de ella. Los ejemplos de esta guía utilizan la siguiente estructura.

Cuando se carga una página, el código del sitio inserta los datos de la página y un evento de vista de página:

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push({
  event: "page view",
  page: {
    name: "Home",
    section: "Products",
    url: "https://example.com/products",
    referrer: "https://example.com/"
  }
});
```

Cuando un visitante completa una compra, el código del sitio inserta los detalles del pedido y un evento de compra:

```js
window.adobeDataLayer.push({
  event: "purchase",
  transaction: { id: "ABC123" },
  products: [
    { name: "Example product", category: "Example category", quantity: 1, price: 25 }
  ]
});
```

ACDL combina cada inserción en un único objeto denominado estado calculado, que se lee en la implementación. Los objetos de evento indican a la implementación cuándo leerla. Ver [Datos y el estado calculado](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/computed-state) y [Eventos](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/events).

## Flujo de trabajo {#workflow}

La implementación de Adobe Analytics mediante una capa de datos suele seguir estos pasos:

1. **Trabaje con el equipo de desarrollo del sitio para implementar una capa de datos**: El equipo de desarrollo del sitio es el principal responsable de asegurarse de que la capa de datos contenga los valores correctos. Revise esta página con el equipo de desarrollo del sitio para asegurarse de que las expectativas estén alineadas entre los equipos. Consulte [Instalar la capa de datos del cliente de Adobe](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/install).
1. **Valide la capa de datos con una consola de explorador**: abra la consola de desarrollador del explorador, lo que puede hacer en la mayoría de los exploradores con la clave `F12`. Ejecute `adobeDataLayer.getState()` para ver el estado calculado o `adobeDataLayer.getState("page.name")` para ver un solo valor. Consulte [Verificar la instalación](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/install#verify).
1. **Conectar la capa de datos a Adobe Analytics**: este paso varía según el método de implementación de su organización. Consulte [Conectar la capa de datos a Adobe Analytics](#connect).

## Conexión de la capa de datos a Adobe Analytics {#connect}

La siguiente tabla muestra cómo se lee cada método de implementación desde la capa de datos del cliente de Adobe:

| Método de implementación | Cómo leer la capa de datos | Más información |
| --- | --- | --- |
| Extensión de etiquetas del SDK web | Reglas de déclencheur con el evento **inserción de capa de datos** de la extensión de capa de datos del cliente de Adobe. Asigne valores de capa de datos a campos XDM o al objeto `data` con la acción **Actualizar variable** de Web SDK y, a continuación, envíelos con la acción **Enviar evento**. | [Enviar datos de capa de datos del cliente de Adobe con Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/web-sdk), [asignación de campos de objetos XDM](../aep-edge/xdm-var-mapping.md) y [asignación de campos de objetos de datos](../aep-edge/data-var-mapping.md) |
| Biblioteca JavaScript de Web SDK | Escuche los eventos de capa de datos con `addEventListener()` y establezca los campos XDM o `data` de la capa de datos cuando llame a `sendEvent`. | [Enviar datos de capa de datos del cliente de Adobe con Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/web-sdk), [asignación de campos de objetos XDM](../aep-edge/xdm-var-mapping.md) y [asignación de campos de objetos de datos](../aep-edge/data-var-mapping.md) |
| Extensión de Analytics | Déclencheur las reglas con el evento **inserción de capa de datos** y cree **elementos de datos de estado calculado de capa de datos** desde la extensión de capa de datos del cliente de Adobe. Asigne los elementos de datos a las variables de Analytics en la acción **Set Variables** y, a continuación, envíe los datos con la acción **Send Beacon**. | [Asignar objetos de capa de datos a elementos de datos](../launch/layer-to-elements.md) y [Asignar elementos de datos a variables de Analytics](../launch/elements-to-variable.md) |
| AppMeasurement | Leer los valores con `getState()` después de cargar ACDL y, a continuación, llamar a `s.t()`. | [Leer la capa de datos con AppMeasurement](#appmeasurement) |

### Lectura de la capa de datos con AppMeasurement {#appmeasurement}

ACDL agrega su método `getState()` a la matriz `adobeDataLayer` cuando se carga la biblioteca. Para asegurarse de que la biblioteca se ha cargado y de que el estado calculado incluye los datos más recientes, lea los valores dentro de un detector de eventos:

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function(dl) {
  dl.addEventListener("page view", function(event) {
    s.pageName = dl.getState("page.name");
    s.channel = dl.getState("page.section");
    s.t();
  });
});
```

El agente de escucha se ejecuta una vez por cada evento `page view`, incluidos los eventos insertados antes de que se agregara el agente de escucha. Las páginas de variables de esta guía, como [`pageName`](../vars/page-vars/pagename.md), muestran cómo leer valores individuales con `getState()`. Use esos ejemplos dentro de un oyente como este, o en el editor de código personalizado de una regla de extensión de Analytics que un evento de **inserción de capa de datos** déclencheur.

Si la implementación envía más de una visita por página, por ejemplo, en una aplicación de una sola página, utilice [`clearVars()`](../vars/functions/clearvars.md) para que los valores de una visita no persistan hasta la siguiente.

## Pasos siguientes

* [Asignar objetos de capa de datos a elementos de datos](../launch/layer-to-elements.md): use la capa de datos del sitio en las etiquetas de Adobe Experience Platform.
* [Documentación de la capa de datos del cliente de Adobe](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/overview): obtenga información acerca de todos los métodos, eventos y prácticas recomendadas de ACDL.
