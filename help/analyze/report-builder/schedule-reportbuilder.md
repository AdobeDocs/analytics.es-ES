---
title: Programación de libros mediante Report Builder en Adobe Analytics
description: Aprenda a utilizar la función de programación en Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 40e1feb0-64bc-40e6-83cb-4a1ea7e2d0cc
source-git-commit: 9ece9f6fcebdf308b6218aa50ab78af4f75ee8e7
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 69%

---

# Programar libros compartiéndolos por correo electrónico

>[!NOTE]
>
>Además de programar libros para compartirlos por correo electrónico, como se describe en esta sección, puede programar libros para que se exporten a destinos en la nube, como se describe en [Programar libros para exportarlos a destinos en la nube](/help/analyze/report-builder/report-builder-export.md).

Después de guardar un libro y completar el análisis, puede compartir fácilmente el libro con otros integrantes del equipo mediante la función de programación. La función Programación permite crear una programación que actualice automáticamente los datos del libro y envíe el archivo .xlsx del libro de Excel como datos adjuntos a la audiencia especificada en una fecha y hora específicas. La configuración de una programación proporciona a los destinatarios actualizaciones regulares de forma automática. También puede utilizar la función de programación para enviar el libro una vez sin programar actualizaciones automáticas.

Puede crear varias programaciones para un solo libro. Por ejemplo, puede enviar un libro a su equipo diariamente y enviarlo al administrador una vez a la semana creando dos programaciones diferentes.

La función Programación también permite configurar la protección con contraseña para un libro y editar los libros programados previamente.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Programar libros](https://video.tv.adobe.com/v/3417503?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Programar un libro

Utilice el botón Programar del concentrador de Report Builder para crear rápidamente una programación de modo que pueda distribuir automáticamente un archivo de Excel de libro (.xlsx) a un individuo o grupo.

1. Haga clic en el botón Programar en el centro del Report Builder.

   ![Haga clic en el botón Programar para crear una programación.](./assets/schedule-button.png){width="55%"}

1. Haga clic en Programar libro o en el botón de signo más en la parte superior izquierda para crear un nuevo libro programado.

   ![Ventana Programar libros.](./assets/schedule-workbook.png){width="55%"}

   El panel de programación muestra información predefinida sobre el libro, como el nombre del libro y la última fecha de modificación del libro.

   ![Panel de programación.](./assets/schedule-pane.png){width="55%"}

1. (Opcional) Introduzca un nombre de archivo.

   El nombre de archivo del libro es el nombre predeterminado del libro, pero puede cambiarlo, si quiere. Si envía el mismo libro a varias audiencias y desea ponerle un nombre un poco más descriptivo para una audiencia determinada, puede cambiar el nombre.

1. (Opcional) Seleccione **Adjuntar marca temporal al nombre del archivo**.

   Puede adjuntar una marca temporal al nombre del archivo para identificar la fecha en que se actualizó el libro. Esto resulta útil para ver rápidamente qué versión de un libro se envió en una fecha específica. La **Vista previa del nombre de archivo** muestra cómo aparecerá el nombre del archivo del libro en el correo electrónico cuando se distribuya el libro. El formato de la marca temporal es AAAA-MM-DD.

1. (Opcional) Seleccione **Compresión .zip** para comprimir el archivo y configurar la protección con contraseña en el archivo.

   Cuando realice esta selección, se le pedirá que introduzca una contraseña para abrir el archivo. Esto resulta útil si le preocupa la seguridad de los datos y desea proteger el libro con contraseña. La protección del archivo con una contraseña requiere que seleccione **Compresión .zip**. La contraseña debe tener al menos ocho caracteres y contener un número y un carácter especial.

   ![Escriba una contraseña en el campo Proteger el libro con contraseña.](./assets/zip-compression.png){width="55%"}

1. Introduzca los **Destinatarios**. Puede introducir el nombre de una persona reconocida en su organización, o una dirección de correo electrónico de una persona interna o externa de la organización.

1. Introduzca el **Asunto** del correo electrónico y una descripción para sus destinatarios. El asunto adopta como valor predeterminado el nombre de archivo del libro, pero puede modificarlo si es necesario. Puede agregar detalles en la sección de descripción.

   ![Escriba un asunto en el campo Asunto.](./assets/recipients-subject.png){width="55%"}

1. Configure las opciones de programación para establecer la fecha y la hora en que desea que el libro se envíe por correo electrónico a los destinatarios.

   Elija los intervalos de fecha y hora de inicio y fin. Puede ser la fecha de hoy o una fecha futura.

   Elija la **Frecuencia** en el menú desplegable. Puede establecer que la frecuencia sea horaria, diaria, semanal, mensual o anual en un día específico. Por ejemplo, puede configurar una programación para enviar el libro el primer domingo por la noche del mes de modo que los destinatarios tengan el correo electrónico en su bandeja de entrada el lunes por la mañana.

   ![Seleccione la frecuencia para programar el informe.](./assets/frequency.png){width="55%"}

1. Después de configurar la programación, haga clic en **Enviar según lo programado**.

   ![Haga clic en Enviar según lo programado.](./assets/send-on-schedule.png){width="55%"}

   Verá un mensaje de confirmación en la parte inferior de Report Builder hub y el libro programado se mostrará en la pestaña Libros.

   ![Mensaje de confirmación](./assets/confirmation-toast.png){width="55%"}

## Programar un libro convertido {#converted}

1. Programar un libro heredado [convertido](/help/analyze/report-builder/convert-workbooks.md).

   Aparece una ventana emergente que le pregunta si desea utilizar la métrica de programación del libro de trabajo heredado para crear una nueva tarea programada.

1. Si selecciona **[!UICONTROL Usar]**, Report Builder rellena automáticamente la información de programación heredada.

1. Asegúrese de que esta información es correcta y programe.

1. Si desea enviar el libro en una programación diferente, programe una tarea programada completamente nueva.


## Enviar el libro solo una vez

También puede enviar el libro solo una vez.

1. Desmarque **Mostrar opciones de programación**.

   ![Haga clic en Desmarcar Mostrar opciones de programación para enviar un libro una vez.](./assets/send-now.png){width="40%"}

1. Haga clic en **Enviar ahora**.

## Administrar libros programados

Para obtener información acerca de la administración de libros que ya están programados, vea [Administrar libros programados](/help/analyze/report-builder/manage-schedules-reportbuilder.md).
