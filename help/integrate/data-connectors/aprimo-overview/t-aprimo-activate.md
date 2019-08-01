---
description: Use el Asistente para la configuración de Data Connectors de Adobe para configurar la integración.
seo-description: Use el Asistente para la configuración de Data Connectors de Adobe para configurar la integración.
seo-title: Activar la integración
title: Activar la integración
uuid: 0 a 5 d 2 d 45-5133-4259-96 ce-c 992 a 1 e 314 EE
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a3310ec57ce4c68539f07e0d294c8175742c49dc

---


# Activate the Integration {#activate-the-integration}

Use el Asistente para la configuración de Data Connectors de Adobe para configurar la integración.

1. Start [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Complete el Asistente de integración con la información de la siguiente tabla:

| Campo | Descripción |
|--- |--- |
| Grupo de informes | Grupo de informes que recibe los datos de esta integración. |
| Nombre de la integración | Especifique el nombre de la integración que Data Connectors muestra en la lista de integración activa del conjunto de informes. |
| ID de cuenta | Especifique su ID de cuenta de Aprimo. |
| Recipient ID | Este ID es una representación numérica o codificada de una dirección de correo electrónico del sistema Aprimo. Este "ID de destinatario" está asociado con el comportamiento de los visitantes en línea en la ID del destinatario del sitio (abandonos del carro, compras, etc.) que se extraen al sistema Aprimo y se pueden aprovechar para fines de remercadotecnia. |
| Pulsado | (Requerido) Especifique el evento de Adobe Analytics que almacena el correo electrónico de los datos importados importados del sistema de correo electrónico. El evento Clics permite ver la cantidad de visitantes que hicieron clic en el mensaje de correo electrónico. |
| ID de mensaje | (Requerido) Almacena el ID de correo único. |
| Abierto | (Requerido) Especifique el evento de Adobe Analytics que almacena el correo electrónico abierto importado desde el sistema de correo electrónico. El evento Abierto permite ver la cantidad de visitantes que abrieron el mensaje de correo electrónico. |
| Recipient ID | (Requerido) Almacena el ID de visitante único. |
| Enviado | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos enviados por correo electrónico importados del sistema de correo electrónico. El evento Enviado permite ver la cantidad de mensajes de correo electrónico que se enviaron. |
| Devoluciones | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de Devoluciones totales del mensaje de correo electrónico importados del sistema de correo electrónico. El evento de devoluciones totales permite ver la cantidad de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Sin suscripción | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de cancelación de suscripción de correo electrónico importados del sistema de correo electrónico. El evento Sin suscripción permite ver la cantidad de visitantes que abrieron el mensaje de correo electrónico pero luego hicieron clic en el vínculo Cancelar suscripción para rechazar los futuros mensajes de correo electrónico de su organización. |
| Segmentos | Esta integración crea los segmentos definidos por el socio que se muestran en la sección Segmentos de socio. Además, puede seleccionar segmentos existentes de nivel de grupo de informes para incluirlos en la integración. |
| Solicitudes de acceso | Habilite los privilegios de acceso recomendados. |
| Recopilación de datos | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. |
Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. Si selecciona esta opción, especifique los identificadores exclusivos utilizados para esta integración:
<ul><li>Parámetro de cadena de consulta de ID de mensaje: Este valor representa el ID de mensaje que el socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li>
<li>Parámetro de cadena de consulta de ID de destinatario: Este valor representa la ID del destinatario que el socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li></ul>|
| Tablero y Generación de marcadores | Genere automáticamente un tablero y marcadores para la integración.|
