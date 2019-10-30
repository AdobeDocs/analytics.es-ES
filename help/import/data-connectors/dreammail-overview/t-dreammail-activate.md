---
description: Utilice el Asistente para la configuración de Conectores de datos de Adobe para configurar la integración.
seo-description: Utilice el Asistente para la configuración de Conectores de datos de Adobe para configurar la integración.
seo-title: Activar la integración
title: Activar la integración
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
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
| UUID de integración | Especifique el UUID de integración de DreamMail. |
| Nombre del cliente | Especifique el nombre del cliente de DreamMail. |
| Nombre del sitio | Especifique el nombre del sitio de DreamMail. |
| Devoluciones | Número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Enviado | Número de entregas de mensajes correctas. |
| Errores de envío | Entregas de mensajes fallidas. |
| Aperturas HTML | Número de visitantes que abrieron el mensaje de correo electrónico. |
| Inválidos | Número de direcciones de correo electrónico no válidas. |
| Campaign | ID de campaña de marketing. |
| Pasar alongs | El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. |
| Email eVar | Una dirección de correo electrónico del sistema DreamMail. Esta "eVar de correo electrónico" está asociada con el comportamiento de los visitantes que bajan del flujo en el sitio (abandonos del carro de compras, compras, etc.) que se incorpora al sistema DreamMail y se puede aprovechar para fines de remercadotecnia. |
| Evento destacado | Evento que se puede exportar en segmentos de remercadotecnia. |
| Compras destacadas | Evento que se puede exportar en segmentos de remercadotecnia. |
| Valor destacado | Evento de ingresos que se puede exportar en segmentos de remercadotecnia. |
| TotalClicks | El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. |
| Segmentos | Esta integración crea los segmentos definidos por el socio que se muestran en la sección Segmentos del socio. Además, puede seleccionar segmentos existentes de nivel de grupo de informes para incluirlos en la integración. |
|  Solicitudes de acceso | Habilite los privilegios de acceso recomendados. |
| Recopilación de datos | Seleccione **JavaScript Plug-in** si desea utilizar el complemento s_code.js como modelo de recopilación para esta integración (consulte ). Seleccione Solución **** automatizada si desea utilizar un modelo de recopilación automatizada para esta integración y, a continuación, especifique los identificadores únicos utilizados para esta integración. Si selecciona esta opción, especifique los identificadores únicos utilizados para esta integración:<ul><li>Parámetro de cadena de consulta de ID del mensaje: Este valor representa el ID del mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li><li>Parámetro de cadena de consulta de ID del destinatario: Este valor representa la ID del destinatario anexada a la URL de la página de aterrizaje por su socio de correo electrónico.</li></ul> |
| Generación de tableros y marcadores | Genere automáticamente un tablero y marcadores para la integración. |