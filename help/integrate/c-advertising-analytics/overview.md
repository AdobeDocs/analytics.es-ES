---
description: Descubra todo lo que puede hacer con Advertising Analytics, incluidos los permisos requeridos, y las dimensiones y métricas disponibles.
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 70%

---

# Advertising Analytics

Advertising Analytics le permite ver todos los datos de búsqueda de pago de Google Ads y Microsoft Advertising alineados en Adobe Analytics. Anteriormente, cualquier dato de Google Ads o Microsoft Advertising tenía que visualizarse en Adobe Advertising Cloud (AMO) o en cada interfaz de publicidad correspondiente. Ahora puede obtener datos de impresiones, clics y costes directamente de los motores de búsqueda, así como instancias de ID de AMO (instancias de clic).

Al unir los datos de estos motores de búsqueda en Adobe Analytics, puede analizarlos mediante la potencia de Analysis Workspace. Una nueva plantilla [Rendimiento de búsqueda de pago](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) en Workspace facilita este análisis.

![](assets/aa_aw.png)

Esta integración va dirigida a los públicos siguientes:

* El **analista** que debe recopilar informes de rendimiento para el comercializador de búsqueda de pago.
* El **comercializador de búsqueda de pago** que busca respuestas a estas preguntas: ¿Cuánto tráfico estoy enviando a nuestro sitio web y qué proporción de ese tráfico están convirtiendo los clientes? ¿Cuáles son mis campañas publicitarias rentables?


## Requisitos previos {#prerequisites}

* Advertising Analytics está disponible únicamente para los SKU [Select](https://www.adobe.com/es/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/es/data-analytics-cloud/analytics/prime.html) y [Ultimate](https://www.adobe.com/es/data-analytics-cloud/analytics/ultimate.html) de Adobe Analytics.
* Esta funcionalidad está disponible para clientes que no sean de Advertising Cloud ni de AMO.
* Debe ser administrador de Adobe Analytics para tener acceso a Advertising Analytics o pertenecer a un perfil de producto al que se le haya [concedido acceso](/help/integrate/c-advertising-analytics/overview.md#permissions) a Advertising Analytics.
* Para los grupos de informes de los que desee consultar los datos de búsqueda de Google Ads o Microsoft Advertising, debe [habilitar dichos grupos de informes para Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Administrador]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Configuración de Advertising Analytics]**).
* Necesita credenciales de inicio de sesión para un usuario con permisos de edición en las cuentas de búsqueda que desee integrar en Adobe Analytics, como un identificador de cuenta de Google y una contraseña.
* En el caso de Microsoft Advertising, también necesita el [[!UICONTROL identificador de cuenta] y el [!UICONTROL identificador de cuenta del administrador]](c-adanalytics-workflow/aa-locate-account-id.md).

## Permisos de Advertising Analytics {#permissions}

Analytics tiene dos permisos que se conceden automáticamente a los administradores de Analytics. Los administradores tienen la opción de conceder estos permisos a los usuarios que no sean administradores.

| Permiso | Definición | Conceder permiso si ha iniciado sesión en Adobe Experience Cloud |
| --- | --- | --- |
| Administración de Advertising Analytics | Permite a los usuarios configurar/editar/visualizar las cuentas de búsqueda publicitarias. | Inicie sesión en [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Productos] > [!UICONTROL Adobe Analytics] > [!UICONTROL Perfil del producto] > [!UICONTROL Permisos] pestaña > [!UICONTROL Herramientas de Analytics] > [!UICONTROL Administración de Advertising Analytics] |
| Configuración de Advertising Analytics | Permite a los usuarios configurar los grupos de informes que se van a aprovisionar para Advertising Analytics. | Inicie sesión en [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Productos] > [!UICONTROL Adobe Analytics] > [!UICONTROL Perfil del producto] > [!UICONTROL Permisos] pestaña > [!UICONTROL Herramientas de Analytics] > [!UICONTROL Configuración de Advertising Analytics] |

## Dimensiones y métricas de Advertising Analytics {#dimensions-metrics}

Advertising Analytics agrega las siguientes dimensiones y métricas a Analysis Workspace, Report Builder y la API de informes de Analytics.

### Dimensiones

>[!IMPORTANT]
>
>Esta integración crea un nuevo conjunto de dimensiones a través de las clasificaciones de la variable de ID de AMO. Estas dimensiones nuevas no afectan a los canales de marketing existentes ni a las dimensiones de la variable de seguimiento de campañas ni los modifican. El identificador de AMO está conectado al perfil de un visitante cuando dicho visitante aterriza en el sitio web desde un anuncio de búsqueda de pago. Como tal, las dimensiones de AMO se pueden utilizar para desglosar las métricas de AMO que proporciona esta integración, así como los datos que el visitante haya capturado del sitio web (visitas, visitantes, visualizaciones de páginas, tasa de rebotes, pedidos, ingresos, eventos personalizados, etc.). También se pueden desglosar por otras dimensiones al informar sobre otras métricas en el sitio.
>
>Las clasificaciones de estas métricas se actualizan a diario. Así pues, si realiza cambios en los metadatos en un motor de búsqueda, es posible que dichos cambios no se reflejen hasta el día siguiente cuando se actualicen las clasificaciones.

| Nombre de la clasificación (dimensión) | Definición |
| --- | --- |
| **[!UICONTROL Tipo de coincidencia de palabra clave (ID de AMO)]** | El tipo de coincidencia de palabra clave. Por lo general, los valores serán amplia, frase, exacta o sin valor si el tipo de anuncio no tiene ningún tipo de coincidencia. |
| **[!UICONTROL Plataforma de publicidad (ID de AMO)]** | El nombre del motor de búsqueda. Los valores pueden incluir &quot;Google AdWords&quot; o &quot;Microsoft Bing Ads&quot;. |
| **[!UICONTROL Cuenta (ID de AMO)]** | El nombre de la cuenta de motor de búsqueda de la que se está realizando un seguimiento. |
| **[!UICONTROL Campaña (ID de AMO)]** | El nombre de la campaña en la cuenta de motor de búsqueda. |
| **[!UICONTROL Grupo de publicidad (ID de AMO)]** | El nombre del grupo de publicidad en las campañas de motor de búsqueda. |
| **[!UICONTROL Anuncio (ID de AMO)]** | El Título de anuncio + Descripción de anuncio que se utilizan en su anuncio. |
| **[!UICONTROL Palabra clave (ID de AMO)]** | El valor Palabra clave de su cuenta de motor de búsqueda. |
| **[!UICONTROL Tipo de coincidencia (ID de AMO)]** | El tipo de coincidencia de palabra clave asignado a su palabra clave. Por lo general, los valores serán amplia, frase, exacta o sin valor si el tipo de anuncio no tiene ningún tipo de coincidencia. |
| **[!UICONTROL Tipo de anuncio (ID de AMO)]** | Tipo de anuncio publicado, que suele ser “Anuncio de texto”. |
| **[!UICONTROL Título de anuncio (ID de AMO)]** | El objeto Título que se utiliza en su anuncio. |
| **[!UICONTROL Descripción de anuncio (ID de AMO)]** | El objeto Descripción de anuncio que se utiliza en su anuncio. |
| **[!UICONTROL URL para mostrar el anuncio (ID de AMO)]** | El objeto URL mostrada de anuncio que se utiliza en su anuncio. |
| **[!UICONTROL URL de destino de anuncio (ID de AMO)]** | La URL de la página de destino o la URL final asignada a su anuncio. |
| **[!UICONTROL Red (ID de AMO)]** | La red en la que se publica su anuncio. Para Advertising Analytics, este valor es siempre “Búsqueda”. |
| **[!UICONTROL Ubicación (ID de AMO)]** | El sitio web de colocación gestionada (para las redes de contenido). Solo las colocaciones gestionadas utilizan esta dimensión. |
| **[!UICONTROL Segmentación de productos (ID de AMO)]** | El nombre del segmento de producto utilizado en los anuncios PLA (no el producto comprado en sí). |
| **[!UICONTROL Optimización (ID de AMO)]** | No se utiliza en Advertising Analytics. Solo lo utilizan los clientes de Advertising Cloud. |
| **[!UICONTROL Dispositivo (ID de AMO)]** | No se utiliza hoy en día. Marcador de posición para posibles mejoras futuras en los tipos de dispositivo de destino indicados (p. ej., móvil, escritorio) del anuncio (no el dispositivo en sí del visitante). |

### Métricas

>[!IMPORTANT]
>
>Las métricas que proporciona Advertising Analytics (enumeradas más abajo) son datos de resumen de los motores de búsqueda. No están conectadas a los perfiles de visitante de Analytics. Solo están conectadas a la variable de ID de AMO y a sus dimensiones de clasificación asociadas. Como tal, no se debe realizar ningún informe de ellas según ninguna dimensión ni ningún segmento que no sean los basados en las dimensiones de ID de AMO. En caso de hacerlo, Analytics mostrará los datos como ceros. Puede incluirlas en métricas calculadas con otras métricas, pero estas métricas calculadas también deben desglosarse únicamente por las dimensiones de ID de AMO.
>
>Estas métricas son datos que se obtienen a diario, de manera que no tendrán datos correspondientes al día en curso. Tampoco se deben hacer informes de ellas con una granularidad inferior a diario.
>
>Existe una métrica denominada Instancias de ID de AMO que se define cuando el ID de AMO se establece en una página de aterrizaje (es decir, un clic). Esta métrica se captura en tiempo real junto con el acceso a la página de aterrizaje y está disponible para el desglose con otras dimensiones establecidas también en la página de aterrizaje.

| Nombre de la métrica | Definición |
| --- | --- |
| **[!UICONTROL Impresiones de AMO]** | El número de impresiones de un anuncio según la información del motor de búsqueda. |
| **[!UICONTROL Clics de AMO]** | El número de clics en anuncios según la información del motor de búsqueda. |
| **[!UICONTROL Costo de AMO]** | El coste pagado por cada palabra clave o anuncio según la información del motor de búsqueda. |
