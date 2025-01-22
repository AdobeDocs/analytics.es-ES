---
description: Descubra todo lo que puede hacer con Advertising Analytics, incluidos los permisos requeridos, y las dimensiones y métricas disponibles.
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
source-git-commit: 2244dbb3376c78b9d4a8b476b667ccef59db84f4
workflow-type: tm+mt
source-wordcount: '1138'
ht-degree: 93%

---

# Advertising Analytics

Advertising Analytics le permite consultar todos los datos de búsqueda de pago de Google y Bing alineados en Adobe Analytics. Anteriormente, cualquier dato de Google AdWords/DFA o Microsoft Bing Ads tenía que visualizarse en Adobe Advertising Cloud (AMO) o en Google/Bing. Ahora puede obtener los datos siguientes en Adobe Analytics: impresiones, clics, costes directamente de los motores de búsqueda, así como instancias de ID de AMO (instancias de clic).

Al unir los datos de estos motores de búsqueda en Adobe Analytics, puede analizarlos mediante la potencia de Analysis Workspace. Una nueva plantilla [Rendimiento de búsqueda de pago](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) en Workspace facilita este análisis.

![](assets/aa_aw.png)

Esta integración va dirigida a los públicos siguientes:

* El **analista** que debe recopilar informes de rendimiento para el comercializador de búsqueda de pago.
* El **comercializador de búsqueda de pago** que busca respuestas a estas preguntas: ¿Cuánto tráfico estoy enviando a nuestro sitio web y qué proporción de ese tráfico están convirtiendo los clientes? ¿Cuáles son mis campañas publicitarias rentables?

## Vídeo

>[!VIDEO](https://video.tv.adobe.com/v/23119?quality=12&learn=on)


## Requisitos previos {#prerequisites}

* Advertising Analytics está disponible únicamente para los SKU [Select](https://www.adobe.com/es/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/es/data-analytics-cloud/analytics/prime.html) y [Ultimate](https://www.adobe.com/es/data-analytics-cloud/analytics/ultimate.html) de Adobe Analytics.
* Esta funcionalidad está disponible para clientes que no sean de Advertising Cloud ni de AMO.
* Para tener acceso a Advertising Analytics, debe ser administrador de Adobe Analytics. Posteriormente, puede [conceder permisos de acceso](/help/integrate/c-advertising-analytics/overview.md#permissions) a los usuarios que no sean administradores.
* Para los grupos de informes de los que desee consultar los datos de búsqueda de Google/Bing, [habilite dichos grupos de informes para Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md). Puede hacerlo en **[!UICONTROL Administración]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Configuración de Advertising Analytics]**.
* Necesita credenciales de inicio de sesión para un usuario con permisos de edición en las cuentas de búsqueda que desee integrar en Adobe Analytics, como un identificador de cuenta de Google y una contraseña.
* En el caso de Bing Ads, también necesita el identificador de cliente de Bing.

## Permisos de Advertising Analytics {#permissions}

Analytics cuenta con dos permisos que se conceden automáticamente a los administradores de Analytics. Los administradores tienen la opción de conceder estos permisos a los usuarios que no sean administradores.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Permiso </th> 
   <th colname="col2" class="entry"> Definición </th> 
   <th colname="col3" class="entry"> Conceder permiso en Adobe Analytics </th> 
   <th colname="col4" class="entry"> Conceder permiso si ha iniciado sesión en Adobe Experience Cloud </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Administración de Advertising Analytics </p> </td> 
   <td colname="col2"> <p>Permite a los usuarios configurar/editar/visualizar las cuentas de búsqueda publicitarias. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol">Administración</span> &gt; <span class="uicontrol">Todos los administradores</span> &gt; <span class="uicontrol">Administración de usuarios</span> &gt; <span class="uicontrol">Grupos</span> &gt; <span class="uicontrol">Editar acceso a todos los informes</span> &gt; <span class="uicontrol">Personalizar herramientas de Analytics</span> &gt; <span class="uicontrol">Administración de Advertising Analytics</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Inicio de sesión en adminconsole.adobe.com</span> &gt; <span class="uicontrol">Productos</span> &gt; <span class="uicontrol">Perfil del producto</span> &gt; <span class="uicontrol">Pestaña Permisos</span> &gt; <span class="uicontrol">Herramientas de Analytics</span> &gt; <span class="uicontrol">Administración de Advertising Analytics</span></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configuración de Advertising Analytics </p> </td> 
   <td colname="col2"> <p>Permite a los usuarios configurar los grupos de informes que se van a aprovisionar para Advertising Analytics. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol">Administración</span> &gt; <span class="uicontrol"></span> &gt; <span class="uicontrol">Administración de usuarios</span> &gt; <span class="uicontrol">Grupos</span> &gt; <span class="uicontrol">Editar acceso a todos los informes</span> &gt; <span class="uicontrol">Personalizar herramientas de grupos de informes</span> &gt; <span class="uicontrol">Configuración de Advertising Analytics</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Inicio de sesión en adminconsole.adobe.com</span> &gt; <span class="uicontrol">Productos</span> &gt; <span class="uicontrol">Perfil del producto</span> &gt; <span class="uicontrol">Pestaña Permisos</span> &gt; <span class="uicontrol">Herramientas de grupos de informes</span> &gt; <span class="uicontrol">Configuración de Advertising Analytics</span></span> </td> 
  </tr> 
 </tbody> 
</table>

## Dimensiones y métricas de Advertising Analytics {#dimensions-metrics}

Advertising Analytics agrega las siguientes dimensiones y métricas a Analysis Workspace, Report Builder y la API de informes de Analytics.

### Dimensiones

>[!IMPORTANT]
>
>Esta integración crea un nuevo conjunto de dimensiones a través de las clasificaciones de la variable de ID de AMO. Estas dimensiones nuevas no afectan a los canales de marketing existentes ni a las dimensiones de la variable de seguimiento de campañas ni los modifican. El identificador de AMO está conectado al perfil de un visitante cuando dicho visitante aterriza en el sitio web desde un anuncio de búsqueda de pago. Como tal, las dimensiones de AMO se pueden utilizar para desglosar las métricas de AMO que proporciona esta integración, así como los datos que el visitante haya capturado del sitio web (visitas, visitantes, visualizaciones de páginas, tasa de rebotes, pedidos, ingresos, eventos personalizados, etc.). También se pueden desglosar por otras dimensiones al informar sobre otras métricas en el sitio.
>
>Las clasificaciones de estas métricas se actualizan a diario. Así pues, si realiza cambios en los metadatos en un motor de búsqueda, es posible que dichos cambios no se reflejen hasta el día siguiente cuando se actualicen las clasificaciones.

| Nombre de la clasificación (dimensión) | Definición |
|--- |--- |
| Tipo de coincidencia de palabra clave (ID de AMO) | El tipo de coincidencia de palabra clave. Por lo general, los valores serán amplia, frase, exacta o sin valor si el tipo de anuncio no tiene ningún tipo de coincidencia. |
| Plataforma de publicidad (ID de AMO) | El nombre del motor de búsqueda. Los valores pueden incluir Google AdWords o Microsoft Bing Ads. |
| Cuenta (ID de AMO) | El nombre de la cuenta de motor de búsqueda de la que se está realizando un seguimiento. |
| Campaña (ID de AMO) | El nombre de la campaña en la cuenta de motor de búsqueda. |
| Grupo de publicidad (ID de AMO) | El nombre del grupo de publicidad en las campañas de motor de búsqueda. |
| Anuncio (ID de AMO) | El Título de anuncio + Descripción de anuncio que se utilizan en su anuncio. |
| Palabra clave (ID de AMO) | El valor de palabra clave de su cuenta de motor de búsqueda. |
| Tipo de coincidencia (ID de AMO) | El tipo de coincidencia de palabra clave asignado a su palabra clave. Por lo general, los valores serán amplia, frase, exacta o sin valor si el tipo de anuncio no tiene ningún tipo de coincidencia. |
| Tipo de anuncio (ID de AMO) | Tipo de anuncio publicado, que suele ser “Anuncio de texto”. |
| Título de anuncio (ID de AMO) | El objeto Título que se utiliza en su anuncio. |
| Descripción de anuncio (ID de AMO) | El objeto Descripción de anuncio que se utiliza en su anuncio. |
| URL mostrada de anuncio (ID de AMO) | El objeto URL mostrada de anuncio que se utiliza en su anuncio. |
| URL de destino de anuncio (ID de AMO) | La URL de la página de destino o la URL final asignada a su anuncio. |
| Red (ID de AMO) | La red en la que se publica su anuncio. Para Advertising Analytics, este valor es siempre “Búsqueda”. |
| Ubicación (ID de AMO) | El sitio web de colocación gestionada (para las redes de contenido). Solo las colocaciones gestionadas utilizan esta dimensión. |
| Segmentación de productos (ID de AMO) | El nombre del segmento de producto utilizado en los anuncios PLA (no el producto comprado en sí). |
| Optimización (ID de AMO) | No se utiliza en Advertising Analytics. Solo lo utilizan los clientes de Advertising Cloud. |
| Dispositivo (ID de AMO) | No se utiliza hoy en día. Marcador de posición para posibles mejoras futuras en los tipos de dispositivo de destino indicados (p. ej., móvil, escritorio) del anuncio (no el dispositivo en sí del visitante). |

### Métricas

>[!IMPORTANT]
>
>Las métricas que proporciona Advertising Analytics (enumeradas más abajo) son datos de resumen de los motores de búsqueda. No están conectadas a los perfiles de visitante de Analytics. Solo están conectadas a la variable de ID de AMO y a sus dimensiones de clasificación asociadas. Como tal, no se debe realizar ningún informe de ellas según ninguna dimensión ni ningún segmento que no sean los basados en las dimensiones de ID de AMO. En caso de hacerlo, Analytics mostrará los datos como ceros. Puede incluirlas en métricas calculadas con otras métricas, pero estas métricas calculadas también deben desglosarse únicamente por las dimensiones de ID de AMO.
>
>Estas métricas son datos que se obtienen a diario, de manera que no tendrán datos correspondientes al día en curso. Tampoco se deben hacer informes de ellas con una granularidad inferior a diario.
>
>Existe una métrica denominada Instancias de ID de AMO que se define cuando el ID de AMO se establece en una página de aterrizaje (es decir, un clic). Esta métrica se captura en tiempo real junto con el acceso a la página de aterrizaje y está disponible para el desglose con otras dimensiones establecidas también en la página de aterrizaje.

| Nombre de la métrica | Definición |
|--- |--- |
| Impresiones de AMO | El número de impresiones de un anuncio según la información del motor de búsqueda. |
| Clics de AMO | El número de clics en anuncios según la información del motor de búsqueda. |
| Coste de AMO | El coste pagado por cada palabra clave o anuncio según la información del motor de búsqueda. |
