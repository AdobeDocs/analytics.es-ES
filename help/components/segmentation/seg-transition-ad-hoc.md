---
description: Si está habituado a trabajar con el Generador de segmentos en Ad Hoc Analysis, esta lista de preguntas más frecuentes le explica qué sucede con los segmentos y las carpetas existentes y qué acciones debe realizar.
keywords: segmentation;segments
title: Guía de transición para Ad Hoc Analysis
topic: Segments
uuid: d409d71a-f8d9-42a2-add2-37d426cd40d1
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 100%

---


# Guía de transición para Ad Hoc Analysis

Si está habituado a trabajar con el Generador de segmentos en Ad Hoc Analysis, esta lista de preguntas más frecuentes le explica qué sucede con los segmentos y las carpetas existentes y qué acciones debe realizar.

## Funciones  {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* Los segmentos son universales para todos los grupos de informes. Antes, los segmentos eran específicos de cada grupo de informes.
* El Ad Hoc Analysis incluye actualizaciones para el Generador de segmentos y una actualización completa del Administrador de segmentos.
* Ahora puede etiquetar segmentos para organizar y buscar más tarde en lugar de utilizar carpetas. Antes, utilizaba las carpetas en [!DNL Ad Hoc Analysis] para organizar los segmentos.

## ¿Qué ha pasado con mis segmentos existentes? {#section_76CF47142D1A4FB6A0718AD9073049FE}

Sus segmentos existentes seguirán funcionando como siempre. Todos los informes a los que se hayan aplicado dichos segmentos funcionarán correctamente.

La mayoría de los anteriores segmentos predefinidos y de grupo se migrarán como plantillas de segmento al Generador de segmentos. Las plantillas de segmentos se utilizan para generar rápidamente segmentos personalizados con audiencias comunes. Las plantillas de segmentos no pueden aplicarse a un informe directamente, pero pueden guardarse de manera muy sencilla en un segmento personalizado.

Las plantillas de segmentos están marcadas con un icono especial en el Generador de segmentos.

## ¿Qué ha pasado con mis carpetas de segmentos existentes?  {#section_FB04DCF775694E69B761DCA53F301C30}

En lugar de carpetas de Análisis específicos, el Administrador de segmentos utiliza etiquetas. Los nombres de sus carpetas se convierten automáticamente en etiquetas, que se aplican a los segmentos respectivos.

## ¿Qué ha pasado con los informes programados que tienen segmentos aplicados?  {#section_81D1B215533C46E99E17BAE7A3376FDF}

Los informes programados siguen ejecutándose correctamente con los segmentos que haya definido.

Si elimina un segmento, los informes programados y los paneles a los que se haya aplicado siguen funcionando normalmente, es decir, el informe o panel siguen utilizando el segmento eliminado.

## ¿Qué es el contenedor de visitas? ¿En qué se diferencia de un contenedor de vistas de página?  {#section_65BBE60A836C4001938830DDA15DC256}

El contenedor de vista de página se llama ahora “contenedor de visita individual” para indicar que el contenedor segmenta todos los tipos de datos, no solo vistas de página. Por ejemplo, si vincula las llamadas de seguimiento, el Contenedor de visita individual incluirá o excluirá las llamadas trackAction desde los SDK móviles.

Tenga en cuenta que no se ha modificado la manera de funcionar del contenedor; simplemente se le ha cambiado el nombre.

## ¿Qué derechos y privilegios necesito para utilizar, crear y administrar segmentos?  {#section_648DFA3A882146C485A84ED014EEC707}

Todos los usuarios pueden crear y editar segmentos personales. Estos segmentos se pueden compartir directamente con cualquier otro usuario de Analytics. Los usuarios de Ad Hoc Analysis pueden ver los segmentos que cada uno creó y los compartidos directamente con el usuario.

En la consola web de Segmentación unificada, los administradores pueden editar cualquier segmento, y compartir segmentos con grupos y con todas las personas de la organización.

## ¿Puedo ver todos los segmentos de mi compañía?  {#section_AC2D328C7410419E80C7C17971CD95B3}

Se muestran todos los segmentos de análisis específicos que tiene y los segmentos que han sido compartidos específicamente con usted.

## ¿Puedo administrar todos los segmentos de análisis en el Administrador de segmentos?  {#section_AF5EDD72C74A4739BD40C4AF125CE489}

Los análisis específicos solo muestran segmentos creados por usted o los segmentos que han sido compartidos específicamente con usted. Para análisis específicos solamente, puede utilizar el Administrador de segmentos (Organizar segmentos) para administrar segmentos de análisis específicos. Utilice el Administrador de segmentos en Segmentación unificada para administrar todos los segmentos de Analytics.

## ¿Qué debería hacer con los segmentos duplicados que tienen el mismo nombre pero que pueden tener definiciones distintas?  {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

Ahora que los segmentos funcionan en múltiples grupos de informes, es posible que descubra que tiene múltiples segmentos con el mismo nombre. Le recomendamos que siga uno de los procedimientos siguientes

* Cambie el nombre de los segmentos que tienen el mismo nombre pero tienen definiciones distintas, o
* Elimine los segmentos que ya no son necesarios.

## ¿Cómo recomienda Adobe que limpie los segmentos?  {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* Etiquete todos los segmentos con la etiqueta heredada.
* Revise los segmentos que tiene.
* Añádalos a la biblioteca de segmentos cuando sea pertinente.
* Apruebe los segmentos canónicos.

## ¿Por qué no puedo eliminar un segmento?  {#section_0FEB6711031A4ABCA915CDA745ECF38D}

Si el segmento se publicó en Experience Cloud, no puede ni eliminarlo ni editarlo. Pero sí copiarlo y editar esa versión copiada.

## Más acerca de lo que ocurre con sus segmentos existentes  {#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Categoría del segmento </th> 
   <th colname="col2" class="entry"> ¿Qué les sucede a estos segmentos? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Segmentos favoritos en Ad Hoc Analysis </td> 
   <td colname="col2">Estos segmentos de Ad Hoc Analysis se muestran como segmentos regulares en Adobe Analytics. <p>No se deben confundir con la función Favoritos del Administrador de segmentos, que le permite marcar segmentos como favoritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmentos preconfigurados en Ad Hoc Analysis específicos: 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">Visitas a una sola página </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">Visitas desde dispositivos móviles </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">Visitas de búsqueda natural </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">Visitas de búsqueda de pago </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">Visitas con cookie de ID de visitante </li> 
    </ul> </td> 
   <td colname="col2"> <p>Estos segmentos se migrarán como  plantillas de segmentos al Generador de segmentos. </p> <p>Los informes existentes que tengan estos segmentos aplicados seguirán funcionando correctamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmentos de Experience Cloud (Suite): 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">No compradores </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">Compradores </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">Visitas por primera vez </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">Visitas provenientes de sitios sociales </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">Visitas de más de 10 minutos* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">Visitas con más de 5 visitas previas* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">Visitas provenientes de Facebook* </li> 
    </ul> </td> 
   <td colname="col2"> <p> La mayoría de estos segmentos (excepto los marcados con un asterisco *) se migrarán como  plantillas de segmentos al Generador de segmentos. Además, se han agregado varias plantillas de segmentos nuevas. </p> <p>Los informes existentes que tengan estos segmentos aplicados seguirán funcionando correctamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

