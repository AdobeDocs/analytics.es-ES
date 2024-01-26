---
title: Asignación de elementos de datos de etiquetas a variables de Analytics
description: Asigne elementos de datos a variables de Analytics para que pueda utilizarlos como dimensiones en Analysis Workspace.
feature: Tags
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 96%

---


# Asignación de elementos de datos de etiquetas a variables de Analytics

Una vez que tenga un repositorio de elementos de datos de etiquetas, puede asignarlos a dimensiones de Analytics.

## Requisitos previos

[Asignar objetos de capa de datos a elementos de datos](layer-to-elements.md): Asegúrese de comprender los elementos de datos de etiquetas y de que tiene varios para trabajar con ellos.

[Cree un documento de diseño de solución](../prepare/solution-design.md): un documento de diseño de soluciones es vital para mantenerse organizado. El documento de diseño de la solución simplifica la asignación de elementos de datos a variables de Analytics.

## Asignar elementos de datos a variables de Analytics

La publicación de una biblioteca de etiquetas después de seguir estos pasos le permite usar dimensiones personalizadas en Analysis Workspace. Puede establecer variables de Analytics de forma global o en reglas individuales.

### Establecer variables globales

Las variables globales son ideales en los casos en los que desee establecer valores de variables en todas las páginas donde exista el elemento de datos.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Haga clic en la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Configurar] en Adobe Analytics.
1. Haga clic en el acordeón [!UICONTROL Variables globales], que muestra la interfaz para asignar variables globales.

### Establecer variables en reglas

Las variables configuradas en las reglas son ideales cuando no desea que se configuren variables en todas las páginas. Los criterios se definen en la regla. Consulte [Reglas](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=es) en la documentación de etiquetas de Adobe Experience Platform.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Haga clic en la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla deseada (o cree una).
1. Haga clic en el botón [!UICONTROL Añadir] en [!UICONTROL Acciones].
1. Configure las variables [!UICONTROL Extensión] lista desplegable para Adobe Analytics y la variable [!UICONTROL Tipo de acción] para establecer variables.
1. Haga clic en el icono del ![elemento de datos](assets/data-element.png) a la derecha de la variable de Analytics deseada. El [documento de diseño de soluciones](../prepare/solution-design.md) de su organización dicta qué variable de Analytics usar.
1. Seleccione el elemento de datos deseado en la ventana modal. Haga clic en [!UICONTROL Seleccionar].
1. El nombre del elemento de datos se agrega al campo de texto rodeado de símbolos `%`. Por ejemplo, si le asignara al elemento de datos el nombre &quot;Nombre de página&quot;, vería la cadena `%Page name%` al asignar un elemento de datos a una variable.

>[!TIP]
>
>Puede concatenar elementos de datos en la misma variable. Por ejemplo, si tiene un elemento de datos &quot;Nombre de host&quot; y un elemento de datos &quot;Nombre de ruta&quot;, puede combinar ambos en una sola variable mediante `%Hostname%%Pathname%`.

## Pasos siguientes

[Variables de página](../vars/page-vars/page-variables.md): conozca qué variables de nivel de página puede utilizar en la implementación para obtener más información sobre las dimensiones en Analysis Workspace.

[Variables de configuración](../vars/config-vars/configuration-variables.md): descubra qué variables de configuración puede utilizar en la implementación para desbloquear más funciones en Adobe Analytics.
