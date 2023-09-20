---
description: La página Métricas calculadas ofrece numerosas maneras de conservar las métricas, como compartir, filtrar, etiquetar, aprobar, copiar, eliminar y marcar como favorito.
title: Administrador de métricas calculadas
feature: Calculated Metrics
exl-id: 32430e77-2450-4672-9c21-255e76802a4c
source-git-commit: 637f498c8abee0f3c83780bccd0447f2e3a804e3
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 12%

---

# Administrador de métricas calculadas

La página Métricas calculadas ofrece numerosas maneras de conservar las métricas, como compartir, filtrar, etiquetar, aprobar, copiar, eliminar y marcar como favorito.

La página Métricas calculadas muestra todos los segmentos que posee y que han compartido con usted. Los usuarios con nivel de administrador pueden ver todas las métricas personalizadas de la organización.

<!-- add screenshot -->

## Acceso al Administrador de métricas calculadas

1. En Adobe Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Métricas calculadas**].

## Acciones disponibles en el Administrador de métricas calculadas

En el Administrador de métricas calculadas, puede:

* [Filtrar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-filter.md)

* [Marcar métricas calculadas como favoritas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md)

* [Aprobar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-approving.md)

* [Etiquetar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-tagging.md)

* [Compartir métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md)

* Exportar una métrica calculada a un archivo CSV.

* [Copiar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-copy.md)

* Eliminar métricas calculadas

## Configuración de columnas

Puede configurar la información mostrada para cada métrica calculada en el Administrador de métricas calculadas configurando las columnas que se muestran.

Para configurar las columnas visibles en el Administrador de métricas calculadas:

1. En Adobe Analytics, seleccione la **[!UICONTROL Componentes]** pestaña, luego seleccione **[!UICONTROL Métricas calculadas]**.

1. En el Administrador de métricas calculadas, seleccione la **Personalizar columnas** icono ![Icono Personalizar columnas](assets/customize-columns-icon.png)A continuación, seleccione las columnas que desea mostrar en el Administrador de métricas calculadas.

   Las columnas disponibles son las siguientes:

   | Título de columna | Descripción |
   |---|---|
   | Favoritos | Muestra iconos de estrella junto a cada métrica calculada, lo que le permite marcar las métricas calculadas como favoritas. Para obtener más información, consulte [Marcar métricas calculadas como favoritas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). |
   | Título y descripción | Estos valores se proporcionan en el Creador de métricas calculadas. Para editar el título y la descripción, seleccione el vínculo del título para abrir el Creador de métricas calculadas. |
   | Grupo de informes | Indica en qué grupo de informes se guardó por última vez la métrica. |
   | Propietario | Indica quién es el propietario de la métrica personalizada. Si no es el administrador, solo podrá ver las métricas que le pertenecen o que compartieron con usted. |
   | Etiquetas | Muestra las etiquetas que se aplicaron a la métrica, tanto por su parte como por parte de las personas que compartieron la métrica calculada con usted. |
   | Compartido con | Enumera las personas o los grupos (solo administrador) o todos (solo administrador) con los que compartió la métrica calculada. <p>Cuando se comparte una métrica calculada, aparece un icono de uso compartido junto al nombre de la métrica calculada.</p> |
   | Fecha de modificación | Indica la fecha en la que se modificó por última vez la métrica personalizada. |
   | Utilizado en | **Nota:** Esta funcionalidad se encuentra en la fase de prueba limitada de la versión y es posible que aún no esté disponible en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener más información sobre el proceso de lanzamiento de Customer Journey Analytics, consulte [Versiones de funcionalidades de Customer Journey Analytics](/help/release-notes/releases.md).<p>Muestra en cuál de los siguientes tipos de componentes se está utilizando actualmente la métrica calculada:</p> <ul><li>Alertas</li><li>Métricas calculadas </li><li>Proyectos</li><li>Proyectos programados</li></ul> Por ejemplo, si los componentes se utilizan en 40 proyectos y 2 alertas, esta columna muestra [!UICONTROL **Alertas (2), Proyectos (40)**]. <p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización o si se debe eliminar.</p><p>Esta información no incluye el uso de la API, el Report Builder o la Data Warehouse.</p><p>Puede usar el complemento [Diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) junto con esta información, para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización. |
   | Último uso | **Nota:** Esta funcionalidad se encuentra en la fase de prueba limitada de la versión y es posible que aún no esté disponible en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener más información sobre el proceso de lanzamiento de Customer Journey Analytics, consulte [Versiones de funcionalidades de Customer Journey Analytics](/help/release-notes/releases.md).<p>Muestra la fecha en la que se utilizó por última vez la métrica calculada en cualquiera de los siguientes tipos de componentes:</p> <ul><li>Alertas</li><li>Métricas calculadas </li><li>Proyectos</li><li>Proyectos programados</li></ul> <p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización o si se debe eliminar.</p><p>Esta información no incluye el uso de la API, el Report Builder o la Data Warehouse.</p><p>Puede usar el complemento [Diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) junto con esta información, para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización. |

   {style="table-layout:auto"}
