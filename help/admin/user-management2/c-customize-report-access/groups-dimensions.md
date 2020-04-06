---
description: Personalice el acceso de usuarios a nivel granular con eVars, informes de tráfico, informes de soluciones e informes de rutas.
keywords: groups;permissions
subtopic: Users and groups
title: Personalizar permisos para dimensiones
topic: Admin tools
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Personalizar permisos para dimensiones

>[!IMPORTANT] La administración de usuarios y productos se va a trasladar a [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Adobe le avisará cuando deba migrar a sus usuarios. After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** will be retired.

Personalice el acceso de usuarios a nivel granular con eVars, informes de tráfico, informes de soluciones e informes de rutas.

**[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL Report Access]** > **[!UICONTROL Dimensions]** > **[!UICONTROL Customize]**

>[!IMPORTANT] Algunas dimensiones no pueden recibir permisos en este momento. Estas dimensiones son: Longitud del marcador móvil; Número de dispositivo móvil; DRM móvil; Servicios informativos móviles; Java VM móvil; Decoración de correo móvil; Protocolos de red móvil; Mobile OS; Pulsa para hablar móvil.
>
>Estas dimensiones están disponibles para todos los usuarios, independientemente de los demás permisos.

La configuración de esta página corresponde a los grupos de informes seleccionados en la [!UICONTROL Define User Groups] página.

![](assets/permissions-dimensions.png)

Obtenga la siguiente información sobre la categoría de permisos de dimensión.

* Las eVars 1-250 tienen permisos individuales.
* Todos los informes de tráfico son dimensiones.
* Los informes de Vídeo y Móvil son dimensiones, al igual que otros informes de soluciones de Analytics (Experience Manager, Advertising Cloud, Social, etc.).
* Los informes de rutas están disponibles si un usuario tiene acceso a la dimensión principal.
* Todas las dimensiones y métricas actuales de los grupos personalizados se han migrado automáticamente a las nuevas categorías. Si un grupo existente tiene métricas habilitadas, se le asignarán todas las dimensiones con permisos nuevos (eVars y reconocimiento de contenido) y métricas de forma predeterminada.
* Permisos del Importador de clasificaciones (anteriormente, SAINT): el acceso a las clasificaciones viene determinado por el acceso a la [variable](https://marketing.adobe.com/resources/help/es_ES/reference/c_classifications.html) en la cual se basa la clasificación.

Para obtener más información, consulte Preguntas [más frecuentes sobre los cambios](https://marketing.adobe.com/resources/help/es_ES/reference/index.html?f=permissions_faq)de permisos.

**Personalizar dimensiones**

Los siguientes elementos son dimensiones para las que puede obtener permisos.

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/admin/admin/conversion-var-admin/conversion-var-admin.md"> eVars </a> </p> </td> 
   <td colname="col2"> <p>Las eVars 1-250 tienen permisos individuales. Las eVars son variables de conversión personalizadas que se utilizan para segmentar las métricas de éxito de conversión en los informes personalizados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/es_ES/sc/implement/props_eVars.html"> Propriétés </a> </p> </td> 
   <td colname="col2"> <p>Las props son variables de tráfico personalizadas. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/es_ES/sc/implement/props_eVars.html">Props de tráfico y eVars de conversión</a> en Implementación de Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/es_ES/sc/implement/hierN.html"> Jerarquía </a> </p> </td> 
   <td colname="col2"> <p> La variable de jerarquía (hierN) determina la ubicación de una página en la jerarquía del sitio o en la estructura de páginas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/es_ES/sc/implement/listN.html"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> De forma similar a como funcionan las propiedades de Lista, las variables de lista permiten varios valores dentro de la misma solicitud de imagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Estándar </p> </td> 
   <td colname="col2"> <p>Hace referencia a dimensiones dimensiones (integradas) en Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/em/"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/media-optimizer/"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/es_ES/analytics/activitymap/"> Página de </a> </p> </td> 
   <td colname="col2"> <p> Dimensiones de los informes de Activity Map: Página de Activity Map; Vínculo de Activity Map; Región de Activity Map; Vínculo de Activity Map por región; Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/es_ES/mobile/"> Mobile </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>Esta integración de partners ya no está activa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/es-ES/media-analytics/using/media-overview.html"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>Esta integración de partners ya no está activa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>No se usa. </p> </td> 
  </tr> 
 </tbody> 
</table>
