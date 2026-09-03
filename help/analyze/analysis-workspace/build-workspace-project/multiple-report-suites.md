---
title: Múltiples grupos de informes
description: Aprenda a trabajar con varios grupos de informes en un proyecto de Analysis Workspace.
feature: Workspace Basics
role: User, Admin
exl-id: 0429ddd9-935f-44ef-ae1e-97bb02e6e2df
TQID: https://experienceleague.adobe.com/IrWsvooPWqWmbDAD-70CgI71gEPJCQY-1wFHFyuJsyc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 69%

---

# Múltiples grupos de informes

Puede crear proyectos en Analysis Workspace con datos de más de un grupo de informes. Los grupos de informes se eligen en el panel, por lo que puede elegir un grupo de informes diferente para cada panel dentro del mismo proyecto de Workspace.

Esta capacidad es útil si desea:

* Comparar datos de dos regiones diferentes y los datos están en dos grupos de informes diferentes. Puede generar tablas y visualizaciones para comparar los datos en paralelo.

* Cree un tablero de métricas y visualizaciones para informar a otras organizaciones. Puede incluir datos de varios grupos de informes en el mismo proyecto.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Varios grupos de informes](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/using-panels/multiple-report-suites-in-analysis-workspace){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Aplicar grupo de informes a todos los paneles

Puede aplicar un grupo de informes a todos los paneles a la vez haciendo clic con el botón derecho en el encabezado de cualquier panel y seleccionando **[!UICONTROL Aplicar grupo de informes a todos los paneles]**.

![](assets/apply-rs-all-panels.png)

## Panel activo

Puede reconocer el panel activo por el borde celeste que lo rodea. Simplemente, seleccione dentro de un panel para convertir ese panel en el panel activo.

>[!TIP]
>
>Puede arrastrar y soltar en cualquier panel que esté en el mismo grupo de informes del panel activo. Al arrastrarlo a un panel inactivo del mismo grupo de informes, el panel se activará.
>

## Trabajar con varios grupos de informes

![](assets/mrs-ui.png)

1. Crear un nuevo proyecto con 2 o más paneles en Workspace.

1. Arrastre y suelte componentes (métricas, dimensiones, segmentos e intervalos de fechas) en el panel. Asegúrese de que los paneles tengan datos y visualizaciones específicos de su grupo de informes.


   >[!NOTE]
   >
   >En ocasiones, aparece un banner al cargar un proyecto (o al cambiar a un grupo de informes) en el que no todos los componentes del proyecto están incluidos en el grupo de informes. Se enumerarán los componentes que faltan. Siga [estas instrucciones](/help/admin/admin-console/permissions/product-profile.md) y establezca permisos para las métricas y dimensiones requeridas.
   >

   ![](assets/incompat-rs.png)

   Tiene 3 opciones para hacer frente a esta incompatibilidad:
   * Habilitar las dimensiones o métricas requeridas.
   * Cambiar el grupo de informes.
   * Continuar con algunos componentes faltantes. Esto implica que no habrá datos para esos componentes ni para visualizaciones en blanco.

1. Cambie el panel a otro grupo de informes y observe cómo se actualizan la etiqueta del componente (grupo de informes activo actualmente) y los componentes enumerados en función del nuevo grupo de informes.

1. Use un acceso directo del teclado (`shift` mientras arrastra) para convertir un panel inactivo en un panel activo.

1. (Opcional) También puede dirigirse a otros creadores de componentes de Analytics y comprobar que ahora muestren una etiqueta de grupo de informes que indique

   * Dónde se creará un segmento: [Generador de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md).
   * Dónde se creará una métrica calculada: [Creador de métricas calculadas](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md).
   * Dónde se generará una alerta: [Generador de alertas](/help/components/alerts/alert-builder.md).
