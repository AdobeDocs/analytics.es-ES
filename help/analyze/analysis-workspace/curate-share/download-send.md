---
description: Puede descargar proyectos guardados y sin guardar en los formatos PDF y CSV.
seo-description: Puede descargar proyectos guardados y sin guardar en los formatos PDF y CSV.
seo-title: Descarga de archivos PDF o CSV
title: Descarga de archivos PDF o CSV
uuid: 8 af 5 f 3 d 7-5870-4 ed 6-8 a 9 f-ef 290 a 48 ef 5 f
translation-type: tm+mt
source-git-commit: b9e57162fae605719d7d85aad52a29165cb63fe4

---


# Descarga de archivos PDF o CSV

Puede descargar proyectos guardados y sin guardar en los formatos PDF y CSV.

El nombre del archivo PDF o CSV coincide con el nombre actual del proyecto. En el caso de proyectos sin guardar, el archivo descargado incluye los cambios sin guardar en el proyecto. Tenga en cuenta que no puede programar proyectos no guardados en PDF o CSV.

>[!NOTE]
>
>También es compatible con la visualización de visitas en el orden previsto en formato CSV.

>[!NOTE]
>
>Cuando procesamos un proyecto en PDF, solo procesamos lo que se encuentra en la página. Si un proyecto tiene paneles y visualizaciones de tamaño personalizado, deberá cambiarlos a tamaño automático (mediante el botón que hay en la esquina superior derecha) para que no se trunque el contenido.

1. Cree o abra un proyecto.
1. Click **[!UICONTROL Project]** &gt; **[!UICONTROL Download CSV (or Download PDF).]**

On April 11, 2019, several changes were made to **[!CSV downloads]** (and **[!Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* El separador de miles ya no se incluye. (Se seguirá incluyendo el separador decimal y se respetará el formato definido dentro de **[!UICONTROL Componentes &gt; Configuración de informes &gt; Separador de miles]**).
* No se muestran símbolos de moneda.
* No se muestran símbolos porcentuales.
* Los porcentajes están en forma decimal; Por ejemplo: el 75% se representa como 0,75.
* La hora se muestra en segundos.
* Las tablas de cohorte solo muestran valores sin procesar; se eliminan los porcentajes.
* Si un número no es válido, se muestra una celda vacía.

>[!Note:]
>
> Los valores numéricos que utilizan una coma como separador decimal seguirán apareciendo en el CSV exportado.