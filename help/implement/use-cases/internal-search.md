---
title: Captura de términos de búsqueda interna
description: Utilice una variable personalizada para capturar términos de búsqueda interna.
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: ht
source-wordcount: '372'
ht-degree: 100%

---


# Captura de términos de búsqueda interna

Los informes de búsqueda interna son parte integral de muchas organizaciones y no es una dimensión predeterminada en Adobe Analytics. Sin embargo, con esfuerzos de implementación mínimos, los informes de términos de búsqueda interna se pueden capturar fácilmente.

## Requisitos previos

[Valide una implementación de desarrollo y publíquela en producción](../launch/validate-publish-prod.md): En esta página se da por hecho que tiene una implementación básica en funcionamiento y ve solicitudes de imagen de Adobe Analytics en el depurador de Adobe.

## Creación de una eVar para dar cabida a la búsqueda interna

Siga [Administración de variables de conversión](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) para crear una nueva eVar dedicada a la búsqueda interna. Asigne a la eVar un nombre fácilmente reconocible (como “Término de búsqueda interna”) y registre la nueva eVar en el [documento de diseño de soluciones](../prepare/solution-design.md) de su organización.

## Determinación de la palabra clave de búsqueda interna

La mayoría de las búsquedas internas utilizan cadenas de consulta para pasar datos de palabra clave entre páginas. Utilice la búsqueda interna del sitio y anote la dirección URL en la página de resultados de la búsqueda:

`https://example.com/search.html?q=kittens`

Si la búsqueda interna del sitio no utiliza la dirección URL, busque el término de búsqueda en otras ubicaciones, como una capa de datos o una cookie. Colabore con el equipo de desarrollo del sitio si no está seguro de dónde encontrar el término de búsqueda interna.

## Asignación del parámetro de cadena de consulta a un elemento de datos

Siga [Asignación de objetos de capa de datos a elementos de datos](../launch/layer-to-elements.md). Al seleccionar **[!UICONTROL Tipo de elemento de datos]**, escoja **[!UICONTROL Parámetro de cadena de consulta]** en lugar de **[!UICONTROL Variable JavaScript]**. Coloque el parámetro de cadena de consulta deseado (generalmente `q`) en el campo de texto.

## Asignación del elemento de datos al eVar

Siga [Asignación de elementos de datos a variables de Analytics](../launch/elements-to-variable.md). Asegúrese de seleccionar el mismo eVar que creó en la configuración del grupo de informes.

## Inicio de la implementación de etiquetas

Siga [Integración de una implementación de Analytics en un entorno de desarrollo](../launch/deploy-dev.md). Una vez que haya confirmado que funciona en su entorno de desarrollo, puede [Validar una implementación de desarrollo y publicarla en producción](../launch/validate-publish-prod.md).

## Creación de informes en Workspace

Asigne un poco de tiempo a la implementación para recopilar datos y, a continuación, podrá empezar a utilizar la dimensión en Analysis Workspace.

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
2. Si no ha iniciado sesión automáticamente en Adobe Analytics, haga clic en el icono de 9 cuadrículas en la parte superior derecha y seleccione **[!UICONTROL Analytics]**.
3. Haga clic en la pestaña **[!UICONTROL Workspace]** y cree un nuevo proyecto.
4. Busque el nombre de la eVar que ha creado en Dimensiones y arrástrela al lienzo del espacio de trabajo.
