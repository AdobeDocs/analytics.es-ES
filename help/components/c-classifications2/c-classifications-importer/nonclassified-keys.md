---
description: Las claves no clasificadas se agrupan en informes de clasificación como un solo artículo de línea etiquetado como Ninguno. Puede resultar útil cambiar el nombre de Ninguno por otro más descriptivo.
seo-description: Las claves no clasificadas se agrupan en informes de clasificación como un solo artículo de línea etiquetado como Ninguno. Puede resultar útil cambiar el nombre de Ninguno por otro más descriptivo.
seo-title: Claves no clasificadas
solution: Analytics
subtopic: Clasificaciones
title: Claves no clasificadas
topic: Herramientas de administración
uuid: b 73 a 9161-0 c 6 f -4 c 8 d -900 b -54 ab 2 c 36147 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Claves no clasificadas

Las claves no clasificadas se agrupan en informes de clasificación como un solo artículo de línea etiquetado como Ninguno. Puede resultar útil cambiar el nombre de Ninguno por otro más descriptivo.

## Non-classified keys {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Las claves no clasificadas se agrupan en informes de clasificación como un solo artículo de línea etiquetado como *`None`*. It can be useful to rename *`None`* to something more descriptive.

Por ejemplo, imaginemos que los códigos de seguimiento contienen información que define el tipo de campaña móvil con el que se asocian. Se usa la clasificación (Tipo de campaña de móvil) para agrupar estos códigos de seguimiento en categorías (Web móvil, Aplicación iOS, Aplicación Android, etc.). Las campañas que no sean campañas móviles no se clasificarán con el tipo de campaña móvil. Todos los códigos de seguimiento no clasificados se agruparán como *`None`* en el informe [!UICONTROL Tipo de campaña móvil].

## Cambiar el nombre de la clave de clasificación Ninguno {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Steps that describe how to rename a non-classified key that displays as *`none`* in reporting.

1. Con el importador, exporte las clasificaciones a un archivo local.
1. Add a row to the file, and type [!DNL ~none~] in the Key column.
1. En la fila que ha agregado, escriba el nombre más descriptivo en la o las columnas de clasificación correspondientes. 

   Para continuar con el ejemplo de esta documentación, debe escribirse "campaña no móvil" en una columna denominada [!UICONTROL Nombre de campaña móvil].

   Esta entrada cambia el nombre de *`None`* en *`non-mobile campaign`* el informe [!UICONTROL Tipo] de campaña móvil.
1. [Importe los datos](../../../components/c-classifications2/c-classifications-importer/import-file.md#concept_F88785E2BDFD448CB5D1DA3491466B0D) de nuevo en el sistema.
