---
description: Puede descargar proyectos guardados y sin guardar en los formatos PDF y CSV.
title: Descarga de archivos PDF o CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Descarga de archivos PDF o CSV

Puede descargar proyectos guardados y sin guardar en los formatos PDF y CSV.

El nombre del archivo PDF o CSV coincide con el nombre actual del proyecto. En el caso de proyectos sin guardar, el archivo descargado incluye los cambios sin guardar en el proyecto. Tenga en cuenta que no puede programar proyectos no guardados en PDF o CSV.

> [!NOTE] También se admite la visualización de abandonos en formato CSV.

> [!NOTE] Cuando procesamos un proyecto en PDF, solo procesamos lo que figura en la página. Si un proyecto tiene paneles y visualizaciones de tamaño personalizado, deberá cambiarlos a tamaño automático (mediante el botón que hay en la esquina superior derecha) para que no se trunque el contenido.

1. Cree o abra un proyecto.
1. Haga clic en **[!UICONTROL Proyecto]** &gt; **[!UICONTROL Descargar CSV (o Descargar PDF).]**

A partir del 11 de abril de 2019, se han aplicado varios cambios en las **[!CSV descargas de]** (y en **[!CCopiar al Portapapeles]**) desde Analysis Workspace para eliminar el formato de los datos exportados.
* El separador de miles ya no se incluye. (Se seguirá incluyendo el separador decimal y se respetará el formato definido dentro de **[!UICONTROL Componentes &gt; Configuración de informes &gt; Separador de miles]**).
* No se muestran símbolos de moneda.
* No se muestran símbolos de porcentaje.
* Los porcentajes están en forma decimal. Por ejemplo, el 75% se representa como 0,75.
* El tiempo se muestra en segundos.
* Las tablas de cohorte solo muestran valores sin procesar y se eliminan los porcentajes.
* Si un número no es válido, se mostrará una celda vacía.

>[!Nota:]
>
> Los valores numéricos que utilizan una coma como separador decimal seguirán citados en el CSV exportado.
