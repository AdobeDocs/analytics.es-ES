---
title: Capture los términos de búsqueda interna
description: Utilice una variable personalizada para capturar los términos de búsqueda interna.
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---


# Capture los términos de búsqueda interna

El sistema de informes de búsqueda interna es esencial para muchas organizaciones y no es una dimensión lista para usar con Adobe Analytics. Sin embargo, con los esfuerzos de implementación mínimos, se puede capturar fácilmente el sistema de informes de términos de búsqueda interna.

## Requisitos previos

[Valide una implementación de desarrollo y publique en producción](../launch/validate-publish-prod.md): En esta página se asume que dispone de una implementación básica que funciona y que se ven solicitudes de imagen de Adobe Analytics en el depurador de Adobe.

## Crear un eVar para dar cabida a la búsqueda interna

Siga las instrucciones de administración [de las variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) de conversión para crear un nuevo eVar dedicado a la búsqueda interna. Asigne al eVar un nombre fácilmente reconocible (como &quot;término de búsqueda interna&quot;) y registre el nuevo eVar en el documento [de diseño de la](../prepare/solution-design.md)solución de su organización.

## Determinar palabra clave de búsqueda interna

La mayoría de las búsquedas internas utilizan cadenas de consulta para pasar datos de palabras clave entre páginas. Utilice la búsqueda interna del sitio y anote la dirección URL en la página de resultados de búsqueda:

`https://example.com/search.html?q=kittens`

Si la búsqueda interna del sitio no utiliza la dirección URL, busque el término de búsqueda en otras ubicaciones, como una capa de datos o una cookie. Trabaje con el equipo de desarrollo del sitio si no está seguro de dónde encontrar el término de búsqueda interna.

## Asignar el parámetro de cadena de consulta a un elemento de datos

Follow [Map data layer objects to data elements](../launch/layer-to-elements.md). Al seleccionar el tipo **[!UICONTROL de elemento]** de datos, seleccione el parámetro **[!UICONTROL de cadena de]** Consulta en lugar de la variable **[!UICONTROL de]** JavaScript. Coloque el parámetro de cadena de consulta deseado (normalmente `q`) en el campo de texto.

## Asignar el elemento de datos al eVar

Follow [Map Launch data elements to Analytics variables](../launch/elements-to-variable.md). Asegúrese de seleccionar el mismo eVar que creó en la configuración del grupo de informes.

## Inicio del proceso de implementación de Launch

Follow [Deploy an Analytics implementation to a development environment](../launch/deploy-dev.md). Una vez que haya confirmado que funciona en su entorno de desarrollo, puede [Validar una implementación de desarrollo y publicar en producción](../launch/validate-publish-prod.md).

## Sistema de informes en Workspace

Asigne tiempo a la implementación para recopilar datos y, a continuación, puede realizar inicios con la dimensión en Analysis Workspace.

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
2. Si no ha iniciado sesión automáticamente en Adobe Analytics, haga clic en el icono de 9 cuadrícula en la parte superior derecha y seleccione **[!UICONTROL Analytics]**.
3. Haga clic en la ficha **[!UICONTROL Espacio de trabajo]** y cree un nuevo proyecto.
4. Busque el nombre del eVar que ha creado en Dimension y arrástrelo al lienzo del área de trabajo.
