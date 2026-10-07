---
title: Asistente de actualización de Web SDK
description: Planifique y ejecute la migración de la extensión de etiquetas de Adobe Analytics a Adobe Experience Platform Web SDK.
feature: Implementation Basics
role: Admin, Developer, Leader
badge: Beta
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 629efca210346d32b8555c60f7db15d1d8285b20
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 3%
---
# Asistente de actualización de Web SDK

El asistente de actualización de Web SDK le ayuda a planificar y ejecutar la migración de la extensión de etiquetas de Adobe Analytics a Adobe Experience Platform Web SDK. Lleva la migración a un único espacio de trabajo guiado, para que pueda pasar de la implementación de etiquetas existente a Web SDK de una manera estructurada y rastreable.

## Funcionamiento del asistente de actualización {#how-it-works}

Cada migración funciona con la implementación de Adobe Analytics en una propiedad de etiquetas. El asistente de actualización agrega acciones de Web SDK a las reglas existentes sin eliminar sus acciones de Adobe Analytics, de modo que la implementación continúa enviando datos a Adobe Analytics a lo largo de Web SDK.

El asistente de actualización solo convierte componentes de Adobe Analytics. Puede incluir componentes de otras extensiones, como Adobe Target, Adobe Audience Manager o extensiones de terceros, pero el asistente de actualización no los convierte al SDK web.

El asistente de actualización le guiará a través de los pasos siguientes y cada paso se basa en las decisiones que tome en el paso anterior:

1. **[Selección de componentes](component-selection.md)**: elija las reglas, elementos de datos y extensiones que desea incluir en la migración.
1. **[Conclusiones de la auditoría](audit-findings.md)**: revise las recomendaciones de limpieza opcionales de los componentes que ha seleccionado.
1. **[Verificación del grupo de informes](rs-verification.md)**: revise las variables de Analytics en los grupos de informes y elija las que desea transferir.
1. **[Asignación de XDM](xdm-mapping.md)**: asigne las variables de Analytics a los campos de un esquema XDM.
1. **[Implementación de Web SDK](web-sdk-implementation.md)**: revise las acciones de Web SDK que el asistente de actualización agrega a las reglas.
1. **[Revisión final](final-review.md)**: seleccione una zona protegida de Experience Platform, revise lo que crea la migración y finalice la migración.

Cada paso configura parte de la migración y puede volver a los pasos completados para revisarlos o cambiarlos con la frecuencia que desee. El asistente de actualización no cambia la propiedad de etiquetas ni crea nada en Experience Platform hasta que no finalice la migración. Cuando lo finaliza, el asistente de actualización crea todo a la vez y agrega los cambios de las etiquetas a una nueva biblioteca. A continuación, pruebe esa biblioteca y publíquela en producción mediante el flujo de publicación de etiquetas.

>[!IMPORTANT]
>
>El asistente de actualización utiliza inteligencia artificial (IA) para generar recomendaciones, como asignaciones de campos XDM y configuraciones de reglas de Web SDK. Es posible que estas recomendaciones no sean precisas o completas. Compruébelos antes de publicar los cambios en producción.

## Requisitos previos {#prerequisites}

Antes de crear una migración, asegúrese de lo siguiente:

* Los [permisos](#permissions) que requiere el asistente de actualización.
* Propiedad tags que utiliza la extensión Adobe Analytics.
* Una biblioteca en esa propiedad que contiene la implementación que desea migrar. La biblioteca puede estar en cualquier estado, incluso publicado. Consulte [Bibliotecas](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/libraries) en la guía de usuario sobre etiquetas.

### Permisos {#permissions}

El asistente de actualización requiere el siguiente acceso. Póngase en contacto con el administrador de productos de Experience Platform de su organización para obtener los permisos que le faltan.

| Tipo de acceso | Requerido |
| --- | --- |
| [Permisos de Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home#permissions) | <ul><li>[!UICONTROL Ver esquemas]</li><li>[!UICONTROL Administrar esquemas]</li><li>[!UICONTROL Ver conjuntos de datos de vistas]</li><li>[!UICONTROL Administrar conjuntos de datos]</li><li>[!UICONTROL Ver espacios de nombres de identidad]</li></ul> |
| Acceso al producto | <ul><li>Recopilación de datos (etiquetas)</li><li>Adobe Analytics</li></ul> |
| [Derechos de etiquetas](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/administration/user-permissions) | [!UICONTROL Administrar propiedades] |

Cuando esté listo, [cree una migración](manager.md#create).
