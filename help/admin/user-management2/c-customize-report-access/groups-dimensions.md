---
description: Personalice el acceso de usuarios a nivel granular con eVars, informes de tráfico, informes de soluciones e informes de rutas.
keywords: grupos; permisos
seo-description: Personalice el acceso de usuarios a nivel granular con eVars, informes de tráfico, informes de soluciones e informes de rutas.
seo-title: Personalizar permisos de dimensiones
solution: Analytics
subtopic: Usuarios y grupos
title: Personalizar permisos de dimensiones
topic: Herramientas de administración
uuid: aaf 164 ad -3863-4129-864 e -39 ec 71 c 6 a 8 eb
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Personalizar permisos de dimensiones

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe le avisará cuando deba migrar a sus usuarios. After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** will be retired.

Personalice el acceso de usuarios a nivel granular con eVars, informes de tráfico, informes de soluciones e informes de rutas.

**[!UICONTROL Administración]** de usuarios &gt; **[!UICONTROL Grupos]** &gt; **[!UICONTROL Acceso a informes]** &gt; **[!UICONTROL Dimensiones]** &gt; **[!UICONTROL Personalizar]**

>[!IMPORTANT]
>
>En este momento, algunas dimensiones no pueden autorizarse. Estas dimensiones son: Longitud del marcador móvil, Número del dispositivo móvil, DRM móvil, Servicios de información móvil, Máquina virtual Java móvil, Decoración de correo móvil, Protocolos de red móvil, Sistema operativo móvil, Pulsar para hablar móvil.
>
>Estas dimensiones están disponibles para todos los usuarios, independientemente de otros permisos.

Las opciones de esta página pertenecen a los grupos de informes seleccionados en la página [!UICONTROL Definir grupos de usuarios].

![](assets/permissions-dimensions.png)

Conozca la información que sigue sobre la categoría de permisos Dimensión.

* Las eVars 1 a 250 obtienen permisos de forma individual.
* Todos los informes de tráfico son dimensiones.
* Los informes de vídeo y móviles son dimensiones, así como otros informes de soluciones de Analytics (Experience Manager, Advertising Cloud, Social, etc.).
* Los informes de rutas están disponibles si un usuario tiene acceso a la dimensión primaria.
* Se han migrado automáticamente a las nuevas categorías todas las dimensiones y métricas actuales dentro de grupos personalizados. Si un grupo existente tiene métricas habilitadas, se le asignarán todas las dimensiones que puedan recibir permisos por primera vez (eVars y según el contenido) y métricas de forma predeterminada.
* Permisos del Importador de clasificaciones (anteriormente, SAINT): el acceso a las clasificaciones viene determinado por el acceso a la [variable](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html) en la cual se basa la clasificación.

Para obtener más información, consulte [Preguntas más frecuentes sobre cambios de permisos](https://marketing.adobe.com/resources/help/en_US/reference/permissions_faq.html).

**Personalizar dimensiones**

Los elementos que siguen son dimensiones para las cuales se pueden asignar permisos.

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="../../../admin/admin/conversion-var-admin/conversion-var-admin.md#concept_C02F7AA01DE242F1AA1A4E74022BE9DE" format="dita" scope="local"> eVars </a> </p> </td> 
   <td colname="col2"> <p>Las eVars 1 a 250 obtienen permisos de forma individual. Las eVars son variables de conversión personalizadas que se emplean para segmentar las métricas de éxito de conversión de segmentos en los informes personalizados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external"> Props </a> </p> </td> 
   <td colname="col2"> <p>Las props son variables de tráfico personalizadas. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external">Props de tráfico y eVars de conversión</a> en Implementación de Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/hierN.html" format="html" scope="external"> Jerarquía </a> </p> </td> 
   <td colname="col2"> <p> La variable de jerarquía (hierN) determina la ubicación de una página en la jerarquía del sitio o en la estructura de páginas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html" format="html" scope="external"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> Similar a cómo funcionan las props de lista, las variables de lista permiten incluir varios valores dentro de la misma solicitud de imagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> </td> 
   <td colname="col2"> <p>Hace referencia a dimensiones (predeterminado) de Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/em/" format="https" scope="external"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/media-optimizer/" format="https" scope="external"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/" format="https" scope="external"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Dimensiones de los informes de Activity Map: Página de Activity Map; Vínculo de Activity Map; Región de Activity Map; Vínculo de Activity Map por región; Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/" format="https" scope="external"> Mobile </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>Esta integración de partners ya no está activa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html" format="html" scope="external"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>Integraciones de socios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>No se usa. </p> </td> 
  </tr> 
 </tbody> 
</table>

