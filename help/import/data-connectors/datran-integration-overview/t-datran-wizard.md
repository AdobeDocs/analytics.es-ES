---
description: El Asistente para la integración de Conectores de datos le guía a través del proceso de integración de Conectores de datos.
seo-description: El Asistente para la integración de Conectores de datos le guía a través del proceso de integración de Conectores de datos.
seo-title: Running the Data Connectors Integration Wizard
title: Ejecución del Asistente para la integración de Data Connectors
uuid: 714417f7-c1df-4e61-a07f-d319f6581c9c
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Ejecución del Asistente para la integración de Data Connectors{#running-the-data-connectors-integration-wizard}

El Asistente para la integración de Conectores de datos le guía a través del proceso de integración de Conectores de datos.

Para configurar la integración:

1. Iniciar sesión en Experience Cloud.
1. En la página de inicio de Adobe Analytics, haga clic en el icono Data Connectors™ en la rueda de programas o en la barra de herramientas.
1. En la página Conectores de datos, seleccione el grupo de informes en el que desea configurar la integración.

   >[!NOTE]
   >
   >Asegúrese de seleccionar el grupo de informes deseado en la lista desplegable Grupo **de** informes en la esquina superior izquierda de la página Conectores de datos.

1. Haga clic en la ficha **Alfabética** en la parte superior de la lista **de** socios en la parte izquierda de la interfaz de usuario de Data Connectors y, a continuación, busque el icono de **Datran** .
1. Arrastre el icono de **Datran** a una ranura de complemento vacía del grupo de informes de Adobe Analytics para iniciar el Asistente para la integración de Data Connectors.

1. En la página de introducción de Integración de Datran, revise el texto, luego seleccione la casilla de verificación para aceptar las tarifas asociadas con la integración y haga clic en **Siguiente**.

   Esta página proporciona información general sobre la integración, junto con vínculos útiles para obtener más información. Esta integración conlleva tarifas tanto de Adobe como de Datran. Póngase en contacto con los Representantes de ventas correspondientes para ambas organizaciones y asegúrese de comprender la estructura de tarifas.
1. On each page of the Data Connectors Integration Wizard, provide the required information, as described in the following table:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>Nº DE PÁGINA DEL ASISTENTE</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>CAMPO</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIPCIÓN</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>Nombre de la integración </p> </td> 
   <td colname="col3"> <p>Especifique el nombre de la integración que Data Connectors muestra en la Lista de integración activa del conjunto de informes. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Integración de dirección de correo electrónico </p> </td> 
   <td colname="col3"> <p>Especifique la dirección de correo electrónico que recibe todas las notificaciones relacionadas con esta integración y haga clic en <b>Siguiente</b> para continuar con el paso 2 del Asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>ID de cuenta </p> </td> 
   <td colname="col3"> <p>Especifique su ID de cuenta de Datran (el identificador único asignado a su organización por Datran) y haga clic en <b>Siguiente</b> para continuar con el paso 3 del Asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID del mensaje </p> </td> 
   <td colname="col3"> <p>Identify the Adobe Analytics eVar used for tracking the email Message ID. </p> <p>El ID del mensaje se utiliza para campañas de mercadotecnia y remercadotecnia. La ID del mensaje se conoce generalmente como "Código de seguimiento". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>Identify the Adobe Analytics eVar used for tracking the email Recipient ID. </p> <p>La ID del destinatario se utiliza para campañas de mercadotecnia y remercadotecnia. La ID del mensaje se conoce generalmente como "código del visitante". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Casilla de verificación Aceptación </p> </td> 
   <td colname="col3"> <p>Revise la información mostrada junto a la casilla de verificación Aceptación: </p> <p><i>I understand that by enabling "Recipient ID" tracking, this feature may track personally identifiable information of our site visitors. Esto tiene implicaciones para la privacidad que requieren la implementación de los procedimientos apropiados por parte de mi organización, tales como la notificación y el consentimiento de los visitantes de nuestro sitio. </i> </p> <p>Si acepta la declaración de aceptación, active la casilla de verificación y, a continuación, haga clic en <b>Siguiente</b> para continuar con el paso 4 del Asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Segmentos de nivel de grupo de informes definidos por el cliente </p> </td> 
   <td colname="col3"> <p>Esta integración crea los segmentos definidos por el socio que se muestran en la parte izquierda de la página Segmentos de integración del Asistente para integración. </p> <p>Además, puede seleccionar segmentos existentes de nivel de grupo de informes para incluirlos en la integración. </p> <p>Seleccione los segmentos deseados en la parte derecha de la página y haga clic en <b>Siguiente</b> para continuar con el paso 5 del Asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Clicked </p> </td> 
   <td colname="col3"> <p>Specify the Adobe Analytics event that stores the email Clicked data imported from the email system. </p> <p>El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Abierto </p> </td> 
   <td colname="col3"> <p>Specify the Adobe Analytics event that stores the email Opened data imported from the email system. </p> <p>The Opened event lets you see the number of visitors who opened the email message. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Sent </p> </td> 
   <td colname="col3"> <p>Specify the Adobe Analytics event that stores the email Sent data imported from the email system. </p> <p>The Clicked event lets you see the number of email messages that were sent. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Total Bounces </p> </td> 
   <td colname="col3"> <p>Specify the Adobe Analytics event that stores the email Total Bounces data imported from the email system. </p> <p>El evento Devoluciones totales permite ver el número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Unsubscribed </p> </td> 
   <td colname="col3"> <p>Specify the Adobe Analytics event that stores the email Unsubscribe data imported from the email system. </p> <p>El evento Cancelar suscripción le permite ver el número de visitantes que abrieron el mensaje de correo electrónico y luego hicieron clic en el vínculo Cancelar suscripción para rechazar futuros mensajes de correo electrónico de su organización. </p> <p>Haga clic en Siguiente para continuar con el paso 6 del Asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Recopilación de datos: Complemento JavaScript </p> </td> 
   <td colname="col3"> <p>Seleccione <b>JavaScript Plug-in</b> si desea utilizar el complemento como modelo de recopilación para esta integración, luego haga clic en <b>Siguiente</b> para continuar con el paso 7 del Asistente. </p> <p> <p>Nota:  La solución automatizada es la selección predeterminada. </p> </p> <p>Póngase en contacto con su consultor de Adobe para obtener una copia del complemento JavaScript utilizado para esta integración. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Recopilación de datos: Solución automatizada </p> </td> 
   <td colname="col3"> <p>Select Automated Solution if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration.<b></b> </p> <p> <p>Nota:  La solución automatizada es la selección predeterminada. </p> </p> <p>Si selecciona esta opción, especifique los identificadores únicos utilizados para esta integración: </p> <p><b>Parámetro de cadena de consulta de ID de mensaje:</b>este valor representa el ID del mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje. </p> <p><b></b> Parámetro de cadena de consulta de ID del destinatario: Este valor representa la ID del destinatario anexada a la dirección URL de la página de aterrizaje por su socio de correo electrónico. </p> <p>Haga clic en <b>Siguiente</b> para continuar con el paso 7 del Asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Resumen de integración </p> </td> 
   <td colname="col3"> <p>Compruebe los parámetros de integración haciendo clic en el signo más (+) situado junto a cada categoría y, a continuación, haga clic en <b>Guardar</b> para continuar con el paso 8 del Asistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Integración completada </p> </td> 
   <td colname="col3"> <p>Haga clic en <b>Finalizar</b> para completar la integración. </p> <p><b></b> IMPORTANTE: Adobe Analytics no guarda la configuración de integración hasta que haga clic en <b>Finalizar</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>
