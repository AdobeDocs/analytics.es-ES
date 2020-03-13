---
title: Asignación de elementos de datos de Launch a variables de Analytics
description: Asigne elementos de datos a variables de Analytics para que pueda utilizarlos como dimensiones en Analysis Workspace.
translation-type: tm+mt
source-git-commit: bb9648f4886ac26c77d89f850f7a68d40a9b4ffc

---


# Asignación de elementos de datos de Launch a variables de Analytics

Una vez que tenga un repositorio de elementos de datos en Adobe Experience Platform Launch, puede asignarlos a dimensiones de Analytics.

## Requisitos previos

[Asignar objetos de capa de datos a elementos](layer-to-elements.md)de datos: Asegúrese de comprender los elementos de datos en Launch y de que tiene varios con los que trabajar.

[Crear un documento](../prepare/solution-design.md)de diseño de solución: Un documento de diseño de solución es vital para mantenerse organizado. El siguiente documento de diseño de la solución simplifica la asignación de elementos de datos a variables de Analytics.

## Asignación de elementos de datos a variables de Analytics

La publicación de una biblioteca en Launch después de seguir estos pasos le permite utilizar dimensiones personalizadas en Analysis Workspace. Puede establecer variables de Analytics de forma global o en reglas individuales.

### Establecer variables globales

Las variables globales son ideales en los casos en los que desee establecer valores de variables en todas las páginas donde exista el elemento de datos.

1. Vaya a [Adobe Experience Platform Launch](https://launch.adobe.com) e inicie sesión si se le solicita.
1. Haga clic en la propiedad Launch que desee.
1. Haga clic en la [!UICONTROL Extensions tab], luego haga clic [!UICONTROL Configure] en la extensión Adobe Analytics.
1. Haga clic en el [!UICONTROL Global variables] acordeón, que muestra la interfaz para asignar variables globales.

### Establecer variables en reglas

Las variables configuradas en las reglas son ideales en los casos en los que no desee que se configuren variables en todas las páginas. Los criterios se definen en la regla. See [Rules](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html) in the Adobe Experience Platform Launch user guide.

1. Vaya a [Adobe Experience Platform Launch](https://launch.adobe.com) e inicie sesión si se le solicita.
1. Haga clic en la propiedad Launch que desee.
1. Haga clic en la [!UICONTROL Rules] ficha y, a continuación, haga clic en la regla que desee (o cree una).
1. Haga clic en el [!UICONTROL Add] botón debajo de [!UICONTROL Actions].
1. Configure el [!UICONTROL Extension] menú desplegable en Adobe Analytics y el [!UICONTROL Action Type] en Definir variables.
1. Haga clic en el icono del elemento [!Dde](assets/data-element.png) datos a la derecha de la variable de Analytics deseada. El documento [de diseño de la](../prepare/solution-design.md) solución de su organización dicta qué variable de Analytics usar.
1. Seleccione el elemento de datos deseado en la ventana modal. Haga clic en [!UICONTROL Select].
1. El nombre del elemento de datos se agrega al campo de texto rodeado de `%` signos. Por ejemplo, si le asignara al elemento de datos el nombre &quot;Nombre de página&quot;, vería la cadena `%Page name%` al asignar un elemento de datos a una variable.

> [!TIP] Puede concatenar elementos de datos en la misma variable. Por ejemplo, si tiene un elemento de datos &quot;Nombre de host&quot; y un elemento de datos &quot;Nombre de ruta&quot;, puede combinar ambos en una sola variable mediante `%Hostname%%Pathname%`.

## Pasos siguientes

[Variables](../vars/page-vars/page-variables.md)de página: Descubra qué variables de nivel de página puede utilizar en la implementación para obtener más información sobre las dimensiones en Analysis Workspace.

[Variables](../vars/config-vars/configuration-variables.md)de configuración: Descubra qué variables de configuración puede utilizar en la implementación para desbloquear más funciones en Adobe Analytics.
