---
description: Usar el inventario de Analytics
title: Inventario de Analytics
feature: Admin Tools
role: Admin
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: 1a6f086105c76cbfcf361ddc54d71a7e7c4921d5
workflow-type: tm+mt
source-wordcount: '1183'
ht-degree: 21%

---

# Inventario de Analytics {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Inventario de Analytics"
>abstract="En esta página se ofrece información general completa sobre el entorno de Adobe Analytics, incluido el número de proyectos y componentes, grupos de informes, usuarios, etc. Esta información es especialmente valiosa a medida que inicia los preparativos para actualizar a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

El inventario de Analytics proporciona una visión general del entorno de Adobe Analytics, incluido el número de proyectos y componentes, grupos de informes, usuarios, etc. Esta información es especialmente valiosa a medida que inicia los preparativos para actualizar a Customer Journey Analytics.

El objetivo del inventario de Analytics es ayudarle a responder a las siguientes preguntas:

* En el caso de su organización, ¿qué recursos (como grupos de informes, segmentos, usuarios, proyectos de Workspace, etc.) necesita migrar y qué recursos puede dejar?

* Una vez que haya determinado qué recurso debe migrar:

   * ¿Debe realizar alguna limpieza de recursos antes de esta actualización?

   * ¿Debe llevar a cabo alguna consolidación de activos como parte del proceso?

   * ¿Cuál debe ser la secuencia de actualización de los recursos?

   * ¿Qué grupos de informes debe actualizar primero o último?

## Permisos

El inventario de Analytics está disponible para los usuarios con privilegios de administrador de productos de Adobe Analytics en [Adobe Admin Console](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-console/admin-roles-in-analytics).

## Acceder al inventario de Analytics

1. Haga clic en **[!UICONTROL Inventario de Analytics]** en el menú **[!UICONTROL Administrador]**. O vaya a **[!UICONTROL Todos los administradores]** > **[!UICONTROL Inventario de Analytics]**.

![Menú-inventario-de-Analytics](assets/an-inventory-menu.png)

1. La pantalla principal muestra un inventario completo del entorno de Adobe Analytics:

   ![Pantalla de inventario principal](assets/an_inventory.png)

   En concreto, esta pantalla muestra:

   * Número total de proyectos de cuadros de resultados móviles y Analysis Workspace activos en esta organización, entre todos los usuarios.
   * Número total de segmentos y métricas calculadas que están activos en esta organización, entre todos los usuarios.
   * Número total de grupos de informes base que se han definido. No se incluyen los grupos de informes virtuales.
   * Si la función Media Analytics está activa y si es así, en qué modo.
   * Número total de usuarios definidos en esta organización.


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
* ¿Qué grupos de informes no han recibido visitas en los últimos 90 días?
* ¿Qué grupos de informes tienen el mayor número de dimensiones definidas?
* ¿Qué grupos de informes tienen el mayor número de métricas definidas?

Las respuestas a estas preguntas le darán una buena idea de qué grupos de informes son los mejores candidatos para la migración.

>[!NOTE]
>
>Esta tabla se rellena lentamente, con un valor de celda cada vez.


1. Para analizar los grupos de informes, vaya a **[!UICONTROL Configuración y recopilación de datos]** > **[!UICONTROL Grupos de informes]** y haga clic en **[!UICONTROL Analizar]**.

   ![Lista de grupos de informes](assets/an_inv_rs.png)

   | Elemento | Descripción |
   | --- | --- |
   | Nombre | Nombre del grupo de informes |
   | ID | El ID del grupo de informes (rsid). Especifica un ID único que contiene solamente caracteres alfanuméricos. La ID no se puede cambiar una vez creada. Adobe establece el prefijo de ID necesario, que no se puede cambiar tampoco. |
   | Ocurrencias (últimos 90 días) | La métrica “Ocurrencias” muestra el número de visitas configurado o en las que persiste una variable. ¿Cuántas visitas recibió este grupo de informes en los últimos 90 días? |
   | Métricas | ¿Cuántas métricas se definen en este grupo de informes? |
   | Dimensiones | ¿Cuántas dimensiones se definen en este grupo de informes? |
   | Analytics for Target (A4T) habilitado | [Oculto de forma predeterminada] ¿Está habilitado este grupo de informes para [Analytics for Target](https://experienceleague.adobe.com/es/docs/target/using/integrate/a4t/a4t)? |
   | Canales de marketing habilitados | [Oculto de forma predeterminada] ¿Está habilitado este grupo de informes para [Canales de marketing](https://experienceleague.adobe.com/es/docs/analytics/components/marketing-channels/c-getting-started-mchannel)? |
   | Conector de Source activado | ¿Está habilitado este grupo de informes para [Adobe Analytics Source Connector para los datos del grupo de informes](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/adobe-applications/analytics) en Adobe Experience Platform? En otras palabras, ¿se puede migrar este grupo de informes a Customer Journey Analytics mediante el conector de Source de Analytics? |
   | Tipo de calendario | [Oculto de forma predeterminada] Para obtener más información, consulte [Calendarios personalizados](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/custom-calendar#) |

#### Analizar dimensiones

Esta pantalla proporciona una vista detallada de todas las dimensiones definidas para un grupo de informes específico. Desde esta vista, puede responder a las siguientes preguntas:

* ¿Qué dimensiones están habilitadas para este grupo de informes?
* ¿Cuáles son los diez elementos de dimensión principales de los últimos 90 días para esta dimensión?

1. Haga clic en el vínculo **[!UICONTROL Dimensiones]** en la página Grupo de informes.

   | Elemento | Descripción |
   | --- | --- |
   | Nombre | Nombre de la dimensión |
   | ID | El ID de dimensión. |
   | Tipo | El tipo de dimensión. Los valores posibles incluyen Conversión, Tráfico, Navegación, Fuentes de tráfico, Clientes, Fecha o dimensiones específicas del producto de Adobe como AEM, Audiencia, Adobe Campaign, Aplicación móvil, etc. |
   | Descripción | No todas las dimensiones tienen descripciones. |
   | Conector de Source activado | ¿Está habilitada esta dimensión para el [conector Source de Adobe Analytics para los datos del grupo de informes](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/adobe-applications/analytics) en Adobe Experience Platform? En otras palabras, ¿puede migrar esta dimensión a Customer Journey Analytics mediante el conector de Source de Analytics? |

1. Determine qué dimensiones tienen sentido para migrar a CJA.


#### Analizar métricas

Esta pantalla proporciona una vista detallada de todas las métricas definidas para un grupo de informes específico. Desde esta vista, puede responder a las siguientes preguntas:

* ¿Qué métricas están habilitadas para este grupo de informes?
* ¿Cuáles son las diez métricas principales de los últimos 90 días?

1. Haga clic en el vínculo **[!UICONTROL Métricas]** en la página Grupo de informes.


   | Elemento | Descripción |
   | --- | --- |
   | Nombre | Nombre de la métrica |
   | ID | El ID de métrica. |
   | Tipo | El tipo de métrica. Los valores posibles incluyen Conversión, Tráfico, Navegación, Fuentes de tráfico, Clientes, Fecha o dimensiones específicas del producto de Adobe como AEM, Audiencia, Adobe Campaign, Aplicación móvil, etc. |
   | Descripción | No todas las dimensiones tienen descripciones. |
   | Conector de Source activado | ¿Se ha habilitado esta métrica para el [conector Source de Adobe Analytics para los datos del grupo de informes](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/adobe-applications/analytics) en Adobe Experience Platform? En otras palabras, ¿puede migrar esta métrica a Customer Journey Analytics mediante el conector de Source de Analytics? |

1. Determine qué métricas tienen sentido para migrar a CJA.

### Exportar a CSV

1. Para exportar la lista de grupos de informes, dimensiones o métricas a un archivo .csv, haga clic en **[!UICONTROL Exportar a CSV]**.

1. El archivo .csv aparecerá en la carpeta Descargas.

1. Ábralo y guárdelo con una aplicación de hoja de cálculo en su dispositivo.

>[!NOTE]
>
>Los elementos y las columnas que se filtran no se exportan al archivo .csv.


### Filtrar, buscar, ordenar y navegar

* Puede buscar en la tabla.
* En el carril izquierdo, haga clic en el icono Filtro para filtrar por &quot;Tipo&quot;. O haga clic en **[!UICONTROL Ocultar filtro]**.
* Puede ordenar todas las columnas en orden ascendente/descendente (solo orden de columna única).
* Puede hacer clic en los elementos de la ruta de exploración para desplazarse a otra pantalla.

## Administración de usuarios {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="Administración de usuarios"
>abstract="En esta sección se muestra la cantidad de usuarios en su entorno de Adobe Analytics."

<!-- markdownlint-enable MD034 -->

La administración de usuarios estará disponible en una versión posterior del inventario de Analytics.

## Migración de componentes

Con [Migración de componentes](/help/admin/admin/component-migration/component-migration.md), los administradores de Adobe Analytics pueden migrar proyectos de Analytics y sus componentes asociados a Customer Journey Analytics.

El proceso de migración incluye:

* Creación de nuevo de los proyectos de Adobe Analytics en Customer Journey Analytics.

* Asignación de dimensiones y métricas de grupos de informes de Adobe Analytics a dimensiones y métricas en vistas de datos de Customer Journey Analytics.