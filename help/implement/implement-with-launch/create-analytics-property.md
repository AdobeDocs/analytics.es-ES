---
title: Creación de una propiedad de Analytics en Launch
seo-title: Creación de una propiedad Adobe Analytics en Adobe Experience Platform Launch
description: Cree un espacio para personalizar cómo se recopilan los datos mediante el uso de Adobe Experience Platform Launch.
seo-description: Cree un espacio para personalizar cómo se recopilan los datos en Adobe Analytics mediante el uso de Adobe Experience Platform Launch.
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Creación de una propiedad de Analytics en Adobe Experience Platform Launch

Adobe Experience Platform Launch es la herramienta que puede utilizar para integrar soluciones de Experience Cloud en su sitio web (incluido Analytics). Esta página describe específicamente cómo un administrador de Launch puede obtener una implementación básica de Adobe Analytics configurada correctamente.

## Requisitos previos

[Crear un grupo de informes](../../admin/admin-console/create-report-suite.md): Cree un silo para recopilar los datos de Analytics

## Crear una propiedad e instalar extensiones vitales

Las propiedades son contenedores globales que se utilizan para administrar etiquetas. Las extensiones permiten instalar etiquetas específicas de productos y configurarlas.

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. Haga clic en'Nueva propiedad '.
1. Asigne un nombre a su propiedad, como el título del sitio web, e introduzca el dominio al que desee implementar Analytics. Haga clic en Guardar.
1. Haga clic en la propiedad recién creada para especificar su configuración.
1. Haga clic en la ficha Extensiones y, a continuación, haga clic en Catálogo.
1. Localice el servicio de identidad y haga clic en Instalar.
1. Todos los ajustes, incluido el ID de organización de Experience Cloud, deberían completarse. Haga clic en Guardar.
1. Vuelva al catálogo de extensiones, busque Adobe Analytics y haga clic en Instalar.

## Creación de elementos de datos para Adobe Analytics

Los elementos de datos son referencias a partes específicas del sitio para recopilar valores de variables.

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
2. Haga clic en la propiedad Launch que desee implementar en el sitio.
3. Haga clic en la ficha Elementos de datos y, a continuación, haga clic en Crear nuevo elemento de datos.
4. Proporcione al elemento de datos la siguiente configuración:
   * Nombre: Nombre de página
   * Extensión: Principal
   * Tipo de elemento de datos: Variable JavaScript
   * Path to variable: `window.document.title`
      > [!NOTE] Nota: Este es un valor de ejemplo para empezar a utilizarlo. Si su organización define un valor mejor para el nombre de la página, como un valor de capa de datos, puede ingresarlo aquí.
   * Texto limpio marcado
   * Duración: Vista de página
5. Haga clic en Guardar.

## Creación de reglas para Adobe Analytics

Las reglas asignan elementos a los valores de variables de Analytics y determinan cuándo estos valores se envían a los servidores de Adobe.

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. Haga clic en la propiedad Launch que desee implementar en el sitio.
1. Click Create New Rule and name it `Global Rule`.
1. Haga clic en Agregar junto a los eventos e introduzca los siguientes ajustes:
   * Extensión: Principal
   * Tipo de evento: Biblioteca cargada (Principio de página)
   * Nombre: Core - Library Loaded (Página superior)
   * Orden: 50
1. Haga clic en Mantener cambios.
1. En Acciones, haga clic en Agregar e introduzca las siguientes opciones:
   * Extensión: Adobe Analytics
   * Tipo de acción: Configurar variables
   * Page Name: click the container icon, and select the `Page Name` data element.
   * Campaign: Query parameter with a value of `cid`
1. Haga clic en Mantener cambios.
1. Haga clic en el signo más junto a las acciones para agregar otra acción e introduzca las siguientes opciones:
   * Extensión: Adobe Analytics
   * Tipo de acción: Enviar señalización
   * Nombre: Adobe Analytics - Enviar señalización
   * Seguimiento: s. t ()
1. Haga clic en Mantener cambios.
1. Compruebe que tiene el evento y dos acciones y haga clic en Guardar.

## Documentación y recursos adicionales

* [Documentación de extensión de Adobe Analytics](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension): Documentación completa específica de la extensión Adobe Analytics en Adobe Experience Platform Launch.
* [Introducción a Launch](https://docs.adobelaunch.com/getting-started): Documentación completa para Launch, incluida una guía de introducción más detallada
* [Canal YouTube de inicio de Adobe Experience Platform](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&shelf_id=0&sort=dd): Aprenda a utilizar Launch a través de vídeos

## Pasos siguientes

[Implemente su implementación de Analytics en su entorno de desarrollo](deploy-dev.md): Obtenga código de Analytics en un entorno de prueba.
