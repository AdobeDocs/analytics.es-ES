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
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Activar la integración{#activate-the-integration}

Use el Asistente para la configuración de Data Connectors de Adobe para configurar la integración.

1. Inicie [Conectores de datos](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) y haga clic **[!UICONTROL en + Agregar nuevo]** para [agregar una nueva integración](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. En **[!UICONTROL la]** lista Mostrar, seleccione **[!UICONTROL Por nombre]** y arrastre la integración [!DNL ~de socio~] a un espacio de complemento vacío.
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
| Recopilación de datos | Seleccione **el complemento JavaScript** si desea utilizar el complemento s_ code. js como modelo de recopilación para esta integración (véase). Seleccione **Solución automatizada** si desea utilizar un modelo de recopilación automatizado para esta integración y, a continuación, especifique los identificadores únicos utilizados para esta integración. Si selecciona esta opción, especifique los identificadores exclusivos utilizados para esta integración:<ul><li>Parámetro de cadena de consulta de ID de mensaje: Este valor representa el ID de mensaje que el socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li><li>Parámetro de cadena de consulta de ID de destinatario: Este valor representa la ID del destinatario que el socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li></ul> |
| Generación de tableros y marcadores | Generar automáticamente un tablero y marcadores para la integración. |