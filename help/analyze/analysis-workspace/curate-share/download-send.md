---
description: Puede descargar proyectos guardados y sin guardar en los formatos PDF y CSV.
title: Descarga de archivos PDF o CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 08d564f7fb06b94c2010515ea4a1dcbb2e6e2815

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
1. Haga clic **[!UICONTROL Project]** > **[!UICONTROL Download CSV (or Download PDF).]**

A partir del 11 de abril de 2019, se han aplicado varios cambios en las **[!CSV descargas]** (y en **[!CCopiar al Portapapeles]**) desde Analysis Workspace para eliminar el formato de los datos exportados.
* El separador de miles ya no se incluye. (The decimal separator will continue to be included, and will adhere to the format defined under **[!UICONTROL Components > Report Settings > Thousands Separator]**).
* No se muestran símbolos de moneda.
* No se muestran símbolos de porcentaje.
* Los porcentajes están en forma decimal. Por ejemplo, el 75% se representa como 0,75.
* El tiempo se muestra en segundos.
* Las tablas de cohorte solo muestran valores sin procesar y se eliminan los porcentajes.
* Si un número no es válido, se mostrará una celda vacía.

>[!Nota:]
>
> Los valores numéricos que utilizan una coma como separador decimal seguirán citados en el CSV exportado.
