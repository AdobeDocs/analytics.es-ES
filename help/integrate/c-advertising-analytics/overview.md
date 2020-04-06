---
description: nulo
title: Resumen de Advertising Analytics
uuid: 00e461ff-3e17-4071-818b-93fd1e4b36f1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Resumen de Advertising Analytics

Advertising Analytics le permite consultar todos los datos de búsqueda de pago de Google y Bing alineados en Adobe Analytics. Anteriormente, cualquier dato de Google AdWords/DFA o Microsoft Bing Ads tenía que visualizarse en Adobe Media Optimizer (AMO) o en Google/Bing. Ahora, obtendrá los datos siguientes en Adobe Analytics: impresiones, clics, costes, puntuación de calidad y posición media directamente de los motores de búsqueda, así como instancias de ID de AMO (instancias de clic).

>[!NOTE] El 31 de marzo de 2019, Microsoft Bing absorbió Yahoo Gemini. Como resultado, la opción de cuenta publicitaria de Yahoo Gemini ya no está disponible.

Al reunir los datos de estos motores de búsqueda en Adobe Analytics, puede analizar los mismos datos mediante el uso de la potencia de Análisis Workspace. A new [Paid Search Performance](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) template in Workspace facilitates this analysis.

![](assets/aa_aw.png)

Esta integración está dirigida a las siguientes audiencias:

* El **analista** que necesita recopilar informes de rendimiento para el especialista en mercadotecnia de búsqueda paga.
* El **especialista en mercadotecnia** de búsqueda paga que busca respuestas a estas preguntas: ¿Cuánto tráfico envío a nuestro sitio y qué conversión tienen los clientes? ¿Cuáles son mis campañas publicitarias rentables?

## Requisitos previos {#section_C25E0CA3474C4EDEAEAA9A5B8AAC9299}

* Advertising Analytics is available for Adobe Analytics [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html), and [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) SKUs only.

* Esta funcionalidad está disponible para los clientes que no sean de Advertising Cloud y los que no sean de AMO.
* Debe ser administrador de Adobe Analytics para tener acceso a Advertising Analytics. Posteriormente, puede [otorgar permisos](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) de acceso a usuarios que no sean administradores.
* Los grupos de informes de Analytics de los que desee consultar los datos de búsqueda de Google/Bing, deben [estar asignados a su organización de Experience Cloud](https://marketing.adobe.com/resources/help/es_ES/mcloud/report-suite-mapping.html).
* For any report suite where you want to view Google/Bing search data, you must [enable those report suite/s for Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**).

* Necesita credenciales de inicio de sesión para un usuario con permisos de edición en las cuentas de búsqueda que desea integrar con Adobe Analytics, como un ID de cuenta y una contraseña de Google.
* En el caso de los anuncios de Bing, también necesita el ID de cliente de Bing.
* If you use Internet Explorer 11 (or earlier), you will not be able to successfully [set up an advertising account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) for any of the three search engines. En su lugar, utilice otros exploradores web.

## Permisos de Advertising Analytics {#section_FCC58EB635954A32990D4E67B52B4369}

Analytics tiene dos permisos que se conceden automáticamente a los administradores de Analytics. A continuación, los administradores pueden optar por otorgar estos permisos a los no administradores.

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
   <td colname="col2"> <p>Permite a los usuarios configurar/editar/vista cuentas de búsqueda de publicidad. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Administración</span> &gt; <span class="uicontrol">Administración de usuarios</span> &gt; <span class="uicontrol">Grupos</span> &gt; <span class="uicontrol">Editar acceso a todos los informes</span> &gt; <span class="uicontrol">Personalizar herramientas de Analytics</span> &gt; <span class="uicontrol">Administración de Advertising Analytics</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Inicio de sesión en adminconsole.adobe.com</span> &gt; <span class="uicontrol">Productos</span> &gt; <span class="uicontrol">Perfil del producto</span> &gt; <span class="uicontrol">Pestaña Permisos</span> &gt; <span class="uicontrol">Herramientas de Analytics</span> &gt; <span class="uicontrol">Administración de Advertising Analytics</span></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configuración de Advertising Analytics </p> </td> 
   <td colname="col2"> <p>Permite a los usuarios configurar grupos de informes para aprovisionarlos en Análisis de publicidad. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Administración</span> &gt; <span class="uicontrol">Administración de usuarios</span> &gt; <span class="uicontrol">Grupos</span> &gt; <span class="uicontrol">Editar acceso a todos los informes</span> &gt; <span class="uicontrol">Personalizar herramientas de grupos de informes</span> &gt; <span class="uicontrol">Configuración de Advertising Analytics</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Inicio de sesión en adminconsole.adobe.com</span> &gt; <span class="uicontrol">Productos</span> &gt; <span class="uicontrol">Perfil del producto</span> &gt; <span class="uicontrol">Pestaña Permisos</span> &gt; <span class="uicontrol">Herramientas de grupos de informes</span> &gt; <span class="uicontrol">Configuración de Advertising Analytics</span></span> </td> 
  </tr> 
 </tbody> 
</table>

## Dimensiones y métricas de Advertising Analytics {#section_C0DF4A08EA9E46ADABE9E465AFC11E32}

Advertising Analytics agrega las siguientes dimensiones y métricas a Espacio de trabajo de Análisis, Informes y análisis, Creador de informes y la API de Sistema de informes de Analytics.

**Dimensiones**

>[!IMPORTANT]
>
>Esta integración crea un nuevo conjunto de dimensiones a través de las clasificaciones de la variable de ID de AMO. Estas nuevas dimensiones no afectan ni modifican las dimensiones de las variables de seguimiento de campañas o canales de marketing existentes. El ID de AMO está conectado al perfil de un visitante cuando un visitante aterriza en el sitio desde un anuncio de búsqueda paga. Por lo tanto, las dimensiones AMO pueden utilizarse para desglosar tanto las métricas AMO proporcionadas por esta integración como cualquier dato capturado por el visitante (visitas, visitantes, vistas de página, tasa de devoluciones, pedidos, ingresos, eventos personalizados, etc.). También se pueden desglosar según otras dimensiones cuando el sistema de informes se realiza en otras métricas en el sitio.
>
>Las clasificaciones de estas métricas se actualizan diariamente. Por lo tanto, si realiza cambios en los metadatos de un motor de búsqueda, es posible que no vea que dichos cambios se reflejen hasta el día siguiente, cuando se actualicen las clasificaciones.

| Nombre de clasificación (dimensión) | Definición |
|--- |--- |
| Tipo de coincidencia de palabra clave (ID de AMO) | Tipo de coincidencia de palabra clave. Los valores suelen ser amplios, de frase, exactos o sin valor si el tipo de publicidad no tiene un tipo de coincidencia. |
| Plataforma de publicidad (ID de AMO) | El nombre del motor de búsqueda. Los valores pueden incluir Google AdWords o Microsoft Bing Ads. |
| Cuenta (ID de AMO) | Nombre de la cuenta del motor de búsqueda que se está rastreando. |
| Campaña (ID de AMO) | El nombre de la campaña en la cuenta del motor de búsqueda. |
| Grupo de publicidad (ID de AMO) | Nombre del grupo de publicidad en las campañas del motor de búsqueda. |
| Anuncio (ID de AMO) | Título y descripción del anuncio que se usan en el anuncio. |
| Palabra clave (ID de AMO) | Valor de palabra clave de la cuenta de motor de búsqueda |
| Tipo de coincidencia (ID de AMO) | Se trata del tipo de coincidencia de palabra clave asignado a su palabra clave. Los valores suelen ser “amplio”, “frase”, “exacto” o “sin valor” si el tipo de anuncio no tiene ningún tipo de coincidencia. |
| Tipo de anuncio (ID de AMO) | Tipo de anuncio publicado, que suele ser “Anuncio de texto”. |
| Título de anuncio (ID de AMO) | Objeto de título usado en el anuncio. |
| Descripción de anuncio (ID de AMO) | Objeto de la descripción del anuncio usado en el anuncio. |
| URL mostrada de anuncio (ID de AMO) | Objeto de URL de visualización de anuncio usado en el anuncio. |
| URL de destino de anuncio (ID de AMO) | URL de la página de aterrizaje o URL final asignada al anuncio. |
| Red (ID de AMO) | Red en la que se está ofreciendo la publicidad. Para Advertising Analytics, este valor es siempre “Búsqueda”. |
| Ubicación (ID de AMO) | Sitio web de colocación gestionada (para redes de contenido). Solo las colocaciones gestionadas usan esta dimensión. |
| Segmentación de productos (ID de AMO) | Nombre del segmento del producto usado en los anuncios PLA (no es el producto real comprado). |
| Optimización (ID de AMO) | Analytics no lo usa. Solo lo utilizan los clientes de Advertising Cloud. |
| Dispositivo (ID de AMO) | No se usa hoy. Marcador de posición para la posible mejora futura del producto en el tipo de dispositivo de destinatario indicado (por ejemplo, móvil o de escritorio) del anuncio (no el dispositivo de visitante real). |

**Métricas**

>[!IMPORTANT]
>
>Las métricas que proporciona Advertising Analytics (enumeradas más abajo) son datos de resumen de los motores de búsqueda. No están conectados a los perfiles de visitante de Analytics. Solo están conectadas a la variable de ID de AMO y a sus dimensiones de clasificación asociadas. Como tal, no se debe realizar ningún informe de ellas según ninguna dimensión ni ningún segmento que no sean los basados en las dimensiones de ID de AMO. Al hacerlo, Analytics mostrará ceros para los datos. Puede incluirlas en métricas calculadas con otras métricas, pero estas métricas calculadas también deben desglosarse únicamente por las dimensiones de ID de AMO.
>
>Estas métricas son datos que se originan diariamente, por lo que no tendrán datos para el día actual. Tampoco deben notificarse con una granularidad inferior a la diaria.
>
>Existe una métrica denominada Instancias de ID de AMO que se define cuando el ID de AMO se establece en una página de aterrizaje (es decir, un clic). Esta métrica se captura en tiempo real con la visita de página de aterrizaje y está disponible para desgloses con otras dimensiones también definidas en la página de aterrizaje.

| Nombre de la métrica | Definición |
|--- |--- |
| AMO Impresiones | Número de impresiones de publicidad según el motor de búsqueda. |
| AMO Clics | Cantidad de clics en publicidades según los informes del motor de búsqueda. |
| AMO Coste | Costo pagado por cada palabra clave/publicidad según lo informado por el motor de búsqueda. |
| Pos. med. | Métrica calculada que refleja la posición promedio de las publicidades según lo informado por el motor de búsqueda. |
| Promedio de Puntuación de calidad | Una métrica calculada que refleja la puntuación de calidad promedio según lo informado por el motor de búsqueda. |
