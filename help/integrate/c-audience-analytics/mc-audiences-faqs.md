---
description: Respuestas a preguntas que podría tener al implementar Audience Analytics.
solution: Experience Cloud
title: Preguntas frecuentes
uuid: 9dfc8f19-f9b2-4c2e-bff9-3d91cfe01bca
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 98%

---

# Preguntas frecuentes

Respuestas a preguntas que podría tener al implementar Audience Analytics.

## Preguntas frecuentes del ámbito jurídico {#section_B51CFC961C0B45A2BE5F4A4404620764}

<table id="table_22037CCB516C4231BF5820004FBB351A"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>P: ¿Cómo puedo saber si tengo información de identificación personal (PII) en mis datos de Analytics? Si lo sé, ¿qué puedo hacer al respecto?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_71E0ECD5981D4B65BCDA065BE07A43AA"> 
     <li id="li_F8FF61A4D7B54BA39DAA6F28DB51D749">Si tiene correos electrónicos, direcciones, etc. en una prop o eVar, considere crear valores hash de los datos durante la recopilación. </li> 
     <li id="li_57A8B4C7BB784FFCBC1DC363B35D9FF7">Si su país considera que la dirección IP es PII, <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/exclude-ip.html"  >active la confusión de IP </a>. </li> 
     <li id="li_C7AA02B831AE47A59E783623126A7789">Hable con el administrador de Analytics para comprobar lo que está recopilando. </li> 
     <li id="li_F6AAE868141E486AB8CAB291BD8EDB71">Hable con el departamento jurídico para comprobar qué consideran PII. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>P: ¿Cómo sé si mis grupos de informes realizan personalización en el sitio o direccionamiento fuera o dentro del sitio?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F0984CEF80DB4B589716BC55549E32B8"> 
     <li id="li_9BC3819784A9408F846D60FF0F20AAF9">Esto no se aplica al envío de datos de Adobe Analytics a Adobe Audience Manager. </li> 
     <li id="li_050A1BF9978E436895B5C7E33A82527D">Pregúntese lo siguiente: ¿volverá a compartir un segmento ya compartido en Analytics con una dimensión MCA en Experience Cloud? </li> 
     <li id="li_C52D969681B94F4AAA18FDEB21EC5B49">¿Va a realizar la exportación (por ejemplo, a través de fuentes de datos) a un sistema de inteligencia empresarial (BI) que se use para este propósito? </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Preguntas más frecuentes acerca de AAM {#section_6BDF746BA6464359A6A89A64EB025D12}

<table id="table_15B44592161240BDA79F3B020EA9CC9D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Cómo creo un destino de Analytics en Audience Manager?</b> </p> </td> 
   <td colname="col2"> Consulte <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html"  >Configurar un destino de Analytics en AAM</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Después de crear y guardar un destino de Analytics, ¿cuánto tardan los datos en aparecer en mis grupos de informes seleccionados?</b> </p> </td> 
   <td colname="col2"> <p>Los grupos de informes pueden tardar varias horas en rellenarse con datos nuevos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: He creado un nuevo destino de Analytics, pero no lo veo en la sección Asignaciones de destino de mis segmentos disponibles. ¿Dónde está el destino o cómo puedo encontrarlo?</b> </p> </td> 
   <td colname="col2"> <p>Un destino de Analytics desaparece de la sección Asignaciones de destino de un segmento cuando selecciona la opción <span class="uicontrol">Asignar automáticamente todos los segmentos actuales y futuros</span> en <span class="uicontrol">Asignaciones de segmentos</span>. </p> <p><img placement="break" align="left"  src="assets/auto-mapping.png" id="image_670ED5A306784FCBA8A0B336AC1F0FC6" width="300px" /> </p> <p>Para evitarlo, seleccione <span class="uicontrol">Asignar segmentos manualmente</span> en vez de la opción automática. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>P: ¿Esto me proporcionará toda la información de AAM en Analytics?</b> </p> </td> 
   <td colname="col2"> <p>No, solo los datos relacionados con personas que vienen a su sitio durante o después de la activación de Audiencias de Audience Manager y durante o después de la calificación de segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>P: ¿Esto me dará una audiencia total a la que poder dirigirme por segmento?</b> </p> </td> 
   <td colname="col2"> <p>No. Le indicará el número de visitantes de ese segmento que han llegado a su sitio durante o después de la calificación de segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>P: ¿En qué se diferencia esto del destino heredado de las cookies en Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Los segmentos se califican y se devuelven en tiempo real, en la misma visita. </p> <p>Se muestran automáticamente los nombres descriptivos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Qué sucede si algunos de mis grupos de informes contienen datos personales y otros no?</b> </p> </td> 
   <td colname="col2"> <p>Sugerencia: Cree dos destinos. Añada los grupos de informes con datos personales a uno y los grupos sin datos personales al otro. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Preguntas más frecuentes acerca de Analytics {#section_67BFB1B1E48D4113A38B075C020931BA}

<table id="table_19AEAE0A3575423CB4F5F164DB5626D5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Aparecerá esta integración como dimensión o como segmento en Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Como dimensiones: ID de audiencias y Nombre de audiencias.. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Dónde puedo utilizar estas dimensiones en Analytics?</b> </p> </td> 
   <td colname="col2"> <p>En casi cualquier parte; se las trata como cualquier otra dimensión recopilada en Analytics. Hay una excepción: por ahora, los datos no estarán en Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Por qué no veo los datos que pasan a través de Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Probablemente tenga en AAM un conflicto de controles de privacidad entre la fuente y el destino de los datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Por qué faltan en Analytics algunos de mis segmentos, aunque elegí enviarlos todos?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_B8938FD08C6F4F2387EDADDEF8089319"> 
     <li id="li_50A9BDF612304062913370F16BC882EF">Puede existir un conflicto entre los controles de exportación de datos de AAM del destino y de las fuentes de datos del segmento que impida el envío de determinados segmentos. </li> 
     <li id="li_AF5D6F883D6F4D3192E0BF23CF12ADEA">Si utiliza características de datos de terceros en sus segmentos, estos no pueden compartirse con destinos (grupos de conjuntos de informes) que contengan datos personales. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Por qué veo el mensaje “Se ha alcanzado el límite de audiencias” en mi informe de Analytics? (Nota: Esto también se representará como ID de audiencia = -1 y "::max_audiences_expanded::" en Data Warehouse)</b> </p> </td> 
   <td colname="col2"> <p>De forma predeterminada, la integración de Audience Analytics para AAM envía a Analytics, para cada visita, todos los segmentos a los que el visitante pertenece. Si un visitante pertenece a más de 150 segmentos de AAM en una sola visita, se envían a Analytics los <b>150 segmentos para los que se ha obtenido cualificación más recientemente</b> y el resto se trunca. </p> <p>Se envía a Analytics un marcador adicional que indica que la lista de segmentos se ha truncado y se muestra “Alcanzado límite de audiencias” en la dimensión Nombre de audiencia y “-1” en la dimensión ID de audiencia. </p> <p>Aunque es poco probable que un visitante esté cualificado para pertenecer a más de 150 segmentos en una visita particular, puede suceder en un pequeño número de ocasiones. Si el mensaje “Alcanzado límite de audiencias” aparece en su informe, tiene dos opciones: </p> 
    <ul id="ul_8E290B2E32DC49738F6FD00CB0CE2BBB"> 
     <li id="li_12F498981EA949B5BCBD40ECC954C339"><b>Opción 1</b>: permita que la integración siga funcionando del modo predeterminado, con el envío de los 150 segmentos para los que un visitante particular ha obtenido cualificación más recientemente. </li> 
     <li id="li_CA4D5747AA4A4452929097807B604959"><b>Opción 2</b>: en AAM, escoja para la integración los 150 segmentos más relevantes para su negocio. AAM comprobará la adecuación de los visitantes a estos 150 segmentos. La desventaja de este enfoque es que solo recibirá estos 150 segmentos para todos los visitantes. Por su parte, la opción 1 puede ofrecer segmentos ilimitados, ya que la integración se produce por visita. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Se facturan llamadas de servidor adicionales a Analytics por esta integración?</b> </p> </td> 
   <td colname="col2"> <p>No. Las Audiencias de AAM se incorporan a las visitas de Analytics en el servidor. Esto no incurre en llamadas adicionales al servidor en Analytics (ni principales ni secundarias). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Preguntas más frecuentes acerca del reenvío de lado del servidor (SSF) {#section_ADDE84ABCA0D4906B6235E92D185E0C6}

<table id="table_B7067B70FF85498896801F58D716202F"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>P: Si tengo implementado el reenvío de servidor, ¿tengo que activar también el reenvío de servidor para los grupos de informes en Administración de Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Sí. En la configuración de destinos de AAM solo verá los grupos de informes que tengan activado el reenvío de servidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Por qué no puedo activar el reenvío de servidor para determinados grupos de informes en Administración de Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Solo pueden habilitarse los grupos asignados a su organización de Experience Cloud. </p> </td> 
  </tr> 
 </tbody> 
</table>

Para saber más sobre este tema, consulte [Preguntas frecuentes sobre el reenvío de lado del servidor](/help/admin/admin/c-server-side-forwarding/ssf-faq.md).

## Preguntas más frecuentes generales {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

<table id="table_1F7C0C785F9C472286A96F8C25E8440B"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>P: ¿Por qué el visitante del segmento tiene un recuento diferente en Audience Manager y Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Consulte <a href="/help/integrate/c-audience-analytics/visitor-count-reconciliation.md"  > Diferencias en la contabilización de visitantes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Cuál es la diferencia entre las “audiencias” de AAM y los “segmentos” de Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Consulte <a href="/help/integrate/c-audience-analytics/aam-analytics-segments.md"  > Explicación de los segmentos en Analytics y Audience Manager </a>. </p> <p>Las audiencias de AAM se envían y comparten como componentes de “dimensión” para su uso en Analytics. No aparecerán como segmentos en el Generador de segmentos, por ejemplo, sino como dimensiones con las que se pueden crear segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Cuál es la diferencia entre los atributos del cliente y los datos de clientes integrados desde AAM?</b> </p> </td> 
   <td colname="col2"> <p>Los atributos del cliente no dependen del tiempo: se aplican de forma retroactiva y en adelante. Los datos integrados desde AAM dependen del tiempo y solo se aplican en adelante. Además, Atributos de cliente es una tabla de consulta para ID de visitante de Experience Cloud, mientras que la integración AAM consiste en datos vinculados a cada visita de un visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Qué sucede con los enfoques antiguos para este problema, como los destinos de cookies beta o de complemento de consulta?</b> </p> </td> 
   <td colname="col2"> <p>Recomendamos implementar la nueva integración y eliminar los destinos antiguos. </p> </td> 
  </tr> 
 </tbody> 
</table>
