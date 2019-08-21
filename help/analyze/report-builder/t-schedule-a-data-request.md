---
description: Los informes se pueden programar para enviarlos de acuerdo al formato de archivo y la hora que se definan.
seo-description: Los informes se pueden programar para enviarlos de acuerdo al formato de archivo y la hora que se definan.
seo-title: Programar una solicitud de datos
solution: Analytics
title: Programar una solicitud de datos
topic: Creador de informes
uuid: f 6 d 8 c 90 f-e 185-4 d 60-8035-f 20 f 74 bfcd 89
translation-type: tm+mt
source-git-commit: ed8cfa41a2495c884f1096ea54624820bf3a9e07

---


# Programar libros

Puede programar libros, especificar opciones de envío avanzadas, especificar destinatarios y ver el historial de programación. Las opciones de envío avanzadas permiten configurar los libros que desea enviar a un tiempo específico o en intervalos. También puede especificar el formato de archivo en el que desea enviar el libro.

For example, you can schedule workbooks to be delivered immediately or on a recurring schedule, and specify the file format in [!DNL Advanced Delivery Options]. El límite de tamaño de archivo es de 5 MB para cargar un libro.

Additionally, after you create a workbook schedule in Report Builder, you can view and edit the schedule in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]**. (Consulte [Programación y distribución de informes](/help/analyze/reports-analytics/scheduling.md) en la ayuda de Informes y análisis).

>[!NOTE]
>
>Debe tener Excel 2007 o el paquete de compatibilidad instalado para programar un libro. Puede tener un máximo de 10 libros programados por cada licencia del Creador de informes. Sin embargo, puede aumentar este número si resta de otras licencias. To do so, go to **[!UICONTROL Admin]** &gt; **[!UICONTROL Company Settings]** &gt; **[!UICONTROL Report Builder Reports]**. Libro que se ha programado (o cargado en la biblioteca de libros) y que no se ha tocado (actualizado, reemplazado) en más de 28 meses.

>[!NOTE]
>
>La "Hora de entrega"/"Hora del día" ingresada por el usuario especifica la hora en que debe comenzar el proceso, no la hora en que se enviará. La hora real en la que se enviará el libro se basa principalmente en el tiempo que tarda en procesarse (los libros grandes y complejos tardan más en procesarse que los libros simples). Por ejemplo, si un libro tarda 15 minutos en procesarse, la hora de entrega real será de al menos 15 minutos después del "Tiempo de entrega"/"Hora del día" originalmente especificada.
>Además, hay otros factores que pueden aumentar aún más el retraso antes de que se envíe el libro:
>
> * **Al ejecutar muchas programaciones diferentes del mismo tipo al mismo tiempo** , se puede sobrecargar el sistema. El sistema de programación solo permite que algunos libros (5-10) de cualquier tipo se ejecuten de forma simultánea, por lo que cuando se programan más de 5-10 todos a la vez, algunos deberán esperar en línea para que los otros libros acaben antes de comenzar el proceso. Este problema se puede mitigar programando los libros de una empresa en horas escaladas durante el día o la hora, en lugar de hacerlo simultáneamente.
> * Además del tipo de libro específico, los libros también se esperan en línea si la empresa tiene **más de 15 a 20 de cualquier tipo de libro programado a la vez (en todos los tipos de libro)**. Esto se puede mitigar con tiempos de programación escalados en lugar de tener muchas ejecutándose al mismo tiempo.
> * **Los problemas en los servicios** de flujo descendente en los que depende el Programador también pueden afectar al envío de libros. Por ejemplo, si usa de forma independiente las API para ejecutar libros y llenar la cola de solicitud de API, los libros programados pueden entregarse lentamente mientras compite por ese recurso.
> * **La latencia del grupo de informes** (un retraso en la recopilación de datos) también puede retrasar algunos libros programados.


## Programar un libro

1. Genere y guarde un libro.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   La ficha [!UICONTROL Informes programados] resume todas las tareas que se han creado, así como el número de tareas restantes.
1. En la ficha **** Informes programados, haga clic en **[!UICONTROL Nuevo]**.
1. El Asistente de programación básico muestra:

   ![](assets/simple-schedule-wizard.png)

1. En el [!UICONTROL Asistente de programación básico], configure las siguientes opciones:

| Campo | Descripción |
|--- |--- |
| Seleccionar informe | El nombre del libro. Para los nuevos informes programados, este campo se completa con el nombre del libro activo. |
| Seleccionar | Muestra la página Seleccionar informe. Se puede seleccionar un informe del servidor (donde se almacenan todos los libros programados previamente) o del equipo local. Si se selecciona un libro de la unidad local en formato .xls, el sistema convierte el archivo a .xlsx. Como parte de la conversión, el archivo se abre en Excel y se activa. Si el libro seleccionado para el informe programado tiene el mismo nombre de archivo que el libro abierto actualmente en Excel, el sistema selecciona el archivo local en lugar del archivo cargado previamente. Si selecciona un informe desde el repositorio de programación, se crea una copia del libro en el servidor, con su nombre de archivo actualizado con 1. El informe programado recién creado utiliza el libro copiado. |
| Personalizar | Le permite personalizar el formato de fecha. |
| Para | Muestra la libreta de direcciones de Outlook, si corresponde. |
| Enviar a: Correo electrónico | Destinatario de correo electrónico del libro. |
| Enviar a: Lista de publicación | Muestra las listas de distribución disponibles para esta empresa. |
| Power BI | Consulte [Publicar libro en Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md) para obtener más información. |
| Asunto | Descripción definida por el usuario. |
| Programación | Permite especificar cuándo enviar el libro. (Inmediatamente, por hora, diariamente, semanalmente, mensualmente, trimestralmente y anualmente). |

## Opciones de envío avanzadas

1. Click **[!UICONTROL Advanced Delivery Options]** to configure file and publishing options:

| Campo | Descripción |
|--- |--- |
| Ficha **Programación** |  |
| Hora de envío | Permite programar el libro inmediatamente o para un momento posterior. La hora del día se relaciona con la zona horaria especificada en el equipo. |
| Modelo de periodicidad | Envía el libro según sus selecciones. |
| Intervalo de periodicidad | Permite especificar cuándo iniciar y detener la recepción del libro. Nota: Programar un libro el primer día de cualquier período actual (semana, mes, trimestre o año) devuelve datos únicamente para el primer día. |
| Ficha **Opciones de archivo** |  |
| Formato del archivo | Permite seleccionar un formato de envío de Excel 2007 (.xlsx) o 2003 (.xls), .pdf, .csv, .mht, .txt y .xml. |
| Destino del archivo | Especifica un correo electrónico o FTP. Las opciones de la página dependen de lo que seleccione. Para los datos de FTP, debe comprobar que el host se encuentra disponible de forma externa. |
| Lista de publicaciones | Si envía el libro programado a varias listas de publicación, el libro se ejecuta una vez para cada lista. Los grupos de informes variables se reemplazan por el grupo de informes asignado a la lista de publicación. |
| Idioma del contenido del archivo | Especifica el idioma que desea utilizar para la carta de presentación. Puede seleccionar chino (simplificado o tradicional), alemán, francés, japonés, coreano, portugués de Brasil o español. |
| Ficha **Opciones de publicación** |  |
| Publicación en Power BI | <ul><li>Publicar libro en Power BI</li><li>Publicar todas las solicitudes del Creador de informes como conjuntos de datos de Power BI</li><li>Publicar todas las tablas con formato como conjuntos de datos de Power BI</li></ul> |
| Etiquetar este informe de Power BI como | Detalles de etiquetado |

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   Report Builder displays the scheduled workbook in the [Scheduled Task Manager](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31).

