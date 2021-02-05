---
title: Creación de una propiedad de Analytics en Launch
description: Cree un espacio para personalizar el modo en que se recopilan los datos con Adobe Experience Platform Launch.
translation-type: tm+mt
source-git-commit: 632fa007fecadf01e2cef67fd3c2519799636e46
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 82%

---


# Creación de una propiedad de Analytics en Adobe Experience Platform Launch

Adobe Experience Platform Launch es la herramienta que puede utilizar para integrar las soluciones de Experience Cloud en su sitio web (incluido Analytics). Esta página describe específicamente cómo un administrador de Launch puede obtener una implementación básica de Adobe Analytics correctamente configurada.

## Requisitos previos

[Crear un grupo de informes](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Crear un silo para los datos de Analytics que se van a recopilar.

## Crear una propiedad e instalar extensiones vitales

Las propiedades son contenedores generales que se utilizan para administrar etiquetas. Las extensiones permiten instalar etiquetas específicas del producto y configurarlas.

1. Vaya a [launch.adobe.com](https://launch.adobe.com) e inicie sesión si se le solicita.
1. Haga clic en **[!UICONTROL Nueva propiedad]**.
1. Asigne un nombre a la propiedad, como el título del sitio web e introduzca el dominio en el que desea implementar Analytics. Haga clic en **[!UICONTROL Guardar]**.
1. Haga clic en la propiedad recién creada para establecer su configuración.
1. Haga clic en la ficha **[!UICONTROL Extensiones]** y, a continuación, haga clic en **[!UICONTROL Catálogo]**.
1. Localice Identity Service y haga clic en **[!UICONTROL Instalar]**.
1. Todas las opciones de configuración, incluido el ID de organización de Experience Cloud deberían estar completos. Haga clic en **[!UICONTROL Guardar]**.
1. Vuelva al catálogo de extensiones, localice Adobe Analytics y haga clic en **[!UICONTROL Instalar]**.

## Creación de elementos de datos para Adobe Analytics

Los elementos de datos son referencias a partes específicas del sitio para recopilar valores de variables.

1. Vaya a [launch.adobe.com](https://launch.adobe.com) e inicie sesión si se le solicita.
1. Haga clic en la propiedad de Launch que desee implementar en el sitio.
1. Haga clic en la ficha **[!UICONTROL Elementos de datos]** y, a continuación, haga clic en **[!UICONTROL Crear nuevo elemento de datos]**.
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
1. Haga clic en **[!UICONTROL Crear nueva regla]** y asígnele el nombre `Global Rule`.
1. Haga clic en **[!UICONTROL Añadir]** junto a eventos e introduzca la siguiente configuración:
   * Extensión: Core
   * Tipo de evento: Biblioteca cargada (Principio de página)
   * Nombre: Core - Biblioteca cargada (Principio de página)
   * Pedido: 50
1. Haga clic en **[!UICONTROL Mantener cambios]**.
1. En **[!UICONTROL Acciones]**, haga clic en **[!UICONTROL Añadir]** e introduzca la siguiente configuración:
   * Extensión: Adobe Analytics
   * Tipo de acción: Establecer variables
   * Nombre de página: Haga clic en el icono del contenedor y seleccione el elemento de datos `Page Name`
   * Campaña: Parámetro de consulta con un valor de `cid`
1. Haga clic en **[!UICONTROL Mantener cambios]**.
1. Haga clic en el signo Más junto a acciones para agregar otra acción e introduzca la siguiente configuración:
   * Extensión: Adobe Analytics
   * Tipo de acción: Enviar señalización
   * Nombre: Adobe Analytics - Enviar señalización
   * Seguimiento: s.t()
1. Haga clic en **[!UICONTROL Mantener cambios]**.
1. Compruebe que tiene el evento y dos acciones definidas, luego haga clic en **[!UICONTROL Guardar]**.

## Documentación y recursos adicionales

* [Documentación de la extensión de Adobe Analytics](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension): Documentación completa específica de la extensión de Adobe Analytics en Adobe Experience Platform Launch.
* [Introducción a Launch](https://docs.adobelaunch.com/getting-started): Documentación completa para Launch, incluida una guía de introducción más detallada.
* [Canal de de Adobe Experience Platform Launch](https://experienceleague.adobe.com/?tag=Launch#recommended/solutions/experience-platform): Aprenda a utilizar Launch a través de vídeos

## Pasos siguientes

[Añada la implementación de Analytics en su entorno de desarrollo](deploy-dev.md): Obtenga el código de Analytics que funcione en un entorno de prueba.
