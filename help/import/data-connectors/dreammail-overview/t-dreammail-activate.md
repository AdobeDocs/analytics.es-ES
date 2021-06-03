---
description: Utilice el asistente de configuración de Adobe Data Connectors para configurar la integración.
title: Activación de la integración
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
exl-id: b0d6849b-975a-4476-a2d3-36abeee12273
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 96%

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
| UUID de integración | Especifique el UUID de integración de DreamMail. |
| Nombre de cliente | Especifique el nombre del cliente de DreamMail. |
| Nombre de sitio | Especifique el nombre del sitio de DreamMail. |
| Devoluciones | Número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Entregas | Número de entregas de mensajes completadas. |
| Errores de envío | Entregas de mensajes fallidas. |
| Aperturas en HTML | Número de visitantes que abrieron el mensaje de correo electrónico. |
| No válidas | Número de direcciones de correo electrónico no válidas. |
| Campaña | ID de campaña de marketing. |
| Pase de información | El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. |
| eVar de correo electrónico | Una dirección de correo electrónico del sistema de DreamMail. Esta “eVar de correo electrónico” está asociada al comportamiento de los visitantes que siguen el flujo de navegación en el sitio (abandonos del carro de compras, compras, etc.) que se incorpora al sistema de DreamMail y se puede aprovechar para fines de remarketing. |
| Evento destacado | Evento que se puede exportar en segmentos de remarketing. |
| Compras destacadas | Evento que se puede exportar en segmentos de remarketing. |
| Valor destacado | Evento de ingresos que se puede exportar en segmentos de remarketing. |
| Clics totales | El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. |
| Segmentos | Esta integración crea los segmentos definidos por el socio que se muestran en la sección Segmentos de socio. Además, puede seleccionar segmentos existentes de nivel de grupo de informes para incluirlos en la integración. |
| Solicitudes de acceso | Habilite los privilegios de acceso recomendados. |
| Recopilación de datos | Seleccione **Complemento de JavaScript** si desea utilizar el complemento s_code.js como modelo de recopilación para esta integración (consulte ). Seleccione **Solución automatizada** si desea utilizar un modelo de recopilación automatizada para esta integración y, a continuación, especifique los identificadores únicos utilizados para esta integración. Si selecciona esta opción, especifique los identificadores únicos utilizados para esta integración:<ul><li>Parámetro de cadena de consulta de ID de mensaje: este valor representa el ID de mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li><li>Parámetro de cadena de consulta de ID de destinatario: este valor representa el ID de destinatario anexado a la dirección URL de la página de aterrizaje por su socio de correo electrónico.</li></ul> |
| Generación de paneles y marcadores | Genere automáticamente un panel y marcadores para la integración. |
