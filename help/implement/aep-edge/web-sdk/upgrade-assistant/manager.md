---
title: Administrar migraciones en el asistente de actualización de Web SDK
description: Cree, vea y abra migraciones en el asistente de actualización de Web SDK.
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
source-wordcount: '397'
ht-degree: 0%
---
# Administración de migraciones

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_migrations"
>title="Migraciones"
>abstract="Cada migración actualiza la implementación de Adobe Analytics en una propiedad de etiquetas a Web SDK. Abra una migración para continuar donde lo dejó o seleccione &quot;Nuevo&quot; para iniciar una."

La página **[!UICONTROL Migraciones]** es el punto de partida para el asistente de actualización de Web SDK. Enumera las migraciones de su organización, incluido el progreso de cada migración, su estado y quién las creó. Utilice esta página para crear una migración o para abrir una existente.

## Creación de una migración {#create}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_newmigration"
>title="Nueva migración"
>abstract="Seleccione la propiedad de etiquetas que desee migrar y una biblioteca en esa propiedad. El asistente de actualización toma una instantánea de la biblioteca cuando crea la migración. No se incluyen los cambios realizados en la biblioteca después de una instantánea de migración. La propiedad de etiquetas no cambia hasta que finaliza la migración."

<!-- markdownlint-enable MD034 -->

Antes de crear una migración, asegúrese de cumplir [los requisitos previos](overview.md#prerequisites).

1. En la página **[!UICONTROL Migraciones]**, seleccione **[!UICONTROL Nuevo]**.
1. Introduzca un nombre para la migración y, opcionalmente, una descripción.
1. Seleccione la propiedad de etiquetas que desee migrar.
1. Seleccione una biblioteca de etiquetas. Cuando crea la migración, el asistente de actualización toma una instantánea de la implementación tal y como existe en esta biblioteca. Los cambios que realice en la biblioteca posteriormente a no se reflejarán en la migración.
1. Seleccione **[!UICONTROL Crear]**.

La nueva migración aparece en la lista. Ábralo para iniciar [selección de componentes](component-selection.md).

## Abrir una migración {#open}

Seleccione el nombre de una migración para abrirla. Los pasos de la migración aparecen en el panel de navegación izquierdo. Puede volver a cualquier paso completado para revisarlo o cambiarlo con la frecuencia que desee, pero los pasos que aún no haya alcanzado no están disponibles.

El asistente de actualización guarda el progreso a medida que se desplaza por los pasos, por lo que puede dejar una migración y volver a ella más tarde. Nada de lo que configure surtirá efecto hasta que [finalice la migración](final-review.md#finalize). Una vez finalizada, la migración pasa a ser de solo lectura. Puede abrirlo para ver lo que ha creado, pero no puede cambiarlo.

## Otras acciones de migración {#actions}

Seleccione la fila de una migración para mostrar las acciones disponibles:

* **[!UICONTROL Continuar]**: Abre la migración.
* **[!UICONTROL Ejecución duplicada]**: crea una copia de la migración.
* **[!UICONTROL Rename]**: cambia el nombre y la descripción de la migración.
* **[!UICONTROL Archivo]**: cambia el estado de la migración a **[!UICONTROL Archivado]**.
* **[!UICONTROL Eliminar migración]**: elimina permanentemente la migración. No puede deshacer esta acción.
