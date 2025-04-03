---
description: Usar el inventario de Analytics
title: Inventario de Analytics
feature: Admin Tools
role: Admin
hide: true
hidefromtoc: true
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: 1e52aecdbb26dce0875b2df685ed2fa860eaba85
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 25%

---

# Inventario de Analytics {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Inventario de Analytics"
>abstract="En esta página se ofrece información general completa sobre el entorno de Adobe Analytics, incluido el número de proyectos y componentes, grupos de informes, usuarios, etc. Esta información es especialmente valiosa a medida que inicia los preparativos para actualizar a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

El inventario de Analytics proporciona una visión general del entorno de Adobe Analytics, incluido el número de proyectos y componentes, grupos de informes, usuarios, etc. Esta información es especialmente valiosa a medida que inicia los preparativos para actualizar a Customer Journey Analytics.

El objetivo de esta aplicación es ayudarle a responder a las siguientes preguntas:

* Para su organización, ¿qué recursos (como grupos de informes, segmentos, usuarios, proyectos de Workspace, fuentes de datos, etc.) necesita actualizar y qué recursos puede dejar?

* Una vez que haya determinado qué recurso debe migrar:

   * ¿Debe realizar alguna limpieza de recursos antes de esta actualización?

   * ¿Debe llevar a cabo alguna consolidación de activos como parte del proceso?

   * ¿Cuál debe ser la secuencia de actualización de los recursos?

   * ¿Qué grupo de grupos de informes debe actualizar primero? último?

## Permisos

El inventario de Analytics está disponible para los usuarios con privilegios de administrador de productos de Adobe Analytics en [Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/admin-roles-in-analytics).

## Acceder al inventario de Analytics

1. Haga clic en **[!UICONTROL Inventario de Analytics]** en el menú **[!UICONTROL Administrador]**. O vaya a **[!UICONTROL Todos los administradores]** > **[!UICONTROL Inventario de Analytics]**.

![Menú-inventario-de-Analytics](assets/an-inventory-menu.png)

1. La pantalla principal muestra un inventario completo del entorno de Adobe Analytics:

   ![Pantalla de inventario principal](assets/an_inventory.png)

   En concreto, esta pantalla aparece

   * Número total de proyectos de cuadros de resultados móviles y Analysis Workspace activos en esta organización entre todos los usuarios.
   * Número total de segmentos y métricas calculadas que están activos en esta organización en todos los usuarios.
   * Número total de grupos de informes base que se han definido (no se incluyen los grupos de informes virtuales).
   * Si la función Media Analytics está activa y si es así, en qué modo.
   * Número total de usuarios definidos en esa organización.


## Componentes {#components}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-components"
>title="Componentes"
>abstract="En esta sección se muestra el número de proyectos, segmentos y métricas calculadas que existen en el entorno de Adobe Analytics. Los proyectos y componentes se pueden migrar a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

En esta versión inicial, puede ver los números de inventario resumidos de los proyectos de Workspace, los segmentos y las métricas calculadas. Las versiones posteriores le permitirán analizar estos componentes.

## Configuración y recopilación de datos {#data-config}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-data-config"
>title="Configuración y recopilación de datos"
>abstract="En esta sección se muestra el número de grupos de informes en su entorno de Adobe Analytics, así como su acceso a los medios de streaming. "

<!-- markdownlint-enable MD034 -->

### Grupos de informes

La vista de grupos de informes muestra todos los grupos de informes definidos en una organización. Le permite responder a las siguientes preguntas:

* ¿Qué grupos de informes han recibido la mayor cantidad de visitas en los últimos 90 días?
* ¿Qué grupos de informes no han recibido ninguna visita en los últimos 90 días?
* ¿Qué grupos de informes tienen el mayor número de dimensiones definidas?
* ¿Qué grupos de informes tienen el mayor número de métricas definidas?

Las respuestas a estas preguntas le darán una buena idea de qué grupos de informes son los mejores candidatos para la migración.

1. Para analizar los grupos de informes, vaya a **[!UICONTROL Configuración y recopilación de datos]** > **[!UICONTROL Grupos de informes]** y haga clic en **[!UICONTROL Analizar]**.

   ![Lista de grupos de informes](assets/an_inv_rs.png)

   | Elemento | Descripción |
   | --- | --- |
   | Nombre | Nombre del grupo de informes |
   | ID | El ID del grupo de informes (rsid). Especifica un ID único que contiene solamente caracteres alfanuméricos. La ID no se puede cambiar una vez creada. Adobe establece el prefijo de ID necesario, que no se puede cambiar tampoco. |
   | Ocurrencias (últimos 90 días) | ¿Cuántas visitas recibió este grupo de informes en los últimos 90 días? |
   | Métricas | ¿Cuántas métricas se definen en este grupo de informes? |
   | Dimensiones | ¿Cuántas dimensiones se definen en este grupo de informes? |
   | Analytics for Target (A4T) habilitado | ¿Está habilitado este grupo de informes para [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t)? |
   | Canales de marketing habilitados | ¿Está habilitado este grupo de informes para [Canales de mercadotecnia](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel)? |
   | Conector de Source activado | [En desarrollo] ¿Está habilitado este grupo de informes para el [Conector de Adobe Analytics Source para los datos del grupo de informes](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics) en Adobe Experience Platform? En otras palabras, ¿se puede migrar este grupo de informes a Customer Journey Analytics mediante el conector de Source de Analytics? |
   | Tipo de calendario | Para obtener más información, consulte [Calendarios personalizados](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/custom-calendar#) |

1. Observe que...

### Exportar a CSV

1. Para exportar la lista de grupos de informes a un archivo .csv, haga clic en **[!UICONTROL Exportar a CSV]**.

1. El archivo .csv aparecerá en la carpeta Descargas.

1. Ábralo y guárdelo con una aplicación de hoja de cálculo en su dispositivo.


## Administración de usuarios {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="Administración de usuarios"
>abstract="En esta sección se muestra la cantidad de usuarios en su entorno de Adobe Analytics."

<!-- markdownlint-enable MD034 -->

La administración de usuarios estará disponible en una versión posterior del inventario de Analytics.