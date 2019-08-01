---
description: Use el Asistente para la configuración de Data Connectors de Adobe para configurar la integración.
seo-description: Use el Asistente para la configuración de Data Connectors de Adobe para configurar la integración.
seo-title: Activar la integración
title: Activar la integración
uuid: 93 c 59 f 8 e -3 cf 5-44 c 1-9 a 04-22460 af 93 d 5 d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a3310ec57ce4c68539f07e0d294c8175742c49dc

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
| Pulsado | Número total de clics en correo electrónico. |
| ID de campaña | Almacena el ID de mensaje único. Esto suele almacenarse en la variable de campaña. |
| Abierto | Número total de aperturas de correo electrónico. |
| Clics personales | Número de personas que han hecho clic. |
| Procesado | Número total de correos electrónicos procesados. |
| Broadlog ID | Este ID es una representación numérica o codificada de una dirección de correo electrónico del sistema Neolane. Este "ID de Broadlog" está asociado con el comportamiento de los visitantes en línea en el sitio (abandonos del carro de compras, compras, etc.) que se extraen al sistema Neolane y se pueden aprovechar para fines de remercadotecnia. |
| Programado | Número de mensajes de correo electrónico que se han programado para su envío. |
| Enviado | Número de mensajes de correo electrónico que se enviaron. |
| Devoluciones totales | Número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Clics únicos | Cantidad de clics distintos. |
| Aperturas únicas | Número de aperturas diferentes. |
| Sin suscripción | Número de visitantes que abrieron el mensaje de correo electrónico pero luego hicieron clic en el vínculo Cancelar suscripción para rechazar los futuros mensajes de correo electrónico de su organización. |
| Segmentos | Esta integración crea los segmentos definidos por el socio que se muestran en la sección Segmentos de socio. Además, puede seleccionar segmentos existentes de nivel de grupo de informes para incluirlos en la integración. |
| Solicitudes de acceso | Habilite los privilegios de acceso recomendados. |
| Recopilación de datos | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. Si selecciona esta opción, especifique los identificadores exclusivos utilizados para esta integración: <ul><li>Parámetro de cadena de consulta de ID de mensaje: Este valor representa el ID de mensaje que el socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li><li>Parámetro de cadena de consulta de ID de destinatario: Este valor representa la ID del destinatario que el socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li></ul> |
| Generación de tableros y marcadores | Generar automáticamente un tablero y marcadores para la integración. |