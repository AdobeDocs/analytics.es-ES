---
description: Las claves no clasificadas se agrupan en informes de clasificación como un solo artículo de línea etiquetado como Ninguno. Puede resultar útil cambiar el nombre de Ninguno por otro más descriptivo.
subtopic: Classifications
title: Claves no clasificadas
feature: Herramientas de administración
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
translation-type: tm+mt
source-git-commit: f52baf97efe20b209f51108995a0620b6c19bec0
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 62%

---

# Claves no clasificadas

Claves no clasificadas se agrupan en informes de clasificación como un solo artículo de línea etiquetado como Ninguno. Puede resultar útil cambiar el nombre de Ninguno por otro más descriptivo.

## Claves no clasificadas {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Las claves no clasificadas se agrupan en informes de clasificación como un solo artículo de línea etiquetado como *`None`*. Puede resultar útil cambiar el nombre *`None`* por otro más descriptivo.

Por ejemplo, supongamos que los códigos de seguimiento contienen información que define el tipo de campaña móvil con el que se asocia el código de seguimiento. Se usa la clasificación (Tipo de campaña de móvil) para agrupar estos códigos de seguimiento en categorías (Web móvil, Aplicación iOS, Aplicación Android, etc.). Las campañas que no sean campañas móviles no se clasificarán con el tipo de campaña móvil. Todos los códigos de seguimiento no clasificados se agruparán como *`None`* en el informe [!UICONTROL Tipo de campaña móvil].

## Cambiar el nombre de la clave de clasificación Ninguno {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Instrucciones sobre cómo cambiar el nombre de una clave no clasificada que aparece como *`none`* en los informes.

1. Con el importador, exporte las clasificaciones a un archivo local.
1. Agregue una fila al archivo y escriba `~none~` en la columna Clave.
1. En la fila que ha agregado, escriba el nombre más descriptivo en la o las columnas de clasificación correspondientes.

   Para seguir el ejemplo de esta documentación, puede escribir &quot;campaña no móvil&quot; en una columna denominada [!UICONTROL Tipo de campaña móvil].

   Esta entrada cambia el nombre *`None`* por *`non-mobile campaign`* en el informe [!UICONTROL Tipo de campaña móvil].

   ![Ejemplo de clave no clasificada](/help/components/classifications/importer/assets/non-classified-key.png)

1. [Importe los datos](/help/components/classifications/importer/import-file.md) de nuevo en el sistema.
