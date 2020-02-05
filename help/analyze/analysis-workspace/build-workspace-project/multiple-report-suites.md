---
title: Varios grupos de informes en Workspace
description: Descubra cómo y por qué crear proyectos en Workspace con varios grupos de informes
translation-type: tm+mt
source-git-commit: 195681c622b19fc0d701b1758097e7579ebb72f7

---


# Varios grupos de informes en Workspace

>[!IMPORTANT]
>Varios grupos de informes en Workspace se encuentran actualmente en una versión limitada. A partir del 20 de febrero de 2020, la función se lanzará a todos los clientes durante varias semanas.

Ahora puede crear proyectos en Analysis Workspace con datos de más de un grupo de informes. Los grupos de informes ahora se eligen en el nivel de panel, por lo que puede elegir un grupo de informes diferente para cada panel dentro del mismo proyecto de Workspace.

Esta capacidad es útil si desea, por ejemplo,

* Compare datos de dos regiones diferentes y los datos residen en dos grupos de informes diferentes. Puede generar tablas y visualizaciones para comparar los datos en paralelo.

* Cree un tablero de métricas y visualizaciones para informar a otras organizaciones. Ahora puede extraer datos de varios grupos de informes en el mismo proyecto.

## Panel activo

Con esta función, presentamos el concepto de &quot;panel activo&quot; frente a &quot;panel inactivo&quot;. El panel activo es reconocible por el borde azul claro que lo rodea. Al hacer clic dentro de un panel, este se convierte en el panel activo.

>[!IMPORTANT]
>Puede arrastrar y soltar componentes **únicamente en el panel** activo, incluso si otros paneles tienen el mismo grupo de informes. Si desea cambiar el panel mientras arrastra y suelta, puede utilizar un corte corto: presione `shift` mientras arrastra para cambiar un panel inactivo a un panel activo.

| Tarea | Panel activo | Panel inactivo |
|---|---|---|
| Cambiar grupo de informes | Sí | No |
| Arrastrar y soltar componentes | Sí | No |
| Visualización de arrastrar y soltar | Sí | No |

## Trabajar con varios grupos de informes

![](assets/mrs-ui.png)

1. Cree un nuevo proyecto con 2 o más paneles en Workspace.

1. Arrastre y suelte componentes (métricas, dimensiones, segmentos e intervalos de fechas) en el panel. Asegúrese de que los paneles tengan datos y visualizaciones específicos de su grupo de informes.


   >[!NOTE]
   >En ocasiones, aparece un mensaje &quot;Grupo de informes incompatible&quot; al cargar un proyecto (o al cambiar a un grupo de informes) en el que no todos los componentes incluidos en el proyecto están incluidos en el grupo de informes. Se enumerarán los componentes que faltan. Siga [estas instrucciones](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html#createproductprofiles) para establecer permisos para las métricas y dimensiones requeridas.

   ![](assets/incompat-rs.png)

   Tiene 3 opciones para hacer frente a esta incompatibilidad:
   * Continúe con algunos componentes que faltan. Esto no resultará en datos para esos componentes ni en visualizaciones en blanco.
   * Deshacer.
   * Cambiar el grupo de informes.

1. Cambie el panel a otro grupo de informes y observe cómo se actualizan la etiqueta del componente (grupo de informes activo actualmente) y los componentes enumerados en función del nuevo grupo de informes.

1. Utilice el método abreviado de teclado (`shift` mientras arrastra) para convertir un panel inactivo en un panel activo.

1. (Opcional) También puede ir a otros creadores de componentes de Analytics y asegurarse de que ahora muestren una etiqueta de grupo de informes que indique

   * Dónde se creará un segmento: Generador [de segmentos](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html).
   * Dónde se creará una métrica calculada: Creador [de métricas](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)calculadas.
   * Dónde se generará una alerta: Generador [de alertas](https://docs.adobe.com/content/help/en/analytics/components/alerts/alert-builder.html).