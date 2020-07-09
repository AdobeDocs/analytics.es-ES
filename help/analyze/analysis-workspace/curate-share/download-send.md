---
description: Puede descargar proyectos guardados y sin guardar en los formatos PDF y CSV.
title: Descarga de archivos PDF o CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 422b69a9f671bbd3c4e8f033916296cbdf7f27d9
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 61%

---


# Descarga de archivos PDF o CSV

Puede descargar proyectos guardados y sin guardar en los formatos PDF y CSV.

El nombre del archivo PDF o CSV coincide con el nombre actual del proyecto. En el caso de proyectos sin guardar, el archivo descargado incluye los cambios sin guardar en el proyecto. Tenga en cuenta que no puede programar proyectos no guardados en PDF o CSV.

Recuerde:

* También se admite la visualización de abandonos en formato CSV.
* Cuando procesamos un proyecto en PDF, solo procesamos lo que figura en la página. Si un proyecto tiene paneles y visualizaciones de tamaño personalizado, deberá cambiarlos a tamaño automático (mediante el botón que hay en la esquina superior derecha) para que no se trunque el contenido.
* Los archivos PDF descargados en el navegador pueden tardar varios minutos en exportarse. Esto se debe a que tenemos que volver a ejecutar todo el proyecto en nuestros servidores antes de procesarlo en formato PDF. Se recomienda no abandonar el proyecto hasta que el PDF se descargue en el explorador. Sin embargo, puede seguir realizando cambios en el proyecto mientras espera.
* Sabemos que si tiene proyectos de Workspace muy largos, los archivos PDF se exportan como una página gigante en lugar de como un documento paginado. Estamos trabajando en una mejora en la exportación de PDF de Workspace que permitirá la paginación.

1. Cree o abra un proyecto.
1. Haga clic en **[!UICONTROL Proyecto]** > **[!UICONTROL Descargar CSV (o Descargar PDF).]**

On April 11, 2019, several changes were made to **[!UICONTROL CSV downloads]** (and **[!UICONTROL Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* The  **[!UICONTROL Thousands Separator]** is no longer included. (Se seguirá incluyendo el separador decimal y se respetará el formato definido dentro de **[!UICONTROL Componentes > Configuración de informes > Separador de miles]**).
* No se muestran símbolos de moneda.
* No se muestran símbolos de porcentaje.
* Los porcentajes están en forma decimal. Por ejemplo, el 75% se representa como 0,75.
* El tiempo se muestra en segundos.
* Las tablas de cohorte solo muestran valores sin procesar y se eliminan los porcentajes.
* Si un número no es válido, se mostrará una celda vacía.
* No se aplica redondeo (incluso si se especifica en la métrica calculada): se muestran los valores sin procesar.

>[!Nota:]
>
> Los valores numéricos que utilizan una coma como separador decimal seguirán citados en el CSV exportado.
