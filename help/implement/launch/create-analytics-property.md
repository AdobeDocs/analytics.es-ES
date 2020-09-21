---
title: Creación de una propiedad de Analytics en Launch
description: Cree un espacio para personalizar el modo en que se recopilan los datos con Adobe Experience Platform Launch.
translation-type: tm+mt
source-git-commit: dd506bf171c480c880863c03eee55be8fd9e15cb
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 84%

---


# Creación de una propiedad de Analytics en Adobe Experience Platform Launch

Adobe Experience Platform Launch es la herramienta que puede utilizar para integrar las soluciones de Experience Cloud en su sitio web (incluido Analytics). Esta página describe específicamente cómo un administrador de Launch puede obtener una implementación básica de Adobe Analytics correctamente configurada.

## Requisitos previos

[Crear un grupo de informes](/help/admin/admin-console/create-report-suite.md): Crear un silo para los datos de Analytics que se van a recopilar.

## Crear una propiedad e instalar extensiones vitales

Las propiedades son contenedores generales que se utilizan para administrar etiquetas. Las extensiones permiten instalar etiquetas específicas del producto y configurarlas.

1. Vaya a [launch.adobe.com](https://launch.adobe.com) e inicie sesión si se le solicita.
1. Click **[!UICONTROL New Property]**.
1. Asigne un nombre a la propiedad, como el título del sitio web e introduzca el dominio en el que desea implementar Analytics. Haga clic en **[!UICONTROL Guardar]**.
1. Haga clic en la propiedad recién creada para establecer su configuración.
1. Click the **[!UICONTROL Extensions]** tab, then click **[!UICONTROL Catalog]**.
1. Locate Identity Service, then click **[!UICONTROL Install]**.
1. Todas las opciones de configuración, incluido el ID de organización de Experience Cloud deberían estar completos. Haga clic en **[!UICONTROL Guardar]**.
1. Back in the extensions catalog, locate Adobe Analytics and click **[!UICONTROL Install]**.

## Creación de elementos de datos para Adobe Analytics

Los elementos de datos son referencias a partes específicas del sitio para recopilar valores de variables.

1. Vaya a [launch.adobe.com](https://launch.adobe.com) e inicie sesión si se le solicita.
1. Haga clic en la propiedad de Launch que desee implementar en el sitio.
1. Click the **[!UICONTROL Data Elements]** tab, then click **[!UICONTROL Create New Data Element]**.
1. Asigne al elemento de datos la siguiente configuración:

   * Nombre: Nombre de la página
   * Extensión: Core
   * Tipo de elemento de datos: Variable JavaScript
   * Ruta a la variable: `window.document.title`

      >[!NOTE]
      >
      >Este es un valor de ejemplo para ayudarle a empezar. Si su organización define un valor más adecuado para el nombre de la página, como un valor de capa de datos, puede utilizarlo aquí.
   * Se ha seleccionado la opción Borrar texto
   * Duración: Vista de página
1. Haga clic en **[!UICONTROL Guardar]**.

## Creación de reglas para Adobe Analytics

Las reglas asignan elementos de datos a valores de variables de Analytics y determinan cuándo se envían dichos valores a los servidores de Adobe.

1. Vaya a [launch.adobe.com](https://launch.adobe.com) e inicie sesión si se le solicita.
1. Haga clic en la propiedad de Launch que desee implementar en el sitio.
1. Click **[!UICONTROL Create New Rule]** and name it `Global Rule`.
1. Click **[!UICONTROL Add]** next to events, and enter the following settings:
   * Extensión: Core
   * Tipo de evento: Biblioteca cargada (Principio de página)
   * Nombre: Core - Biblioteca cargada (Principio de página)
   * Pedido: 50
1. Click **[!UICONTROL Keep Changes]**.
1. Under **[!UICONTROL Actions]**, click **[!UICONTROL Add]**, and enter the following settings:
   * Extensión: Adobe Analytics
   * Tipo de acción: Establecer variables
   * Nombre de página: Haga clic en el icono del contenedor y seleccione el elemento de datos `Page Name`
   * Campaña: Parámetro de consulta con un valor de `cid`
1. Click **[!UICONTROL Keep Changes]**.
1. Haga clic en el signo Más junto a acciones para agregar otra acción e introduzca la siguiente configuración:
   * Extensión: Adobe Analytics
   * Tipo de acción: Enviar señalización
   * Nombre: Adobe Analytics - Enviar señalización
   * Seguimiento: s.t()
1. Click **[!UICONTROL Keep Changes]**.
1. Verify that you have the event and two actions set, then click **[!UICONTROL Save]**.

## Documentación y recursos adicionales

* [Documentación de la extensión de Adobe Analytics](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension): Documentación completa específica de la extensión de Adobe Analytics en Adobe Experience Platform Launch.
* [Introducción a Launch](https://docs.adobelaunch.com/getting-started): Documentación completa para Launch, incluida una guía de introducción más detallada.
* [Canal de YouTube de Adobe Experience Platform Launch](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&amp;shelf_id=0&amp;sort=dd): Aprenda a utilizar Launch a través de vídeos

## Pasos siguientes

[Añada la implementación de Analytics en su entorno de desarrollo](deploy-dev.md): Obtenga el código de Analytics que funcione en un entorno de prueba.
