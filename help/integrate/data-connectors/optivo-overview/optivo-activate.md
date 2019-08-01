---
description: Use el Asistente para la configuración de Data Connectors de Adobe para configurar la integración.
seo-description: Use el Asistente para la configuración de Data Connectors de Adobe para configurar la integración.
seo-title: Activar la integración
title: Activar la integración
uuid: 3 b 2 acdb 8-9 a 1 f -4 f 17-92 f 2-6 a 3780 a 8 f 626
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d10546972c03efae1bc365b7391000a40a79b0a4

---


# Activate the Integration{#activate-the-integration}

Use el Asistente para la configuración de Data Connectors de Adobe para configurar la integración.

1. Start [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Complete el Asistente de integración con la información de la siguiente tabla:

| Campo | Descripción |
|--- |--- |
| Grupo de informes | Grupo de informes que recibe los datos de esta integración. |
| Nombre de la integración | Especifique el nombre de la integración que Data Connectors muestra en la lista de integración activa del conjunto de informes. |
| Dirección de correo electrónico | Proporcione una dirección de correo electrónico para recibir información relacionada con la integración. |
| ID de cuenta | Identificador exclusivo que su proveedor de servicios de correo electrónico asigna a su organización. Se utilizará al solicitar datos de campaña de correo electrónico (p. ej., # Enviado, # Abierto, Pulsado, etc.) desde y enviar segmentos de visitantes a su proveedor de servicios de correo electrónico. |
| Recipient ID | Este ID es una representación numérica o codificada de una dirección de correo electrónico del sistema de correo electrónico optivo®. Este "ID de destinatario" está asociado con el comportamiento de los visitantes en línea en el sitio (abandonos del carro, compras, etc.) que se extraen al sistema de broadmail optivo® y se pueden aprovechar para fines de remercadotecnia. |
| ID de mensaje | (Requerido) Almacena el ID de correo único. These classification dimensions are created by the Data Connectors wizard for the Message ID: a)**Campaigns**: Campaigns associated with the message. b)**Channel**: The channel of transmission, this is constantly "optivo broadmail". c)**Country Code**: This field contains the country code of the origin sender country. Es una constante "DE". d) **Delivery Tool**: Method of transmission, always "Email". e) **Message Name**: The name of the mailing, as it is configured in optivo® broadmail. f) **Start Date**: Timestamp of the start of this mailing. |
| Tiempo de postclic | (Requerido) Esto es necesario para transmitir información sobre una acción de destinatario a optive® broadmail después de que el destinatario haya hecho clic en un vínculo en un correo electrónico. |
| Publicar producto | (Requerido) Esto es necesario para transmitir información sobre una acción de destinatario a optive® broadmail después de que el destinatario haya hecho clic en un vínculo en un correo electrónico. |
| Acción de postclic | (Requerido) Esto es necesario para transmitir información sobre una acción de destinatario a optive® broadmail después de que el destinatario haya hecho clic en un vínculo en un correo electrónico. |
| Devolución fuerte | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de devoluciones importados del sistema de correo electrónico. Número de mensajes de correo electrónico que no se entregaron a los destinatarios y se consideran permanentemente deshabilitables. |
| Devolución suave | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de devoluciones que se importan del sistema de correo electrónico. Número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Pulsado | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos donde se hizo clic por correo electrónico desde el sistema de correo electrónico. El evento Clics permite ver la cantidad de visitantes que hicieron clic en el mensaje de correo electrónico. |
| Abierto | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos abiertos por correo electrónico importados del sistema de correo electrónico. El evento Abierto permite ver la cantidad de visitantes que abrieron el mensaje de correo electrónico. |
| Enviado | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos enviados por correo electrónico importados del sistema de correo electrónico. El evento Enviado permite ver la cantidad de mensajes de correo electrónico que se enviaron. |
| Sin suscripción | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de cancelación de suscripción importados del sistema de correo electrónico. El evento Sin suscripción permite ver la cantidad de visitantes que abrieron el mensaje de correo electrónico pero luego hicieron clic en el vínculo Cancelar suscripción para rechazar los futuros mensajes de correo electrónico de su organización. |
| Segmentos | Permite utilizar los segmentos existentes junto con esta integración (opcional). |
| Solicitudes de acceso | Habilite los privilegios de acceso recomendados. |
| Recopilación de datos | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. Si selecciona esta opción, especifique los identificadores exclusivos utilizados para esta integración:<ul><li>Parámetro de cadena de consulta de ID de mensaje: Este valor representa el ID de mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li><li>Parámetro de cadena de consulta de ID de destinatario: Este valor representa la ID del destinatario que el socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li></ul> |
| Generación de tableros y marcadores | Generar automáticamente un tablero y marcadores para la integración. |