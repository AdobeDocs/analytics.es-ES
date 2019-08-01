---
description: Use el Asistente para la configuración de Data Connectors de Adobe para configurar la integración.
seo-description: Use el Asistente para la configuración de Data Connectors de Adobe para configurar la integración.
seo-title: Activar la integración
title: Activar la integración
uuid: 9084 b 691-291 d -49 f 7-9 fa 4-abda 507 e 060 d
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
| UUID de integración | Especifique el UUID de integración de dreammail. |
| Nombre del cliente | Especifique el nombre del cliente de dreammail. |
| Nombre del sitio | Especifique el nombre del sitio de dreammail. |
| Devoluciones devoluciones | Número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Entregado | Número de envíos de mensajes correctos. |
| Errores de entrega | Envíos fallidos de mensajes. |
| HTML Aperturas | Número de visitantes que abrieron el mensaje de correo electrónico. |
| Invidentes | Número de direcciones de correo electrónico no válidas. |
| Campaign | ID de campaña de marketing. |
| Pasar puntos | El evento Clics permite ver la cantidad de visitantes que hicieron clic en el mensaje de correo electrónico. |
| Email eVar | Una dirección de correo electrónico del sistema dreammail. Esta "evar de correo electrónico" está asociada con el comportamiento de los visitantes en línea en el sitio (abandonos del carro, compras, etc.) que se extraen al sistema de dreammail y se pueden aprovechar para fines de remercadotecnia. |
| Evento destacado | Evento que se puede exportar en segmentos de remarketing. |
| Compras destacadas | Evento que se puede exportar en segmentos de remarketing. |
| Valor destacado | Evento de ingresos que se puede exportar en segmentos de remarketing. |
| Totalclicks | El evento Clics permite ver la cantidad de visitantes que hicieron clic en el mensaje de correo electrónico. |
| Segmentos | Esta integración crea los segmentos definidos por el socio que se muestran en la sección Segmentos de socio. Además, puede seleccionar segmentos existentes de nivel de grupo de informes para incluirlos en la integración. |
| Solicitudes de acceso | Habilite los privilegios de acceso recomendados. |
| Recopilación de datos | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration (see ). Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. Si selecciona esta opción, especifique los identificadores exclusivos utilizados para esta integración:<ul><li>Parámetro de cadena de consulta de ID de mensaje: Este valor representa el ID de mensaje que el socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li><li>Parámetro de cadena de consulta de ID de destinatario: Este valor representa la ID del destinatario que el socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li></ul> |
| Generación de tableros y marcadores | Generar automáticamente un tablero y marcadores para la integración. |