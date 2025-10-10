---
title: Introducción a las fuentes de datos
description: Cargar datos de ejemplo en un grupo de informes de desarrollo.
exl-id: d9f74f55-abbb-4ceb-b4db-8d3c32aacd4a
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 0%

---

# Introducción a las fuentes de datos

Puede seguir estos pasos para cargar fácilmente datos de ejemplo en un grupo de informes de desarrollo y ver el flujo de trabajo en acción. Una vez que comprenda el proceso, puede ampliarlo y adaptarlo específicamente a la implementación de su organización.

>[!IMPORTANT]
>
>Siga estos pasos para usar un grupo de informes de prueba o desarrollo. Los datos cargados a través de fuentes de datos son **permanentes**. Afecta a los datos del grupo de informes de producción si se cargan allí.

1. Inicie sesión en Adobe Analytics mediante [https://experience.adobe.com](https://experience.adobe.com).
1. Vaya a **[!UICONTROL Administración]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Fuentes de datos]**.
1. Seleccione un grupo de informes de desarrollo mediante la lista desplegable de la parte superior derecha.
1. Haga clic en el botón **[!UICONTROL Crear]** en la parte superior izquierda.
1. En [!UICONTROL Seleccionar categoría], elija &quot;[!UICONTROL Genérico]&quot; y en [!UICONTROL Seleccionar tipo], elija &quot;[!UICONTROL Source de datos genérico (solo datos de resumen)]&quot;.
1. Haga clic en **[!UICONTROL Activar]**. Se abre una ventana emergente que muestra el [!UICONTROL Asistente para la activación de Data Source].
   1. Paso 1: Asigne un nombre al origen de datos y haga clic en la casilla de verificación de exención de responsabilidad.
   1. Paso 2: Este paso tenía más uso en versiones anteriores de Adobe Analytics. Haga clic en una casilla de verificación y, a continuación, escriba cualquier valor en el campo de texto situado junto a ella.
   1. Paso 3: Elija la métrica que desea incluir en el archivo de plantilla de fuente de datos. Seleccione &quot;Evento 1&quot; de la lista desplegable.
   1. Paso 4: Este paso tenía más uso en versiones anteriores de Adobe Analytics. Haga clic en una casilla de verificación y, a continuación, escriba cualquier valor en el campo de texto situado junto a ella.
   1. Paso 5: Elija la dimensión que desea incluir en el archivo de plantilla de fuente de datos. Seleccione &quot;eVar1&quot; en la lista desplegable.
   1. Paso 6: Revise el resumen que muestra las dimensiones y métricas que se incluyen en el archivo de plantilla.
   1. Paso 7: Haga clic en el botón **[!UICONTROL Descargar]** para descargar el archivo de plantilla de fuentes de datos. Tenga en cuenta también las credenciales de inicio de sesión en el sitio FTP, ya que se utilizan en breve.
1. La fuente de datos ya está creada; el siguiente paso es proporcionarle los datos que desea procesar. Abra el archivo descargado en el editor de texto deseado.
1. El archivo de plantilla contiene tres líneas; dos líneas de comentario (que comienzan por &quot;`#`&quot;) y una fila de encabezado:

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #    eVar1    event1
   Date    Evar 1    Event 1
   ```

1. Introduzca varias filas de datos, separando cada entrada con una pestaña. No utilice espacios ni comas para separar valores.
   * La primera columna es la fecha con el siguiente formato: `MM/DD/YYYY/HH/mm/SS`.
   * La segunda columna es el valor de texto que desea incluir en eVar1.
   * La tercera columna es la cantidad que desea aumentar en el evento 1.

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #    eVar1    event1
   Date    Evar 1    Event 1
   09/07/YYYY/11/23/00    Data source example value    3
   09/07/YYYY/15/59/00    Another data source value    18
   ```

1. Guarde el archivo. Si lo desea, puede darle un nombre de archivo diferente. Una vez guardado el archivo, puede cerrar el editor de texto.
1. En el Explorador de Windows, Finder o el cliente FTP que elija, vaya a [ftp://ftp.omniture.com](ftp://ftp.omniture.com).
1. Cuando se le soliciten credenciales de inicio de sesión, utilice el nombre de usuario y la contraseña proporcionados en el último paso del asistente para la creación de fuentes de datos. Para volver a hacer referencia a él, vaya a [!UICONTROL Fuentes de datos] y haga clic en **[!UICONTROL Información de FTP]** junto al origen de datos que creó.
1. Una vez autenticado, arrastre el archivo editado a la ventana FTP autenticado.
1. Cree un archivo de texto vacío en cualquier ubicación fuera de la ventana de FTP. Asigne el mismo nombre de archivo que el archivo de fuente de datos que ha cargado en el sitio FTP, con una excepción. En lugar de un tipo de archivo de `.txt`, asígnele un tipo de archivo de `.fin`. Asegúrese de que la configuración del sistema operativo permite ver y cambiar los tipos de archivos.
1. Arrastre el archivo `.fin` vacío a la misma ubicación FTP que el archivo de origen de datos. La presencia del archivo `.fin` indica a Adobe que el archivo de origen de datos está completamente cargado y listo para ser ingerido.
1. Después de varios minutos, el archivo desaparece de la ubicación FTP y se puede ver en los informes.
1. Actualice la página Fuentes de datos y compruebe que el archivo se ha introducido correctamente.
1. Vaya a Analysis Workspace y cree un proyecto.
1. Arrastre eVar1 como dimensión al lienzo del espacio de trabajo y evento 1 como métrica. Asegúrese de que el intervalo de fechas de Workspace incluye las fechas proporcionadas en la fuente de datos.

   ![Informe de ejemplo](assets/success-report.png)

## Pasos siguientes

[Formato de archivo](file-format.md): Conozca los detalles sobre cómo crear un archivo de fuentes de datos adaptado a su organización.
