---
description: Utilice el asistente de configuración de Adobe Data Connectors para configurar la integración.
title: Activación de la integración
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Activación de la integración {#activate-the-integration}

Utilice el asistente de configuración de Adobe Data Connectors para configurar la integración.

1. Start [Data Connectors](https://docs.adobe.com/content/help/en/analytics/import/dataconnectors/getting-started-data-connectors.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://docs.adobe.com/content/help/en/analytics/import/dataconnectors/getting-started-data-connectors.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Complete el asistente de integración con la información de la tabla siguiente:

| Campo | Descripción |
|--- |--- |
| Grupo de informes | Grupo de informes que recibe los datos de esta integración. |
| Nombre de la integración | Especifique el nombre de la integración que Data Connectors muestra en la lista de integración activa del conjunto de informes. |
| Clics | Número total de clics en correos electrónicos. |
| ID de campaña | Guarda el ID exclusivo del mensaje. Generalmente se almacena en la variable de campaña. |
| Aperturas | Número total de aperturas del correo electrónico. |
| Clics de personas | Número de personas que han hecho clic. |
| Procesados | Número total de correos electrónicos procesados. |
| ID de Broadlog | Este ID es una representación numérica o codificada de una dirección de correo electrónico del sistema de Neolane. Este “ID de Broadlog” está asociado con el comportamiento de los visitantes que siguen el flujo en el sitio (abandonos, compras, etc. del ID de Broadlog del carro de compras, etc.) que se incorpora al sistema de Neolane y puede aprovecharse para fines de remarketing. |
| Programado | Número de mensajes de correo electrónico programados para su envío. |
| Enviados | Número de mensajes de correo electrónico enviados. |
| Devoluciones totales | Número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Clics únicos | Número de clics distintos. |
| Aperturas únicas | Número de aperturas distintas. |
| Cancelación de suscripción | Número de visitantes que abrieron el mensaje de correo electrónico y luego hicieron clic en el vínculo Cancelar suscripción para desactivar futuros mensajes de correo electrónico de su organización. |
| Segmentos | Esta integración crea los segmentos definidos por el socio que se muestran en la sección Segmentos de socio. Además, puede seleccionar segmentos existentes de nivel de grupo de informes para incluirlos en la integración. |
| Solicitudes de acceso | Habilite los privilegios de acceso recomendados. |
| Recopilación de datos | Seleccione **Complemento de JavaScript** si desea utilizar el complemento s_code.js como modelo de recopilación para esta integración. Seleccione **Solución automatizada** si desea utilizar un modelo de recopilación automatizada para esta integración y, a continuación, especifique los identificadores únicos utilizados para esta integración. Si selecciona esta opción, especifique los identificadores únicos utilizados para esta integración: <ul><li>Parámetro de cadena de consulta de ID de mensaje: este valor representa el ID de mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li><li>Parámetro de cadena de consulta de ID de destinatario: este valor representa el ID de destinatario anexado a la dirección URL de la página de aterrizaje por su socio de correo electrónico.</li></ul> |
| Generación de paneles y marcadores | Genere automáticamente un panel y marcadores para la integración. |
