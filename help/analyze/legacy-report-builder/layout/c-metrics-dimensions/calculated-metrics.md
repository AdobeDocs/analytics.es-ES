---
description: Report Builder 5.2 es compatible con las métricas calculadas unificadas de Adobe Analytics. Entre otras innovaciones, ahora las métricas calculadas tienen un identificador global, de modo que ya no están restringidas a un grupo de informes.
title: Métricas calculadas
feature: Report Builder
role: User, Admin
exl-id: 462086eb-675f-443c-b3a6-b4fa390254da
TQID: https://experienceleague.adobe.com/Ae-k-aIMg3n3kXYWFngOzYihtlexLCoD5CmnEN3afhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 396
ht-degree: 41%

---

# Métricas calculadas

{{legacy-arb}}

Report Builder 5.2 y versiones posteriores admiten métricas calculadas de Adobe Analytics. Ahora, todas las métricas calculadas tienen un ID global: ya no están restringidas a un grupo de informes.

>[!NOTE]
>
>Los libros de trabajo existentes pueden apuntar a solicitudes con identificadores de métricas antiguas. Al usar Report Builder 5.2, dichos identificadores de métricas antiguas se convertirán en identificadores globales nuevos. Si comparte el libro de trabajo con un usuario de Report Builder 5.1 u otra anterior, dicho usuario no podrá consultar las métricas calculadas.

Para obtener más información sobre cómo crear y administrar métricas calculadas con el nuevo Creador y administrador de métricas calculadas, consulte la Guía de [Métricas calculadas](/help/components/calculated-metrics/cm-overview.md).

En el paso 2 del Asistente para solicitudes, puede filtrar y aplicar métricas calculadas.

## Filtrar métricas calculadas {#section_376E986D3E684999A7CDB08E53854159}

**Filtrar** métricas calculadas haciendo clic en el icono Filtro: ![Captura de pantalla de las opciones de filtro que muestran los campos Aplicación, Usuario y Proyecto.](/help/admin/tools/assets/filter.png)

El cuadro de diálogo Filtros avanzados se rellena con métricas estándar y calculadas.

Los filtros disponibles incluyen:

![Captura de pantalla que muestra las opciones de filtros avanzados que se describen en la tabla siguiente.](assets/advanced_filters.png)

| Nombre del filtro | Descripción |
|---|---|
| Etiquetas | Le permite filtrar métricas calculadas con etiquetas específicas. Tenga en cuenta que los filtros de etiqueta utilizan el operador AND. Si marca dos etiquetas, el panel derecho muestra las métricas que se han etiquetado con **ambas** etiquetas. |
| Grupos de informes | Si aplica el filtro “Solo el *nombre del grupo de informes*” en el Creador de métricas calculadas, en [!DNL Adobe Analytics] y, a continuación, muestra el Filtro avanzado en [!DNL Report Builder], el Filtro avanzado solo mostrará las métricas calculadas correspondientes al informe seleccionado. |
| Propietarios | Le permite filtrar métricas por propietario. Tenga en cuenta que los filtros de Propietario utilizan el operador OR. Si marca dos propietarios, el panel derecho muestra las métricas que son propiedad de **cualquiera de los propietarios de**. |
| Otros filtros > Aprobados | Muestra todas las métricas aprobadas oficialmente. |
| Otros filtros > Favoritos | Muestra todas las métricas que ha marcado como Favoritos. |
| Otros filtros > Míos | Muestra todas las métricas de su propiedad. |
| Otros filtros > Compartidos conmigo | Muestra todas las métricas que otros usuarios han compartido con usted. |

## Aplicar métricas calculadas {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

Una vez que haya seleccionado los filtros, haga clic en **[!UICONTROL Aplicar]** para aplicarlos a su solicitud. Las métricas seleccionadas ahora se añaden al diseño del informe.

![Captura de pantalla que muestra el Paso 2 del Asistente para solicitudes - Totales del sitio que apuntan a la ventana Filtros avanzados y métricas de informe aplicadas.](assets/filtering_for_metric.png)
