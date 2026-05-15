---
description: Los administradores son responsables de supervisar el estado del diccionario de datos. Esto incluye si los componentes están recopilando datos, están aprobados, contienen descripciones y no tienen duplicados.
title: Monitorización del estado del diccionario de datos
feature: Components
role: Admin
exl-id: 82176931-2bd9-4f4e-9ca7-4214d44151a8
TQID: https://experienceleague.adobe.com/q-wAiW4oUc9kH-ywKVLfNKtXHdEfnIr01GXSK-g0YqY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ba438d61e6834acb07c86cd0af58f95b88c1de7
workflow-type: tm+mt
source-wordcount: 361
ht-degree: 66%

---

# Monitorización del estado del diccionario de datos {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_share_primary"
>title="Compartir componente principal"
>abstract="Cuando se selecciona esta opción, el componente principal se comparte con todos los que tienen acceso a los componentes duplicados (tanto los propietarios como cualquiera con los que se comparten los componentes). Estos usuarios pueden seleccionar el componente principal de la lista de componentes para proyectos futuros. Sin embargo, no pueden editar el componente, aunque sean los propietarios de un componente duplicado que se haya consolidado. <br/>Esta opción solo está disponible cuando el componente principal es un segmento, una métrica calculada o un intervalo de fechas. Las métricas y dimensiones siempre están disponibles para todos los usuarios."
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_delete_duplicates"
>title="Eliminar duplicados reemplazados"
>abstract="Cuando se selecciona esta opción, los duplicados consolidados ya no están disponibles para su uso. Anule la selección de esta opción si desea que los duplicados sigan estando disponibles."

<!-- markdownlint-enable MD034 -->

Los administradores de Analytics son responsables de mantener un diccionario de datos correcto.

## Características de un diccionario de datos correcto

Un diccionario de datos correcto es aquel en el que todos los componentes:

* Se están utilizando y recopilando datos

* Incluyen descripciones útiles para que los usuarios sepan cómo utilizarlas mejor

* Están libres de duplicados innecesarios

* Están aprobados por el administrador

## Comprobar el estado del diccionario de datos

Para identificar problemas de estado en el diccionario de datos:

1. Creación de un proyecto de Analysis Workspace.

1. Seleccione el icono del diccionario de datos en la parte izquierda de Analysis Workspace. (Las formas alternativas de acceder al diccionario de datos se describen en “Acceso al diccionario de datos” en [Información general del diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)).

   Se muestra la ventana Diccionario de datos.

   ![Vista de administrador del diccionario de datos](assets/data-dictionary-admin.png)

1. Asegúrese de que el grupo de informes correcto está seleccionado en el menú desplegable.

1. En la pestaña [!UICONTROL **Salud del diccionario**], seleccione [!UICONTROL **Ver**] junto a cualquiera de las siguientes opciones:

   * [!UICONTROL **faltan descripciones en los componentes**]

   * [!UICONTROL **los componentes tienen duplicados**]

   * [!UICONTROL **los componentes no tienen datos conectados**]

   Según lo que seleccione, el filtro adecuado se aplica al diccionario de datos y solo se muestran los componentes relevantes.

1. Edite cualquiera de los componentes para mejorar el estado del diccionario de datos. Para obtener información acerca de cómo editar un componente en el diccionario de datos, consulte [Editar entradas de componentes en el diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).
