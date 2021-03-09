---
description: Descripción de los campos para el Administrador de tareas programadas.
title: Administrador de tareas programadas
topic: Creador de informes
uuid: dec259f0-2a04-4c94-abbc-5008cf2f1cb8
translation-type: tm+mt
source-git-commit: 9edb2224b711cb41552488c8d73cbce1a9577a61
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 97%

---


# Administrador de tareas programadas

El Administrador de tareas programadas le permite ver una lista de los informes programados existentes, así como sus destinatarios, detalles de la programación y formato de los archivos. También le permite reactivar libros programados que no se ejecutaron debido a algún error.

| Campo | Descripción |
| --- | --- |
| Ficha **Informes programados** |  |
| Nombre del informe | Indica el nombre de la tarea programada. |
| Correo electrónico/FTP | Dirección de correo electrónico o FTP del destinatario. **Nota:** Si el correo electrónico está seleccionado, los informes que tengan un tamaño mayor que 1 MB se adjuntan directamente al correo electrónico como un archivo .zip. Esta función no se puede desactivar y ayuda a que el tamaño de archivo siempre sea reducido. |
| Opciones de publicación | Esta columna indicará Power BI si alguna de las [opciones de publicación de Power BI](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/publish-powerbi/power-bi.html) está seleccionada. |
| Programación | Tipo de envío programado. |
| Formato del archivo | Formato de envío del informe como, por ejemplo, Excel, PDF, HTML, etc. |
| Reactivar | Cuando un libro programado no puede ejecutarse, Report Builder intenta ejecutar el libro dos veces más cada quince minutos. Tras tres intentos fallidos, Report Builder desactiva la programación y muestra el botón Reactivar. Cuando se reactiva un libro, el envío programado se reinicia desde el momento en que se desactivó.  Por ejemplo, si un libro programado se desactivó hace 14 días y se ha reactivado hoy, se ejecuta por cada día que falte y se enviará 14 veces. Si no desea que el libro se envíe los días que faltan, puede eliminar el libro programado y posteriormente crear un nuevo libro utilizando los mismos parámetros de programación.   Nota: No se debe reactivar un libro a no ser que se conozcan los motivos por el que el sistema lo desactivó. Una solución al problema consiste en descargar un libro desactivado y actualizarlo en el cliente. Si no aparecen errores, debería poder reactivarlo. |
| Enviado por última vez | La fecha y la hora en que se envió el informe por última vez. |
| Ficha **Destinatario** |  |
| Correo electrónico del destinatario | Destinatario de correo electrónico del informe. |
| Informes | El informe o informes enviados a cada destinatario. |
| Ficha **Historial de informes** |  |
| Nombre del archivo | Indica el nombre de la tarea programada. |
| Fecha | La fecha y la hora en que se envió el informe por última vez. |
| Estado | El estado indica si el informe está Enviado o No enviado. |
| Correo electrónico/FTP | La dirección de correo electrónico o FTP del destinatario del informe. |
| Formato del archivo | Formato de envío del informe como, por ejemplo, Excel, PDF, HTML, etc. |

