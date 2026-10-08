---
title: Preparación del asignador en el asistente de actualización de Web SDK
description: Revise las variables de Analytics en los grupos de informes y elija las que desea transferir a la asignación XDM.
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
source-git-commit: 212d38950264a33b925b7281c241992cadca2bfb
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 0%
---
# Preparación del asignador

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_mapperprep"
>title="Preparación del asignador"
>abstract="Revise las variables de Analytics que la propiedad de etiquetas envía a cada grupo de informes. Las variables que seleccione aquí se transfieren a la asignación XDM. Utilice las pestañas para comprobar si hay datos recientes, buscar variables duplicadas y comparar la configuración entre grupos de informes."

<!-- markdownlint-enable MD034 -->

El asistente de actualización identifica los grupos de informes a los que la propiedad de etiquetas envía datos y, a continuación, compara las variables de Analytics en la implementación con la configuración de cada grupo de informes y los datos recientes. Utilice este paso para decidir qué variables se transfieren a la asignación [XDM](xdm-mapping.md).

El asistente de actualización utiliza los grupos de informes para comprender qué variables establece la implementación y cómo se configuran. Los datos de actividad abarcan los últimos 90 días.

## Actividad variable {#variable-activity}

La ficha **[!UICONTROL Actividad variable]** enumera las variables de Analytics para el grupo de informes que eligió asignar en [Análisis de variables](#variable-analysis), y muestra si cada una de ellas ha recopilado datos en los últimos 90 días.

Las variables que seleccione se transfieren a la asignación XDM. Considere la posibilidad de borrar variables que ya no recopilen datos o que no necesite en la implementación de Web SDK. Una variable sin actividad reciente podría seguir en uso, por ejemplo, si es estacional o tiene poco tráfico, por lo que confirme que no la necesita antes de borrarla.

Para cada variable de lista y prop de lista que transfiera, introduzca el delimitador que separa sus valores. El asistente de actualización no puede obtener delimitadores de Adobe Analytics y no puede continuar hasta que cada uno tenga un delimitador.

## Análisis variable {#variable-analysis}

Si la propiedad de etiquetas envía datos a más de un grupo de informes, elija primero el grupo de informes que desea asignar. A continuación, la ficha **[!UICONTROL Análisis de variables]** marca las variables que podrían requerir una decisión antes de asignarlas:

* Variables que parecen recopilar los mismos datos. Confirme que capturan la misma información y, a continuación, decida si desea combinarlas en una sola variable o mantenerlas separadas.
* Variables que no han recopilado datos recientemente.
* Variables cuyos valores son todos &quot;No especificados&quot;.

## Comparar grupos de informes {#compare}

Si la propiedad de etiquetas envía datos a más de un grupo de informes, la ficha **[!UICONTROL Comparar grupos de informes]** compara la configuración de cada variable en hasta tres de esos grupos de informes. Utilícelo para buscar variables que estén configuradas de forma diferente entre grupos de informes antes de asignarlas a un esquema.

## Actualizar datos de grupos de informes {#refresh}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_mapperprep_refresh"
>title="Actualizar datos de grupos de informes"
>abstract="Vuelve a comprobar los grupos de informes vinculados a esta propiedad de etiquetas, incluida su configuración de variables y los datos recientes, y vuelve a ejecutar el análisis de variables. Si el asistente de actualización aún no ha encontrado ningún grupo de informes, primero lo busca en la propiedad de etiquetas. Las selecciones y decisiones se mantienen."

<!-- markdownlint-enable MD034 -->

Puede cambiar qué grupos de informes analiza el asistente de actualización durante este paso. Si la configuración del grupo de informes cambia mientras hay una migración en curso, seleccione **[!UICONTROL Actualizar datos del grupo de informes]** para volver a ejecutar el análisis. El asistente de actualización mantiene las selecciones y decisiones existentes.

Cuando haya terminado, seleccione **[!UICONTROL Guardar y continuar]** para ir a la [asignación XDM](xdm-mapping.md).
