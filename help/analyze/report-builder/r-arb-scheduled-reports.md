---
description: Descripción de los campos para el Administrador de tareas programadas.
title: Administrador de tareas programadas
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
source-git-commit: 91d94ba33328f0ac5fba09cdafb26f58733b4d58
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 47%

---

# Administrador de tareas programadas

La variable [!UICONTROL Administrador de tareas programadas] permite ver una lista de los informes programados existentes, junto con sus destinatarios, detalles de la programación y formatos de archivo. También le permite reactivar libros programados que no se ejecutaron debido a algún error.

## Pausa de tareas programadas antiguas

**En vigor a partir del 15 de abril de 2022**, Adobe tiene la intención de poner en pausa todas las tareas de Report Builder programadas que se crearon hace más de dos años. Específicamente, esta pausa se aplica a **cualquier tarea creada antes del 31 de enero de 2020**. No se eliminarán tareas, libros ni datos. Las tareas que tengan más de dos años se pausarán y no se enviarán tareas programadas adicionales.

Cualquier tarea que desee reanudar el envío se puede reactivar. Inicie sesión en el Report Builder e inicie la [!UICONTROL Administrador de tareas programadas]. Haga clic en **[!UICONTROL Reactivar]** para la tarea programada que desea reanudar el envío. Cualquier tarea que se reactive tendrá una caducidad predeterminada de 18 meses, a menos que se elija una fecha de caducidad más corta.

Además, cualquier tarea con una fecha de creación inferior a dos años y sin fecha de caducidad actual (o con una fecha de caducidad superior a dos años) tendrá aplicada una fecha de caducidad predeterminada de 18 meses. La nueva fecha de caducidad será el 15 de octubre de 2023. Puede editar esta fecha de caducidad para que sea inferior a 18 meses, pero no buena. En el momento de la caducidad, la tarea se pone en pausa. Sin embargo, puede reactivar la tarea con una nueva fecha de caducidad de 18 meses. No se eliminarán tareas, libros ni datos.

El propósito de esta pausa es administrar y mantener de forma eficaz nuestra base de datos de tareas programadas para garantizar un rendimiento y un envío óptimos para las tareas y los libros necesarios. Esto servirá para que nuestra nueva política de gobernanza avance. A partir del 15 de abril de 2022, todas las tareas tendrán una fecha de caducidad máxima de 18 meses. Después de 18 meses, las tareas caducadas se pausarán y se pueden reactivar según sea necesario.

## Configuración de tareas programadas

| Campo | Descripción |
| --- | --- |
| Ficha **[!UICONTROL Informes programados]** |  |
| [!UICONTROL Nombre del informe] | Indica el nombre de la tarea programada. |
| [!UICONTROL Correo electrónico/FTP] | Dirección de correo electrónico o FTP del destinatario. **Nota:** Si el correo electrónico está seleccionado, los informes que tengan un tamaño mayor que 1 MB se adjuntan directamente al correo electrónico como un archivo .zip. Esta función no se puede desactivar y ayuda a que el tamaño de archivo siempre sea reducido. |
| [!UICONTROL Opciones de publicación] | Esta columna indicará la Power BI si una de las [Power BI de opciones de publicación](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/publish-powerbi/power-bi.html) está seleccionado. |
| [!UICONTROL Programación] | Tipo de envío programado. |
| [!UICONTROL Formato del archivo] | Formato de envío del informe como, por ejemplo, Excel, PDF, HTML, etc. |
| [!UICONTROL Reactivar] | Cuando un libro programado no puede ejecutarse, Report Builder intenta ejecutar el libro dos veces más cada quince minutos. Tras tres intentos fallidos, Report Builder desactiva la programación y muestra el botón Reactivar. Cuando se reactiva un libro, el envío programado se reinicia desde el momento en que se desactivó.<p>Por ejemplo, si un libro programado se desactivó hace 14 días y se ha reactivado hoy, se ejecuta por cada día que falte y se enviará 14 veces. Si no desea que el libro se envíe los días que faltan, puede eliminar el libro programado y posteriormente crear un nuevo libro utilizando los mismos parámetros de programación.<p>**Nota:** No reactive un libro a menos que conozca el motivo por el que el sistema lo desactivó. Para solucionar problemas, descargue un libro desactivado y actualícelo en el lado del cliente. Si no aparecen errores, debería poder reactivarlo. |
| [!UICONTROL Enviado por última vez] | La fecha y la hora en que se envió el informe por última vez. |
| Ficha **Destinatario** |  |
| [!UICONTROL Correo electrónico del destinatario] | Destinatario de correo electrónico del informe. |
| [!UICONTROL Informes] | Los informes que se enviaron a cada destinatario. |
| Ficha **Historial de informes** |  |
| [!UICONTROL Nombre del archivo] | Indica el nombre de la tarea programada. |
| [!UICONTROL Fecha] | La fecha y la hora en que se envió el informe por última vez. |
| [!UICONTROL Estado] | El estado indica si el informe está Enviado o No enviado. |
| [!UICONTROL Correo electrónico/FTP] | La dirección de correo electrónico o FTP del destinatario del informe. |
| [!UICONTROL Formato del archivo] | Formato de envío del informe como, por ejemplo, Excel, PDF, HTML, etc. |
