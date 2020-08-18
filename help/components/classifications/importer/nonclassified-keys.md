---
description: Las claves no clasificadas se agrupan en informes de clasificación como un solo artículo de línea etiquetado como Ninguno. Puede resultar útil cambiar el nombre de Ninguno por otro más descriptivo.
subtopic: Classifications
title: Claves no clasificadas
topic: Admin tools
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 100%

---


# Claves no clasificadas

Las claves no clasificadas se agrupan en informes de clasificación como un solo artículo de línea etiquetado como Ninguno. Puede resultar útil cambiar el nombre de Ninguno por otro más descriptivo.

## Claves no clasificadas {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Las claves no clasificadas se agrupan en informes de clasificación como un solo artículo de línea etiquetado como *`None`*. Puede resultar útil cambiar el nombre *`None`* por otro más descriptivo.

Por ejemplo, imaginemos que los códigos de seguimiento contienen información que define el tipo de campaña móvil con el que se asocian. Se usa la clasificación (Tipo de campaña de móvil) para agrupar estos códigos de seguimiento en categorías (Web móvil, Aplicación iOS, Aplicación Android, etc.). Las campañas que no sean campañas móviles no se clasificarán con el tipo de campaña móvil. Todos los códigos de seguimiento no clasificados se agruparán como  *`None`* en el informe [!UICONTROL Tipo de campaña móvil].

## Cambiar el nombre de la clave de clasificación Ninguno {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Instrucciones sobre cómo cambiar el nombre de una clave no clasificada que aparece como *`none`* en los informes.

1. Con el importador, exporte las clasificaciones a un archivo local.
1. Agregue una fila al archivo y escriba [!DNL ~none~] en la columna Clave.
1. En la fila que ha agregado, escriba el nombre más descriptivo en la o las columnas de clasificación correspondientes.

   Para continuar con el ejemplo de esta documentación, debe escribirse &quot;campaña no móvil&quot; en una columna denominada [!UICONTROL Nombre de campaña móvil].

   Esta entrada cambia el nombre de  *`None`* a *`non-mobile campaign`* en el informe [!UICONTROL Tipo de campaña móvil].
1. [Importe los datos](/help/components/classifications/importer/import-file.md) de nuevo en el sistema.
