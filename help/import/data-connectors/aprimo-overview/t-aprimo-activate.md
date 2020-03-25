---
description: Utilice el asistente de configuración de Adobe Data Connectors para configurar la integración.
title: Activación de la integración
uuid: 0a5d2d45-5133-4259-96ce-c992a1e314ee
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Activación de la integración {#activate-the-integration}

Utilice el asistente de configuración de Adobe Data Connectors para configurar la integración.

1. Inicie [Data Connectors](https://marketing.adobe.com/resources/help/es_ES/genesis/c_overview.html) y haga clic en **[!UICONTROL + Añadir nueva]** para [agregar una nueva integración](https://marketing.adobe.com/resources/help/es_ES/genesis/t_add_integration.html).
1. En la lista **[!UICONTROL Mostrar]**, seleccione **[!UICONTROL Por nombre]** y arrastre la integración de [!DNL ~Partner~] a una ranura de complemento vacía.
1. Complete el asistente de integración con la información de la tabla siguiente:

| Campo | Descripción |
|--- |--- |
| Grupo de informes | Grupo de informes que recibe los datos de esta integración. |
| Nombre de la integración | Especifique el nombre de la integración que Data Connectors muestra en la lista de integración activa del conjunto de informes. |
| ID de cuenta | Especifique su ID de cuenta de Aprimo. |
| Recipient ID (ID de destinatario) | Este ID es una representación numérica o codificada de una dirección de correo electrónico del sistema de Aprimo. Este “ID de destinatario” está asociado al comportamiento de los visitantes que siguen el flujo de navegación en el ID del destinatario del sitio (abandonos del carro de compras, compras, etc.) que se incorpora al sistema de Aprimo y se puede aprovechar para fines de remarketing. |
| Clics | (Obligatorio) Especifique el evento de Adobe Analytics que almacena los datos de correos electrónicos en los que se hizo clic importados desde el sistema de correo electrónico. El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. |
| ID de mensaje | (Obligatorio) Almacena el ID de correo único. |
| Aperturas | (Obligatorio) Especifique el evento de Adobe Analytics que almacena los datos de aperturas a través del correo electrónico importados desde el sistema de correo electrónico. El evento de aperturas (Opened) permite ver el número de visitantes que abrieron el mensaje de correo electrónico. |
| Recipient ID (ID de destinatario) | (Obligatorio) Almacena el ID de visitante único. |
| Enviados | (Obligatorio) Especifique el evento de Adobe Analytics que almacena los datos de mensajes enviados por correo electrónico importados desde el sistema de correo electrónico. El evento de enviados (Sent) permite ver el número de mensajes de correo electrónico que se han enviado. |
| Devoluciones | (Obligatorio) Especifique el evento de Adobe Analytics que almacena los datos de devoluciones totales de correo electrónico importados del sistema de correo electrónico. El evento de devoluciones totales permite ver el número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Cancelación de suscripción | (Obligatorio) Especifique el evento de Adobe Analytics que almacena los datos de cancelación de suscripción de correo electrónico importados desde el sistema de correo electrónico. El evento de cancelación de suscripción (Unsuscribed) le permite ver el número de visitantes que abrieron el mensaje de correo electrónico y luego hicieron clic en el vínculo Cancelar suscripción para rechazar futuros mensajes de correo electrónico de su organización. |
| Segmentos | Esta integración crea los segmentos definidos por el socio que se muestran en la sección Segmentos de socio. Además, puede seleccionar segmentos existentes de nivel de grupo de informes para incluirlos en la integración. |
| Solicitudes de acceso | Habilite los privilegios de acceso recomendados. |
| Recopilación de datos | Seleccione **Complemento de JavaScript** si desea utilizar el complemento s_code.js como modelo de recopilación para esta integración. |
Seleccione **Solución automatizada** si desea utilizar un modelo de recopilación automatizada para esta integración y, a continuación, especifique los identificadores únicos utilizados para esta integración. Si selecciona esta opción, especifique los identificadores únicos utilizados para esta integración:
<ul><li>Parámetro de cadena de consulta de ID de mensaje: este valor representa el ID de mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li>
<li>Parámetro de cadena de consulta de ID de destinatario: este valor representa el ID de destinatario anexado a la dirección URL de la página de aterrizaje por su socio de correo electrónico.</li></ul>|
|Generación de paneles y marcadores|Genere automáticamente un panel y marcadores para la integración.|
