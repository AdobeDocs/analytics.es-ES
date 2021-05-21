---
title: Asignación de elementos de datos de Launch a variables de Analytics
description: Asigne elementos de datos a variables de Analytics para que pueda utilizarlos como dimensiones en Analysis Workspace.
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '448'
ht-degree: 100%

---

# Asignación de elementos de datos de Launch a variables de Analytics

Una vez que tenga un repositorio de elementos de datos en Adobe Experience Platform Launch, puede asignarlos a dimensiones de Analytics.

## Requisitos previos

[Asignar objetos de capa de datos a elementos de datos](layer-to-elements.md): asegúrese de comprender los elementos de datos en Launch y de que tiene varios para trabajar.

[Cree un documento de diseño de solución](../prepare/solution-design.md): un documento de diseño de soluciones es vital para mantenerse organizado. El documento de diseño de la solución simplifica la asignación de elementos de datos a variables de Analytics.

## Asignar elementos de datos a variables de Analytics

La publicación de una biblioteca en Launch después de seguir estos pasos le permite usar dimensiones personalizadas en Analysis Workspace. Puede establecer variables de Analytics de forma global o en reglas individuales.

### Establecer variables globales

Las variables globales son ideales en los casos en los que desee establecer valores de variables en todas las páginas donde exista el elemento de datos.

1. Vaya a [Adobe Experience Platform Launch](https://launch.adobe.com) e inicie sesión si se le solicita.
1. Haga clic en la propiedad de Launch.
1. Haga clic en la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Configurar] en Adobe Analytics.
1. Haga clic en el acordeón [!UICONTROL Variables globales], que muestra la interfaz para asignar variables globales.

### Establecer variables en reglas

Las variables configuradas en las reglas son ideales cuando no desea que se configuren variables en todas las páginas. Los criterios se definen en la regla. Consulte [Reglas](https://docs.adobe.com/content/help/es-ES/launch/using/reference/manage-resources/rules.html) en la guía del usuario de Adobe Experience Platform Launch.

1. Vaya a [Adobe Experience Platform Launch](https://launch.adobe.com) e inicie sesión si se le solicita.
1. Haga clic en la propiedad de Launch.
1. Haga clic en la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla deseada (o cree una).
1. Haga clic en el botón [!UICONTROL Añadir] en [!UICONTROL Acciones].
1. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en Establecer variables.
1. Haga clic en el icono del ![elemento de datos](assets/data-element.png) a la derecha de la variable de Analytics deseada. El [documento de diseño de soluciones](../prepare/solution-design.md) de su organización dicta qué variable de Analytics usar.
1. Seleccione el elemento de datos deseado en la ventana modal. Haga clic en [!UICONTROL Seleccionar].
1. El nombre del elemento de datos se agrega al campo de texto rodeado de símbolos `%`. Por ejemplo, si le asignara al elemento de datos el nombre &quot;Nombre de página&quot;, vería la cadena `%Page name%` al asignar un elemento de datos a una variable.

>[!TIP]
>
>Puede concatenar elementos de datos en la misma variable. Por ejemplo, si tiene un elemento de datos &quot;Nombre de host&quot; y un elemento de datos &quot;Nombre de ruta&quot;, puede combinar ambos en una sola variable mediante `%Hostname%%Pathname%`.

## Pasos siguientes

[Variables de página](../vars/page-vars/page-variables.md): conozca qué variables de nivel de página puede utilizar en la implementación para obtener más información sobre las dimensiones en Analysis Workspace.

[Variables de configuración](../vars/config-vars/configuration-variables.md): descubra qué variables de configuración puede utilizar en la implementación para desbloquear más funciones en Adobe Analytics.
