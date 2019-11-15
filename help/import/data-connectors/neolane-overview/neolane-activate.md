---
description: Utilice el Asistente para la configuración de Conectores de datos de Adobe para configurar la integración.
title: Activar la integración
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Activar la integración{#activate-the-integration}

Utilice el Asistente para la configuración de Conectores de datos de Adobe para configurar la integración.

1. Inicie Conectores [de datos](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) y haga clic en **[!UICONTROL + Agregar nuevo]** para [agregar una nueva integración](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. En la lista **[!UICONTROL Mostrar]** , seleccione **[!UICONTROL Por nombre]** y arrastre la integración de [!DNL ~socio~] a una ranura de complemento vacía.
1. Complete el Asistente para integración con la información de la tabla siguiente:

| Campo | Descripción |
|--- |--- |
| Report Suite | Grupo de informes que recibe los datos de esta integración. |
| Nombre de la integración | Especifique el nombre de la integración que Data Connectors muestra en la Lista de integración activa del conjunto de informes. |
| Clic | Número total de clics en correos electrónicos. |
| ID de campaña | Almacena el ID exclusivo del mensaje. Esto generalmente se almacena en la variable de campaña. |
| Abierto | Número total de aperturas de correo electrónico. |
| Clics de personas | Número de personas que han hecho clic. |
| Procesado | Número total de correos electrónicos procesados. |
| Broadlog ID | Este ID es una representación numérica o codificada de una dirección de correo electrónico del sistema Neolane. Esta "ID de Broadlog" está asociada con el comportamiento de los visitantes que siguen el flujo en el sitio (abandonos, compras, etc. del ID de Broadlog del carro de compras, etc.) que se incorpora al sistema Neolane y puede aprovecharse para fines de remercadotecnia. |
| Programado | Número de mensajes de correo electrónico programados para su envío. |
| Enviado | Número de mensajes de correo electrónico enviados. |
| Devoluciones totales | Número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Clics únicos | Número de clics distintos. |
| Aperturas únicas | Número de aperturas distintas. |
| No suscrito | Número de visitantes que abrieron el mensaje de correo electrónico y luego hicieron clic en el vínculo Cancelar suscripción para desactivar futuros mensajes de correo electrónico de su organización. |
| Segmentos | Esta integración crea los segmentos definidos por el socio que se muestran en la sección Segmentos del socio. Además, puede seleccionar segmentos existentes de nivel de grupo de informes para incluirlos en la integración. |
| Solicitudes de acceso | Habilite los privilegios de acceso recomendados. |
| Recopilación de datos | Seleccione **JavaScript Plug-in** si desea utilizar el complemento s_code.js como modelo de recopilación para esta integración. Seleccione Solución **** automatizada si desea utilizar un modelo de recopilación automatizada para esta integración y, a continuación, especifique los identificadores únicos utilizados para esta integración. Si selecciona esta opción, especifique los identificadores únicos utilizados para esta integración: <ul><li>Parámetro de cadena de consulta de ID del mensaje: Este valor representa el ID del mensaje que su socio de correo electrónico anexó a la dirección URL de la página de aterrizaje.</li><li>Parámetro de cadena de consulta de ID del destinatario: Este valor representa la ID del destinatario anexada a la dirección URL de la página de aterrizaje por su socio de correo electrónico.</li></ul> |
| Generación de tableros y marcadores | Genere automáticamente un tablero y marcadores para la integración. |
