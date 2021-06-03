---
description: Utilice el asistente de configuración de Adobe Data Connectors para configurar la integración.
title: Activación de la integración
uuid: 3b2acdb8-9a1f-4f17-92f2-6a3780a8f626
exl-id: 18fb2f55-f1fb-4d97-bd1e-8c5e74dbde69
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 98%

---

# Activación de la integración {#activate-the-integration}

Utilice el asistente de configuración de Adobe Data Connectors para configurar la integración.

1. Inicie [Data Connectors](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html) y haga clic en **[!UICONTROL + Añadir nueva]** para [agregar una nueva integración](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html).
1. En la lista **[!UICONTROL Mostrar]**, seleccione **[!UICONTROL Por nombre]** y arrastre la integración de [!DNL ~Partner~] a una ranura de complemento vacía.
1. Complete el asistente de integración con la información de la tabla siguiente:

| Campo | Descripción |
|--- |--- |
| Grupo de informes | Grupo de informes que recibe los datos de esta integración. |
| Nombre de la integración | Especifique el nombre de la integración que Data Connectors muestra en la lista de integración activa del conjunto de informes. |
| Correo electrónico | Facilite una dirección de correo electrónico para recibir el informe. |
| ID de cuenta | Identificador único que su proveedor de servicios de correo electrónico asigna a su organización. Se utiliza al solicitar datos de campaña de correo electrónico (p. ej. # Enviados, # Aperturas, # Clics, etc.) y de envío de segmentos de visitantes a su proveedor de servicios de correo electrónico. |
| Recipient ID (ID de destinatario) | Este ID es una representación numérica o codificada de una dirección de correo electrónico desde el sistema de optivo® broadmail. Este “ID de destinatario” está asociado al comportamiento de los visitantes que siguen el flujo de navegación en el sitio (abandonos del carro de compras, compras, etc.) que se incorpora en el sistema de optivo® broadmail y se puede aprovechar para fines de remarketing. |
| ID de mensaje | (Obligatorio) Almacena el ID de correo único. Estas dimensiones de clasificación las crea el asistente de Data Connectors para el ID de mensaje: <br>a)**Campañas**: campañas asociadas al mensaje. <br>b)**Canal**: el canal de transmisión, que no varía de “optivo broadmail”. <br>c)**Código del país**: este campo contiene el código del país de origen del remitente. No varía de “DE”. <br>d) **Herramienta de entrega**: método de transmisión, siempre “Correo electrónico”.<br> e) **Nombre del mensaje**: el nombre del correo, tal como está configurado en optivo® broadmail. <br>f) **Fecha de inicio**: marca de hora del inicio de este correo. |
| Hora tras hacer clic | (Obligatorio) Esto es necesario para transmitir información sobre una acción del destinatario a optivo® broadmail después de que el destinatario haga clic en un vínculo en un correo. |
| Producto tras hacer clic | (Obligatorio) Esto es necesario para transmitir información sobre una acción del destinatario a optivo® broadmail después de que el destinatario haga clic en un vínculo en un correo. |
| Acción tras hacer clic | (Obligatorio) Esto es necesario para transmitir información sobre una acción del destinatario a optivo® broadmail después de que el destinatario haga clic en un vínculo en un correo. |
| Mensajes devueltos no válidos | (Obligatorio) Especifique el evento de Adobe Analytics que almacena los datos de devoluciones de mensajes no válidos importados desde el sistema de correo electrónico. Número de mensajes de correo electrónico que no se entregaron a los destinatarios y que se consideran imposibles de entregar de manera permanente. |
| Mensajes devueltos no entregados | (Obligatorio) Especifique el evento de Adobe Analytics que almacena los datos de devoluciones de mensajes no entregados importados desde el sistema de correo electrónico. Número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Clics | (Obligatorio) Especifique el evento de Adobe Analytics que almacena los datos de correos electrónicos en los que se hizo clic importados desde el sistema de correo electrónico. El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. |
| Aperturas | (Obligatorio) Especifique el evento de Adobe Analytics que almacena los datos de aperturas a través del correo electrónico importados desde el sistema de correo electrónico. El evento de aperturas (Opened) permite ver el número de visitantes que abrieron el mensaje de correo electrónico. |
| Enviados | (Obligatorio) Especifique el evento de Adobe Analytics que almacena los datos de mensajes enviados por correo electrónico importados desde el sistema de correo electrónico. El evento de enviados (Sent) permite ver el número de mensajes de correo electrónico que se han enviado. |
| Cancelación de suscripción | (Obligatorio) Especifique el evento de Adobe Analytics que almacena los datos de cancelación de suscripción de correo electrónico importados desde el sistema de correo electrónico. El evento de cancelación de suscripción (Unsuscribed) le permite ver el número de visitantes que abrieron el mensaje de correo electrónico y luego hicieron clic en el vínculo Cancelar suscripción para rechazar futuros mensajes de correo electrónico de su organización. |
| Segmentos | Habilite los segmentos existentes para usarlos junto con esta integración (opcional). |
| Solicitudes de acceso | Habilite los privilegios de acceso recomendados. |
| Recopilación de datos | Seleccione **Complemento de JavaScript** si desea utilizar el complemento s_code.js como modelo de recopilación para esta integración. Seleccione **Solución automatizada** si desea utilizar un modelo de recopilación automatizada para esta integración y, a continuación, especifique los identificadores únicos utilizados para esta integración. Si selecciona esta opción, especifique los identificadores únicos utilizados para esta integración:<ul><li>Parámetro de cadena de consulta de ID de mensaje: este valor representa el ID de mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li><li>Parámetro de cadena de consulta de ID de destinatario: este valor representa el ID de destinatario anexado a la dirección URL de la página de aterrizaje por su socio de correo electrónico.</li></ul> |
| Generación de paneles y marcadores | Genere automáticamente un panel y marcadores para la integración. |
