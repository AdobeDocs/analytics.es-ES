---
description: Utilice el Asistente para la configuración de Conectores de datos de Adobe para configurar la integración.
seo-description: Utilice el Asistente para la configuración de Conectores de datos de Adobe para configurar la integración.
seo-title: Activar la integración
title: Activar la integración
uuid: 3b2acdb8-9a1f-4f17-92f2-6a3780a8f626
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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
| Dirección de correo electrónico | Proporcione una dirección de correo electrónico para recibir información relacionada con la integración. |
| ID de cuenta | Identificador exclusivo que su proveedor de servicios de correo electrónico le asigna a su organización. Se utilizará al solicitar datos de campaña de correo electrónico (p. ej. # Enviado, # Abierto, # Clic, etc.) y enviar segmentos de visitantes a su proveedor de servicios de correo electrónico. |
| Recipient ID | Este ID es una representación numérica o codificada de una dirección de correo electrónico del sistema de correo electrónico de optivo®. Esta "ID del destinatario" está asociada con el comportamiento de los visitantes que bajan del flujo en el sitio (abandonos del carro de compras, compras, etc.) que se introduce en el sistema de radio y televisión optivo® y se puede aprovechar para fines de remercadotecnia. |
| ID del mensaje | (Requerido) Almacena el identificador de correo único. Estas dimensiones de clasificación las crea el asistente de Data Connectors para el ID del mensaje: <br>a)**Campañas**: Campañas asociadas al mensaje. <br>b)**Canal**: El canal de transmisión, es constantemente "optivo Broadmail". <br>c)**Código** del país: Este campo contiene el código de país del país remitente del origen. Es una constante "DE". <br>d) **Herramienta** de entrega: Método de transmisión, siempre "Correo electrónico".<br> e) Nombre **del** mensaje: El nombre del correo, tal como está configurado en optivo® Broadmail. <br>f) Fecha **inicial**: Marca de hora del inicio de este correo. |
| Hora del anuncio | (Requerido) Esto es necesario para transmitir información sobre una acción del destinatario al correo de radio de optivo® después de que el destinatario haga clic en un vínculo en un correo. |
| Producto de postclic | (Requerido) Esto es necesario para transmitir información sobre una acción del destinatario al correo de radio de optivo® después de que el destinatario haga clic en un vínculo en un correo. |
| Acción de postclic | (Requerido) Esto es necesario para transmitir información sobre una acción del destinatario al correo de radio de optivo® después de que el destinatario haga clic en un vínculo en un correo. |
| Rebotar | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de devoluciones en bruto importados desde el sistema de correo electrónico. Número de mensajes de correo electrónico que no se entregaron a los destinatarios y que se consideran permanentemente inentregables. |
| Rebote suave | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de devoluciones en pantalla importados desde el sistema de correo electrónico. Número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Clic | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de correo electrónico en los que se hizo clic importados desde el sistema de correo electrónico. El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. |
| Abierto | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos abiertos por correo electrónico importados del sistema de correo electrónico. El evento Abrir permite ver el número de visitantes que abrieron el mensaje de correo electrónico. |
| Enviado | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos enviados por correo electrónico importados del sistema de correo electrónico. El evento Enviado permite ver el número de mensajes de correo electrónico que se han enviado. |
| No suscrito | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de cancelación de suscripción de correo electrónico importados del sistema de correo electrónico. El evento Cancelar suscripción le permite ver el número de visitantes que abrieron el mensaje de correo electrónico y luego hicieron clic en el vínculo Cancelar suscripción para rechazar futuros mensajes de correo electrónico de su organización. |
| Segmentos | Habilite los segmentos existentes para usarlos junto con esta integración (opcional). |
|  Solicitudes de acceso | Habilite los privilegios de acceso recomendados. |
| Recopilación de datos | Seleccione **JavaScript Plug-in** si desea utilizar el complemento s_code.js como modelo de recopilación para esta integración. Seleccione Solución **** automatizada si desea utilizar un modelo de recopilación automatizada para esta integración y, a continuación, especifique los identificadores únicos utilizados para esta integración. Si selecciona esta opción, especifique los identificadores únicos utilizados para esta integración:<ul><li>Parámetro de cadena de consulta de ID del mensaje: Este valor representa el ID del mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li><li>Parámetro de cadena de consulta de ID del destinatario: Este valor representa la ID del destinatario anexada a la URL de la página de aterrizaje por su socio de correo electrónico.</li></ul> |
| Generación de tableros y marcadores | Genere automáticamente un tablero y marcadores para la integración. |