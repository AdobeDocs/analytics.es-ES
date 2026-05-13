---
description: Obtenga información acerca de las descripciones de los campos del Administrador de tareas programadas.
title: Acerca del Administrador de tareas programadas
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
TQID: https://experienceleague.adobe.com/bH-sAinp0Hf0X9qesfrJMIUYdDqjrev5Hd7mRpihDLM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 788
ht-degree: 80%

---

# Administrador de tareas programadas

{{legacy-arb}}

El [!UICONTROL Administrador de tareas programadas] le permite ver una lista de los informes programados existentes, así como sus destinatarios, detalles de la programación y formato de los archivos. También le permite reactivar libros programados que no se ejecutaron debido a algún error.

## Pausa de tareas programadas antiguas

El 21 de abril de 2022, implementamos cambios en las tareas programadas en Report Builder como parte de nuestros esfuerzos de optimización de rendimiento y entrega. Estos cambios incluían la eliminación de la capacidad de que los envíos programados “terminen después de x incidencias”. En respuesta a varias solicitudes de clientes que buscan más tiempo para explorar e implementar alternativas, hemos decidido restaurar esta opción de forma limitada hasta el **31 de enero de 2023**.

Podrá programar tareas de Report Builder por hora y hacer que finalicen después de un máximo de 99 incidencias. Tenga en cuenta que la reversión solo se aplica a tareas por hora; el evento “terminar después de x incidencias” permanecerá no disponible para todos los demás intervalos de entrega (diario, semanal, mensual y anual).

Tenga en cuenta que esta opción se retiró el 31 de enero de 2023.
Para obtener más información o ayuda, póngase en contacto con el Servicio de atención al cliente de Adobe.

Específicamente, esta pausa se aplica a **cualquier tarea creada antes del 31 de enero de 2020**. No se eliminarán tareas, libros ni datos. Las tareas que tengan más de dos años se pausarán y no se enviarán tareas programadas adicionales.

Cualquier tarea que cuyo envío desee reanudar se puede reactivar. Inicie sesión en Report Builder y lance el [!UICONTROL Administrador de tareas programadas]. Haga clic en **[!UICONTROL Reactivar]** para la tarea programada cuyo envío desea reanudar. Cualquier tarea que se reactive tendrá una caducidad predeterminada de 18 meses, a menos que se elija una fecha de caducidad más corta.

Además, cualquier tarea con una fecha de creación inferior a dos años y sin fecha de caducidad actual (o superior a dos años) tendrá aplicada una fecha de caducidad predeterminada de 18 meses. La nueva fecha de caducidad será el 15 de octubre de 2023. Puede editarla para que sea inferior a 18 meses, pero no superior. En el momento de la caducidad, la tarea se pone en pausa. Sin embargo, puede reactivarla con una nueva fecha de caducidad de 18 meses. No se eliminarán tareas, libros ni datos.

El propósito de esta pausa es administrar y mantener de forma eficaz nuestra base de datos de tareas programadas para garantizar un rendimiento y un envío óptimos para las tareas y los libros necesarios. Esto servirá para que nuestra nueva política de gobernanza avance. A partir del 31 de enero de 2023, todas las tareas tendrán una fecha de caducidad máxima de 18 meses. Después de 18 meses, las tareas caducadas se pausarán y se podrán reactivar según sea necesario.

## Configuración de tareas programadas

| Campo | Descripción |
| --- | --- |
| **[!UICONTROL Pestaña Informes programados]** | |
| [!UICONTROL Nombre del informe] | Indica el nombre de la tarea programada. |
| [!UICONTROL Correo electrónico/FTP] | La dirección de correo electrónico o FTP del destinatario. **Nota:** Si el correo electrónico está seleccionado, los informes de más de 1 MB se adjuntan automáticamente al correo electrónico como un archivo .zip. Esta función no se puede desactivar y ayuda a que el tamaño de archivo siempre sea reducido. |
| [!UICONTROL Opciones de publicación] | Esta columna indicará Power BI si una de las [opciones de publicación de Power BI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) está seleccionada. |
| [!UICONTROL Programación] | El tipo de envío programado. |
| [!UICONTROL Formato del archivo] | El formato de envío del informe como, por ejemplo, Excel, PDF, HTML, etc. |
| [!UICONTROL Reactivar] | Cuando un libro programado no puede ejecutarse, Report Builder intenta ejecutarlo dos veces más cada quince minutos. Tras tres intentos fallidos, Report Builder desactiva la programación y muestra el botón Reactivar. Cuando se reactiva un libro, la entrega programada se reinicia desde el momento en que se desactiva.<p>Por ejemplo, si un libro programado se desactivó hace 14 días y lo reactiva hoy, se ejecuta para cada día que falta y se enviará 14 veces. Si no desea que el libro se envíe en los días que faltan, puede eliminar el libro programado y, a continuación, crear un nuevo libro programado utilizando los mismos parámetros de programación.<p>**Nota:** No reactive un libro a no ser que se conozcan los motivos por el que el sistema lo desactivó. Para solucionar problemas, descargue un libro desactivado y actualícelo en el lado del cliente. Si no aparecen errores, debería poder reactivarlo. |
| [!UICONTROL Enviado por última vez] | La fecha y la hora en que se envió el informe por última vez. |
| **Pestaña de destinatario** | |
| [!UICONTROL Correo electrónico del destinatario] | El destinatario de correo electrónico del informe. |
| [!UICONTROL Informes] | Los informes enviados a cada destinatario. |
| **Pestaña Historial de informes** | |
| [!UICONTROL Nombre del archivo] | Indica el nombre de la tarea programada. |
| [!UICONTROL Fecha] | La fecha y la hora en que se envió el informe por última vez. |
| [!UICONTROL Estado] | El estado indica si el informe está Enviado o No enviado. |
| [!UICONTROL Correo electrónico/FTP] | La dirección de correo electrónico o FTP del destinatario del informe. |
| [!UICONTROL Formato del archivo] | El formato de envío del informe como, por ejemplo, Excel, PDF, HTML, etc. |
