---
description: El Asistente para integración de Data Connectors lo lleva a través del proceso de integración de Conectores de datos.
seo-description: El Asistente para integración de Data Connectors lo lleva a través del proceso de integración de Conectores de datos.
seo-title: Ejecución del Asistente para integración de Conectores de datos
title: Ejecución del Asistente para integración de Conectores de datos
uuid: 387 ac 9 d 0-3719-49 ff -81 cb -1 f 05 accf 9 b 6 c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d55b23a5baf5be1d7afb708cc6ef94851eac3e77

---


# Running the Data Connectors Integration Wizard{#running-the-data-connectors-integration-wizard}

El Asistente para integración de Data Connectors lo lleva a través del proceso de integración de Conectores de datos.

Para configurar la integración:

1. Inicie sesión en Marketing Cloud.
1. En la página principal de Analytics, haga clic en el icono de Data Connectors™ en la rueda de programas o rueda de programas.
1. En la página Conectores de datos, seleccione el grupo de informes donde desee configurar la integración.

   >[!NOTE]
   >
   >Make sure that you select the desired report suite from the **Report Suite** drop-down list in the upper-left corner of the Data Connectors page.

1. Click the **Alphabetical** tab at the top of the **Partner List** on the left side of the Data Connectors UI, then locate the **Delivra** icon.
1. Drag the **Delivra** icon to an empty plug-in slot in your Analytics report suite to launch the Data Connectors Integration Wizard.
1. On the Delivra Integration introduction page, review the text, then select the check box to accept the fees associated with the integration, then click **Next**.

   Esta página proporciona información general sobre la integración, junto con vínculos útiles para obtener más información. Existen tarifas de Adobe y Delivra asociadas con esta integración. Póngase en contacto con los Representantes de ventas correspondientes para ambas organizaciones y asegúrese de comprender la estructura de tarifas.
1. En cada página del Asistente para integración de Data Connectors, proporcione la información requerida, tal como se describe en la siguiente tabla:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>WIZARD PAGE #</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>FIELD</b> </p> </th> 
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
   <td colname="col3"> <p>Specify the email address that receives all notifications related to this integration, then click <b>Next</b> to proceed to Step 2 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>ID de cuenta </p> </td> 
   <td colname="col3"> <p>Specify your Delivra Account ID (the unique identifier assigned to your organization by Delivra), then click <b>Next</b> to proceed to Step 3 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID de mensaje </p> </td> 
   <td colname="col3"> <p>Identifique la evar de Analytics utilizada para rastrear el ID de mensaje de correo electrónico. </p> <p>El ID de mensaje se utiliza para campañas de mercadotecnia y remercadotecnia. El ID de mensaje se conoce comúnmente como "Código de seguimiento". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>Identifique la evar de Analytics utilizada para rastrear la ID del destinatario de correo electrónico. </p> <p>El ID de destinatario se utiliza para campañas de mercadotecnia y remercadotecnia. El ID de mensaje se conoce comúnmente como "Código de visitante". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Casilla de verificación de aceptación </p> </td> 
   <td colname="col3"> <p>Revise la información mostrada junto a la casilla de verificación Aceptación: </p> <p><i>Reconozco que, al habilitar el seguimiento de «ID de destinatario», es posible que este dispositivo rastree información personal de los visitantes de nuestro sitio. This has privacy implications requiring the implementation of appropriate procedures by my organization, such as providing notice to, and consent of, our site visitors. </i> </p> <p>If you agree to the acceptance statement, select the check box, then click <b>Next</b> to proceed to Step 4 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Segmentos de nivel de grupo de informes definidos por el cliente </p> </td> 
   <td colname="col3"> <p>Esta integración crea segmentos definidos por el socio que se muestran en la parte izquierda de la página Segmentos de integración del Asistente para integración. </p> <p>Además, puede seleccionar segmentos existentes de nivel de grupo de informes para incluirlos en la integración. </p> <p>Select the desired segments on the right side of the page, then click <b>Next</b> to proceed to Step 5 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Pulsado </p> </td> 
   <td colname="col3"> <p>Especifique el evento de Analytics que almacena los datos enviados por correo electrónico importados del sistema de correo electrónico. </p> <p>El evento Clics permite ver la cantidad de visitantes que hicieron clic en el mensaje de correo electrónico. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Abierto </p> </td> 
   <td colname="col3"> <p>Especifique el evento de Analytics que almacena el correo electrónico abierto importado desde el sistema de correo electrónico. </p> <p>El evento Abierto permite ver la cantidad de visitantes que abrieron el mensaje de correo electrónico. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Enviado </p> </td> 
   <td colname="col3"> <p>Especifique el evento de Analytics que almacena los datos enviados por correo electrónico importados del sistema de correo electrónico. </p> <p>El evento Click permite ver la cantidad de mensajes de correo electrónico que se enviaron. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Devoluciones totales </p> </td> 
   <td colname="col3"> <p>Especifique el evento de Analytics que almacena los datos de Devoluciones totales del mensaje de correo electrónico importados del sistema de correo electrónico. </p> <p>El evento de devoluciones totales permite ver la cantidad de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Sin suscripción </p> </td> 
   <td colname="col3"> <p>Especifique el evento de Analytics que almacena los datos de Cancelar suscripción importados del sistema de correo electrónico. </p> <p>El evento Sin suscripción permite ver la cantidad de visitantes que abrieron el mensaje de correo electrónico pero luego hicieron clic en el vínculo Cancelar suscripción para rechazar los futuros mensajes de correo electrónico de su organización. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> Recursos compartidos </td> 
   <td colname="col3"> <p>Specify the number of times the email message was shared to a social network, then click <b>Next</b> to proceed to Step 6 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Recopilación de datos: Complemento JavaScript </p> </td> 
   <td colname="col3"> <p>Select <b>JavaScript Plug-in</b> if you want to use the plug-in as the collection model for this integration, then click <b>Next</b> to proceed to Step 7 of the Wizard. </p> <p> <p>Nota: La solución automatizada es la selección predeterminada. </p> </p> <p>Póngase en contacto con su consultor de Adobe para obtener una copia del complemento JavaScript utilizado para esta integración. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Recopilación de datos: Solución automatizada </p> </td> 
   <td colname="col3"> <p>Select <b>Automated Solution</b> if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. </p> <p> <p>Nota: La solución automatizada es la selección predeterminada. </p> </p> <p>Si selecciona esta opción, especifique los identificadores exclusivos utilizados para esta integración: </p> <p><b>Parámetro de cadena de consulta de ID de mensaje:</b>Este valor representa el ID de mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje. </p> <p><b>Parámetro de cadena de consulta de ID de destinatario:</b> Este valor representa el ID de destinatario que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje. </p> <p>Click <b>Next</b> to proceed to Step 7 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Resumen de integración </p> </td> 
   <td colname="col3"> <p>Verify the integration parameters by clicking the plus sign (+) next to each category, then click <b>Save</b> to proceed to Step 8 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Integración completada </p> </td> 
   <td colname="col3"> <p>Click <b>Finish</b> to complete the integration. </p> <p><b>IMPORTANTE:</b> Analytics no guarda la configuración de integración hasta que haga clic <b>en Finalizar</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

