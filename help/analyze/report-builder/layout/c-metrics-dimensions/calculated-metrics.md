---
description: Report Builder 5.2 es compatible con las métricas calculadas unificadas de Adobe Analytics. Entre otras innovaciones, ahora las métricas calculadas tienen un identificador global, de modo que ya no están restringidas a un grupo de informes.
title: Métricas calculadas
uuid: c9814894-cda6-40ff-8ec4-3ab2c1908ebc
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Métricas calculadas

Report Builder 5.2 es compatible con las métricas calculadas unificadas de Adobe Analytics. Entre otras innovaciones, ahora las métricas calculadas tienen un identificador global, de modo que ya no están restringidas a un grupo de informes.

>[!NOTE] Los libros de trabajo existentes pueden apuntar a solicitudes con identificadores de métricas antiguas. Al usar Report Builder 5.2, dichos identificadores de métricas antiguas se convertirán en identificadores globales nuevos. Si comparte el libro de trabajo con un usuario de Report Builder 5.1 u otra anterior, dicho usuario no podrá consultar las métricas calculadas.

Para obtener más información sobre cómo crear y administrar métricas calculadas con el nuevo Creador y Administrador de métricas calculadas, consulte la Guía de métricas [](https://marketing.adobe.com/resources/help/es_ES/analytics/calcmetrics) calculadas.

En el paso 2 del Asistente para solicitudes, puede filtrar y aplicar métricas calculadas.

## Filtrar métricas calculadas {#section_376E986D3E684999A7CDB08E53854159}

Para **filtrar** métricas calculadas, haga clic en el icono Filtrar:  ![](assets/segment_filter.png)

. El cuadro de diálogo Filtros avanzados se rellena con métricas estándar y calculadas.

Los filtros disponibles incluyen:

![](assets/advanced_filters_(2).png)

| Nombre del filtro | Descripción |
|---|---|
| Etiquetas | Permite filtrar métricas calculadas con etiquetas específicas. Tenga en cuenta que los filtros de etiquetas utilizan el operador Y. Si marca dos etiquetas, el panel derecho muestra las métricas que se han etiquetado con **ambas** etiquetas. |
| Grupos de informes | Si aplica el filtro “Solo el *nombre del grupo de informes*” en el Creador de métricas calculadas, en [!DNL Reports & Analytics] y, a continuación, muestra el Filtro avanzado en [!DNL Report Builder], el Filtro avanzado solo mostrará las métricas calculadas correspondientes al informe seleccionado. |
| Propietarios | Permite filtrar métricas por propietario. Tenga en cuenta que los filtros propietarios utilizan el operador O. Si marca dos propietarios, el panel derecho muestra las métricas que son propiedad de **cualquiera** de los propietarios. |
| Otros filtros > Aprobados | Muestra todos los segmentos oficialmente métricas aprobadas. |
| Otros filtros > Favoritos | Muestra todas las métricas marcadas como Favoritos. |
| Otros filtros > Míos | Muestra todas las métricas que le pertenecen. |
| Otros filtros > Compartidos conmigo | Muestra todas las métricas que otros usuarios compartieron con usted. |

## Aplicar métricas calculadas {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

Después de seleccionar los filtros, haga clic en **[!UICONTROL Apply]** para aplicarlos a la solicitud. Las métricas seleccionadas ahora se agregan al diseño del informe.

![](assets/filtering_for_metric.png)

