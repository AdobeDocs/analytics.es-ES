---
description: El asistente de integración de Data Connectors lo guía durante el proceso de integración.
title: Ejecución del asistente de integración de Data Connectors
uuid: 387ac9d0-3719-49ff-81cb-1f05accf9b6c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Ejecución del asistente de integración de Data Connectors {#running-the-data-connectors-integration-wizard}

El asistente de integración de Data Connectors lo guía durante el proceso de integración.

Para configurar la integración:

1. Iniciar sesión en Experience Cloud.
1. En la página de inicio de Analytics, haga clic en el icono Data Connectors™ en la rueda de programas o en la barra de herramientas.
1. En la página Data Connectors, seleccione el grupo de informes en el que desea configurar la integración.

   >[!NOTE]
   >
   >Asegúrese de seleccionar el grupo de informes deseado en la lista desplegable **Grupo de informes** en la esquina superior izquierda de la página Data Connectors.

1. Haga clic en la pestaña **Alfabéticamente** en la parte superior de la **lista de socios** en la parte izquierda de la interfaz de usuario de Data Connectors y, a continuación, busque el icono **Delivra**.
1. Arrastre el icono de **Delivra** a una ranura de complemento vacía del grupo de informes de Analytics para iniciar el asistente de integración de Data Connectors.
1. En la página de introducción a la integración de Delivra, revise el texto, active la casilla de verificación para aceptar las tarifas asociadas con la integración y, a continuación, haga clic en **Siguiente**.

   Esta página proporciona información general sobre la integración, junto con vínculos útiles para obtener más información. Esta integración incluye tarifas de Adobe y Delivra. Póngase en contacto con los Representantes de ventas correspondientes para ambas organizaciones y asegúrese de comprender la estructura de tarifas.
1. En cada página del asistente de integración de Data Connectors, proporcione la información necesaria, tal como se describe en la tabla siguiente:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>NÚMERO DE PÁGINA DEL ASISTENTE</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>CAMPO</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIPCIÓN</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>Nombre de la integración </p> </td> 
   <td colname="col3"> <p>Especifique el nombre de la integración que Data Connectors muestra en la lista de integración activa del conjunto de informes. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Integración de dirección de correo electrónico </p> </td> 
   <td colname="col3"> <p>Especifique la dirección de correo electrónico que recibe todas las notificaciones relacionadas con esta integración y, a continuación, haga clic en <b>Siguiente</b> para continuar con el paso 2 del asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>ID de cuenta </p> </td> 
   <td colname="col3"> <p>Especifique su ID de cuenta de Delivra (el identificador único asignado a su organización por Delivra) y, a continuación, haga clic en <b>Siguiente</b> para continuar con el paso 3 del asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID de mensaje </p> </td> 
   <td colname="col3"> <p>Identifique la eVar de Analytics que sirve para rastrear el ID de mensaje de correo electrónico. </p> <p>El ID de mensaje se utiliza para campañas de marketing y remarketing. El ID de mensaje se conoce generalmente como “Código de seguimiento”. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID (ID de destinatario) </p> </td> 
   <td colname="col3"> <p>Identifique la eVar de Analytics que sirve para rastrear el ID de destinatario de correo electrónico. </p> <p>El ID de destinatario se utiliza para campañas de marketing y remarketing. El ID del mensaje se conoce comúnmente como “Código de visitante”. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Marque la casilla de verificación </p> </td> 
   <td colname="col3"> <p>Revise la información mostrada junto a la casilla de verificación para aceptar: </p> <p><i>Reconozco que, al habilitar el seguimiento de “ID de destinatario”, esta función puede rastrear información personal de los visitantes de nuestro sitio. Esto tiene implicaciones para la privacidad que requieren la implementación de los procedimientos apropiados por parte de mi organización, como por ejemplo, notificar a los visitantes de nuestro sitio y obtener su consentimiento. </i> </p> <p>Si acepta, marque la casilla de verificación y, a continuación, haga clic en <b>Siguiente</b> para continuar con el paso 4 del asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Segmentos de nivel de grupo de informes definidos por el cliente </p> </td> 
   <td colname="col3"> <p>Esta integración crea los segmentos definidos por el socio que se muestran en la parte izquierda de la página Segmentos de integración del asistente de integración. </p> <p>Además, puede seleccionar segmentos existentes de nivel de grupo de informes para incluirlos en la integración. </p> <p>Seleccione los segmentos que desee en el lado derecho de la página y haga clic en <b>Siguiente</b> para continuar con el paso 5 del asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Clics </p> </td> 
   <td colname="col3"> <p>Especifique el evento de Analytics que almacena los datos de correos electrónicos en los que se hizo clic importados desde el sistema de correo electrónico. </p> <p>El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Aperturas </p> </td> 
   <td colname="col3"> <p>Especifique el evento de Analytics que almacena los datos de correos electrónicos abiertos importados desde el sistema de correo electrónico. </p> <p>El evento de aperturas (Opened) permite ver el número de visitantes que abrieron el mensaje de correo electrónico. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Enviados </p> </td> 
   <td colname="col3"> <p>Especifique el evento de Analytics que almacena los datos de correos electrónicos enviados importados del sistema de correo electrónico. </p> <p>El evento de clics permite ver el número de mensajes de correo electrónico que se enviaron. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Devoluciones totales </p> </td> 
   <td colname="col3"> <p>Especifique el evento de Analytics que almacena los datos de devoluciones totales de correo electrónico importados del sistema de correo electrónico. </p> <p>El evento de devoluciones totales permite ver el número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Cancelación de suscripción </p> </td> 
   <td colname="col3"> <p>Especifique el evento de Analytics que almacena los datos de cancelación de suscripción del correo electrónico importados del sistema de correo electrónico. </p> <p>El evento de cancelación de suscripción (Unsuscribed) le permite ver el número de visitantes que abrieron el mensaje de correo electrónico y luego hicieron clic en el vínculo Cancelar suscripción para rechazar futuros mensajes de correo electrónico de su organización. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> Recursos compartidos </td> 
   <td colname="col3"> <p>Especifique el número de veces que el mensaje de correo electrónico se compartió en una red social y, a continuación, haga clic en <b>Siguiente</b> para continuar con el paso 6 del asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Recopilación de datos: complemento de JavaScript </p> </td> 
   <td colname="col3"> <p>Seleccione <b>Complemento de JavaScript</b> si desea utilizar el complemento como modelo de recopilación para esta integración y, a continuación, haga clic en <b>Siguiente</b> para continuar con el paso 7 del asistente. </p> <p> <p>Nota: La solución automatizada es la opción predeterminada. </p> </p> <p>Póngase en contacto con su consultor de Adobe para obtener una copia del complemento de JavaScript que sirve para esta integración. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Recopilación de datos: solución automatizada </p> </td> 
   <td colname="col3"> <p>Seleccione <b>Solución automatizada</b> si desea utilizar un modelo de recopilación automatizada para esta integración y, a continuación, especifique los identificadores únicos utilizados para esta integración. </p> <p> <p>Nota: La solución automatizada es la opción predeterminada. </p> </p> <p>Si selecciona esta opción, especifique los identificadores únicos utilizados para esta integración: </p> <p><b>Parámetro de cadena de consulta de ID de mensaje:</b> este valor representa el ID de mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje. </p> <p><b>Parámetro de cadena de consulta de ID de destinatario:</b> este valor representa el ID de destinatario anexado a la dirección URL de la página de aterrizaje por su socio de correo electrónico. </p> <p>Haga clic en <b>Siguiente</b> para continuar con el paso 7 del asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Resumen de la integración </p> </td> 
   <td colname="col3"> <p>Compruebe los parámetros de la integración haciendo clic en el signo más (+) situado junto a cada categoría y, a continuación, haga clic en <b>Guardar</b> para continuar con el paso 8 del asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Integración finalizada </p> </td> 
   <td colname="col3"> <p>Haga clic en <b>Finalizar</b> para completar la integración. </p> <p><b>IMPORTANTE:</b> Analytics no guarda la configuración de la integración hasta que no haga clic en <b>Finalizar</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>
