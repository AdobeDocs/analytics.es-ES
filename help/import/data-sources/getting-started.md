---
title: Introducción a las fuentes de datos
description: Cargue datos de ejemplo en un grupo de informes de desarrollo.
exl-id: d9f74f55-abbb-4ceb-b4db-8d3c32aacd4a
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 1%

---

# Introducción a las fuentes de datos

Puede seguir estos pasos para cargar fácilmente datos de ejemplo en un grupo de informes de desarrollo y ver el flujo de trabajo en acción. Una vez que haya comprendido el proceso, puede ampliarlo y adaptarlo en función de la implementación de su organización.

>[!IMPORTANT]
>
>Siga estos pasos utilizando un grupo de informes de desarrollo o prueba. Los datos cargados a través de fuentes de datos son **permanente**. Afecta a los datos del grupo de informes de producción si se cargan allí.

1. Inicie sesión en Adobe Analytics a través de [https://experience.adobe.com](https://experience.adobe.com).
1. Vaya a **[!UICONTROL Administrador]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Fuentes de datos]**.
1. Seleccione un grupo de informes de desarrollo con la lista desplegable de la parte superior derecha.
1. Haga clic en el **[!UICONTROL Crear]** en la parte superior izquierda.
1. En [!UICONTROL Seleccionar categoría], elija &quot;[!UICONTROL Genéricas]&quot;, y en [!UICONTROL Seleccionar tipo], elija &quot;[!UICONTROL Fuente de datos genérica (solo datos de resumen)]&quot;.
1. Haga clic en **[!UICONTROL Activar]**. Se abre una ventana emergente que muestra el [!UICONTROL Asistente para la activación de fuentes de datos].
   1. Paso 1: Asigne un nombre al origen de datos y haga clic en la casilla de verificación de exención de responsabilidad.
   1. Paso 2: Este paso ha sido más útil en versiones anteriores de Adobe Analytics. Haga clic en una casilla de verificación y, a continuación, escriba cualquier valor en el campo de texto situado junto a él.
   1. Paso 3: Elija la métrica que desea incluir en el archivo de plantilla de la fuente de datos. Seleccione &quot;Evento 1&quot; en la lista desplegable.
   1. Paso 4: Este paso ha sido más útil en versiones anteriores de Adobe Analytics. Haga clic en una casilla de verificación y, a continuación, escriba cualquier valor en el campo de texto situado junto a él.
   1. Paso 5: Elija la dimensión que desea incluir en el archivo de plantilla de la fuente de datos. Seleccione &quot;eVar1&quot; en la lista desplegable.
   1. Paso 6: Revise el resumen y muestre las dimensiones y métricas que se incluyen en el archivo de plantilla.
   1. Paso 7: Haga clic en el **[!UICONTROL Descargar]** para descargar el archivo de plantilla de fuentes de datos. Tenga en cuenta también las credenciales de inicio de sesión en el sitio FTP, ya que se utilizan en breve.
1. Se ha creado la fuente de datos; el siguiente paso es darle datos para procesar. Abra el archivo descargado en el editor de texto que desee.
1. El archivo de plantilla contiene tres líneas; dos líneas de comentario (comenzando con &quot;`#`&quot;) y una fila de encabezado:

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #    eVar1    event1
   Date    Evar 1    Event 1
   ```

1. Introduzca en varias filas de datos, separando cada entrada por una pestaña. No utilice espacios ni comas para separar valores.
   * La primera columna es la fecha con el formato siguiente: `MM/DD/YYYY/HH/mm/SS`.
   * La segunda columna es el valor de texto que desea incluir en eVar1.
   * La tercera columna es la cantidad que desea aumentar el evento 1.

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #    eVar1    event1
   Date    Evar 1    Event 1
   09/07/YYYY/11/23/00    Data source example value    3
   09/07/YYYY/15/59/00    Another data source value    18
   ```

1. Guarde el archivo. Si lo desea, puede asignarle un nombre de archivo diferente. Una vez guardado el archivo, puede cerrar el editor de texto.
1. En el Explorador de Windows, Finder o el cliente FTP que elija, vaya a [ftp://ftp.omniture.com](ftp://ftp.omniture.com).
1. Cuando se le soliciten las credenciales de inicio de sesión, utilice el nombre de usuario y la contraseña proporcionados en el último paso del asistente para la creación de fuentes de datos. Para volver a hacer referencia a ella, vaya a [!UICONTROL Fuentes de datos] y haga clic en **[!UICONTROL Información de FTP]** junto al origen de datos que ha creado.
1. Una vez autenticado, arrastre el archivo que ha editado a la ventana de FTP autenticado.
1. Cree un archivo de texto vacío en cualquier ubicación fuera de la ventana de FTP. Asigne el mismo nombre de archivo que el archivo de fuente de datos que cargó en el sitio FTP, con una excepción. En lugar de `.txt` tipo de archivo, asígnele un `.fin` tipo de archivo. Asegúrese de que la configuración del sistema operativo le permita ver y cambiar los tipos de archivo.
1. Arrastre el vacío `.fin` en la misma ubicación de FTP que el archivo de origen de datos. La presencia de `.fin` indica al Adobe que el archivo de fuente de datos está completamente cargado y listo para ser ingerido.
1. Después de varios minutos, el archivo desaparece de la ubicación del FTP y es visible en los informes.
1. Actualice la página Fuentes de datos y valide que el archivo se haya introducido correctamente.
1. Vaya a Analysis Workspace y cree un proyecto.
1. Arrastre eVar1 como dimensión al lienzo del espacio de trabajo y el evento 1 como métrica. Asegúrese de que el intervalo de fechas del espacio de trabajo incluye las fechas proporcionadas en la fuente de datos.

   ![Informe de ejemplo](assets/success-report.png)

## Pasos siguientes

[Formato del archivo](file-format.md): Conozca los detalles sobre la creación de un archivo de fuentes de datos adaptado a su organización.
