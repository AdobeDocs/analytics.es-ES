---
description: Utilice el Asistente para la configuración de Conectores de datos de Adobe para configurar la integración.
seo-description: Utilice el Asistente para la configuración de Conectores de datos de Adobe para configurar la integración.
seo-title: Activar la integración
title: Activar la integración
uuid: 0a5d2d45-5133-4259-96ce-c992a1e314ee
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Activar la integración {#activate-the-integration}

Utilice el Asistente para la configuración de Conectores de datos de Adobe para configurar la integración.

1. Inicie Conectores [de datos](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) y haga clic en **[!UICONTROL + Agregar nuevo]** para [agregar una nueva integración](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. En la lista **[!UICONTROL Mostrar]** , seleccione **[!UICONTROL Por nombre]** y arrastre la integración de [!DNL ~socio~] a una ranura de complemento vacía.
1. Complete el Asistente para integración con la información de la tabla siguiente:

| Campo | Descripción |
|--- |--- |
| Grupo de informes | Grupo de informes que recibe los datos de esta integración. |
| Nombre de la integración | Especifique el nombre de la integración que Data Connectors muestra en la Lista de integración activa del conjunto de informes. |
| ID de cuenta | Especifique su ID de cuenta Aprimo. |
| Recipient ID | Este ID es una representación numérica o codificada de una dirección de correo electrónico del sistema Aprimo. Esta "ID del destinatario" está asociada con el comportamiento de los visitantes que siguen el flujo en el sitio ID del destinatario (abandonos del carro de compras, compras, etc.) que se incorpora al sistema Aprimo y se puede aprovechar para fines de remercadotecnia. |
| Clic | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de correo electrónico en los que se hizo clic importados desde el sistema de correo electrónico. El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. |
| ID del mensaje | (Requerido) Almacena el identificador de correo único. |
| Abierto | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de correo electrónico abiertos importados del sistema de correo electrónico. El evento Abrir permite ver el número de visitantes que abrieron el mensaje de correo electrónico. |
| Recipient ID | (Requerido) Almacena el ID de visitante único. |
| Enviado | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de correo electrónico enviados importados del sistema de correo electrónico. El evento Enviado permite ver el número de mensajes de correo electrónico que se han enviado. |
| Devoluciones | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de Devoluciones totales importados desde el sistema de correo electrónico. El evento Devoluciones totales permite ver el número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| No suscrito | (Requerido) Especifique el evento de Adobe Analytics que almacena los datos de cancelación de suscripción del correo electrónico importados del sistema de correo electrónico. El evento Cancelar suscripción le permite ver el número de visitantes que abrieron el mensaje de correo electrónico y luego hicieron clic en el vínculo Cancelar suscripción para rechazar futuros mensajes de correo electrónico de su organización. |
| Segmentos | Esta integración crea los segmentos definidos por el socio que se muestran en la sección Segmentos del socio. Además, puede seleccionar segmentos existentes de nivel de grupo de informes para incluirlos en la integración. |
|  Solicitudes de acceso | Habilite los privilegios de acceso recomendados. |
| Recopilación de datos | Seleccione **JavaScript Plug-in** si desea utilizar el complemento s_code.js como modelo de recopilación para esta integración. |
Seleccione Solución **** automatizada si desea utilizar un modelo de recopilación automatizada para esta integración y, a continuación, especifique los identificadores únicos utilizados para esta integración. Si selecciona esta opción, especifique los identificadores únicos utilizados para esta integración:
<ul><li>Parámetro de cadena de consulta de ID del mensaje: Este valor representa el ID del mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li>
<li>Parámetro de cadena de consulta de ID del destinatario: Este valor representa la ID del destinatario anexada a la URL de la página de aterrizaje por su socio de correo electrónico.</li></ul>||Generación de tableros y marcadores|Genera automáticamente un tablero y marcadores para la integración.|
