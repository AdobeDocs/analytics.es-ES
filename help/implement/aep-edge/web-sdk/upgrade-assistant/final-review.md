---
title: Revisión final en el asistente de actualización de Web SDK
description: Revise y finalice una migración de Web SDK y, a continuación, publique la biblioteca de etiquetas resultante en producción.
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
source-wordcount: '469'
ht-degree: 0%
---
# Revisión final

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_finalreview"
>title="Revisión final"
>abstract="Seleccione la zona protegida de Experience Platform que desea utilizar y, a continuación, revise todo lo que esta migración crea o cambia. Nada cambia hasta que finalice la migración. Cuando lo finaliza, el asistente de actualización crea todo a la vez, agrega los cambios de las etiquetas a una nueva biblioteca y hace que esta migración sea de solo lectura. A continuación, publique esa biblioteca en producción usted mismo."

<!-- markdownlint-enable MD034 -->

La revisión final es el último paso de una migración. Muestra todo lo que la migración crea o cambia en Experience Platform y en la propiedad de etiquetas.

## Revise lo que crea la migración {#review}

En primer lugar, seleccione la zona protegida de Experience Platform en la que la migración crea sus recursos. No puede finalizar la migración hasta que seleccione una zona protegida.

A continuación, el asistente de actualización enumera todo lo que crea o cambia al finalizar la migración:

* **[!UICONTROL XDM]**: un nuevo esquema con el nombre de su asignación XDM, junto con los grupos de campos personalizados que necesita. Los grupos de campos estándar ya existen, por lo que el esquema los utiliza tal cual. Esta sección solo aparece si eligió crear un nuevo esquema en [asignación XDM](xdm-mapping.md#schema).
* **[!UICONTROL Conjuntos de datos]**: dos conjuntos de datos, uno para desarrollo y otro para producción. Cada uno recibe el nombre de la migración, como `My migration - Development`.
* **[!UICONTROL Datastreams]**: dos flujos de datos, uno para desarrollo y otro para producción, con el mismo nombre que los conjuntos de datos.
* **[!UICONTROL Etiquetas Adobe]**: Una nueva biblioteca con el nombre de la migración, como `Library - "My migration"`. La biblioteca contiene las reglas y los elementos de datos que cambia la migración, junto con la configuración de extensión que necesitan las acciones de Web SDK.

## Finalizar la migración {#finalize}

Hasta que finalice la migración, el asistente de actualización no cambia la propiedad de etiquetas ni crea nada en Experience Platform.

>[!IMPORTANT]
>
>Una vez finalizada la migración, pasa a ser de solo lectura. Puede abrirlo desde la página **[!UICONTROL Migraciones]** para ver lo que ha creado, pero no puede cambiarlo ni finalizarlo de nuevo. Dado que la nueva biblioteca aún está en desarrollo, puede editar o quitar los cambios en las etiquetas en la interfaz de usuario de etiquetas antes de publicar la biblioteca.

1. Seleccione **[!UICONTROL Crear artefactos]**.
1. En el cuadro de diálogo **[!UICONTROL Verificar estas recomendaciones]**, seleccione **[!UICONTROL Continuar]**.
1. En **[!UICONTROL Finalizar esta migración?]** , seleccione **[!UICONTROL Finalizar]**.

El asistente de actualización crea todo a la vez y muestra su progreso. Añade los cambios de las etiquetas a la nueva biblioteca, pero no publica la biblioteca.

## Publicación de los cambios {#publish}

Una vez finalizada la migración, mueva la nueva biblioteca a través del flujo de publicación de etiquetas:

1. Genere y pruebe la biblioteca en su entorno de desarrollo para asegurarse de que la implementación de Web SDK envía los datos esperados.
1. Envíe la biblioteca para su aprobación y pruébela en su entorno de ensayo.
1. Apruebe la biblioteca y publíquela en producción.

Consulte [Flujo de publicación](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/publishing-flow) en la guía de usuario sobre etiquetas.
