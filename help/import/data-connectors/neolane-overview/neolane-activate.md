---
description: Utilice el Asistente para la configuración de Conectores de datos de Adobe para configurar la integración.
seo-description: Utilice el Asistente para la configuración de Conectores de datos de Adobe para configurar la integración.
seo-title: Activar la integración
title: Activar la integración
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
translation-type: tm+mt
source-git-commit: 34b18e7769e0850283fd3840c2557818d5d742f0

---


# Activar la integración{#activate-the-integration}

Utilice el Asistente para la configuración de Conectores de datos de Adobe para configurar la integración.

1. Inicie Conectores [de datos](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) y haga clic en **[!UICONTROL + Agregar nuevo]** para [agregar una nueva integración](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. En la lista **[!UICONTROL Mostrar]** , seleccione **[!UICONTROL Por nombre]** y arrastre la integración de [!DNL ~socio~] a una ranura de complemento vacía.
1. Complete el Asistente para integración con la información de la tabla siguiente:

| Campo | Descripción |
|--- |--- |
| Grupo de informes | Grupo de informes que recibe los datos de esta integración. |
| Nombre de la integración | Especifique el nombre de la integración que Data Connectors muestra en la Lista de integración activa del conjunto de informes. |
| Clic | Número total de clics en correos electrónicos. |
| ID de campaña | Almacena el ID exclusivo del mensaje. Esto generalmente se almacena en la variable de campaña. |
| Abierto | Número total de aperturas de correo electrónico. |
| Clics de personas | Número de personas que han hecho clic. |
| Procesado | Número total de correos electrónicos procesados. |
| Broadlog ID | Este ID es una representación numérica o codificada de una dirección de correo electrónico del sistema Neolane. Esta "ID de Broadlog" está asociada con el comportamiento de los visitantes que bajan del canal en el sitio (abandonos, compras, etc. del ID de Broadlog del carro de compras) que se incorpora al sistema Neolane y puede aprovecharse para fines de remercadotecnia. |
| Programado | Número de mensajes de correo electrónico programados para su envío. |
| Enviado | Número de mensajes de correo electrónico enviados. |
| Devoluciones totales | Número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Clics únicos | Número de clics distintos. |
| Unique Opens | Número de aperturas distintas. |
| Unsubscribed | Number of visitors who opened the email message but then clicked the Unsubscribe link to opt-out of future email messages from your organization. |
| Segmentos | This integration creates the partner-defined segments displayed in the Partner Segments section. Additionally, you can select existing Report Suite-Level segments to include in the integration. |
| Access Requests | Enable the recommended access privileges. |
| Recopilación de datos | Select JavaScript Plug-in if you want to use the s_code.js plug-in as the collection model for this integration. **** Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. Si selecciona esta opción, especifique los identificadores únicos utilizados para esta integración: <ul><li>Parámetro de cadena de consulta de ID del mensaje: Este valor representa el ID del mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li><li>Parámetro de cadena de consulta de ID del destinatario: Este valor representa la ID del destinatario anexada a la URL de la página de aterrizaje por su socio de correo electrónico.</li></ul> |
| Generación de tableros y marcadores | Genere automáticamente un tablero y marcadores para la integración. |
