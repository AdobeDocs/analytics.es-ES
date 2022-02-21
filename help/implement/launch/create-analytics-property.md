---
title: Creación de una propiedad de Analytics en etiquetas
description: Cree un espacio para personalizar cómo se recopilan los datos mediante etiquetas.
feature: Launch Implementation
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 100%

---

# Creación de una propiedad de etiquetas de Adobe Analytics

Las etiquetas en Adobe Experience Platform le permiten integrar soluciones de Experience Cloud en su sitio web (incluido Analytics). Esta página describe específicamente cómo un administrador de etiquetas puede obtener una implementación básica de Adobe Analytics correctamente configurada.

>[!NOTE]
>Adobe Experience Platform Launch se ha convertido en un conjunto de tecnologías de recopilación de datos en Experience Platform. Como resultado, se han implementado varios cambios terminológicos en la documentación del producto. Consulte el siguiente [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=es) para obtener una referencia consolidada de los cambios terminológicos.

## Requisitos previos

[Crear un grupo de informes](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Crear un silo para los datos de Analytics que se van a recopilar..

## Creación de una propiedad de etiquetas e instalación de extensiones vitales

Las propiedades son contenedores generales que se utilizan para administrar etiquetas. Las extensiones permiten instalar etiquetas específicas del producto y configurarlas.

1. Inicie sesión en la [IU de recopilación de datos](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en **[!UICONTROL Nueva propiedad]**.
1. Asigne un nombre a la propiedad, como el título del sitio web e introduzca el dominio en el que desea implementar Analytics. Haga clic en **[!UICONTROL Guardar]**.
1. Haga clic en la propiedad de etiquetas recién creada para establecer su configuración.
1. Haga clic en la pestaña **[!UICONTROL Extensiones]** y, a continuación, en **[!UICONTROL Catálogo]**.
1. Vaya a Servicio de identidad y, a continuación, haga clic en **[!UICONTROL Instalar]**.
1. Todas las opciones de configuración, incluido el ID de organización de Experience Cloud deberían estar completos. Haga clic en **[!UICONTROL Guardar]**.
1. Vuelva al catálogo de extensiones, busque Adobe Analytics y haga clic en **[!UICONTROL Instalar]**.

## Creación de elementos de datos para Adobe Analytics

Los elementos de datos son referencias a partes específicas del sitio para recopilar valores de variables.

1. Inicie sesión en la [IU de recopilación de datos](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas que desee implementar en el sitio.
1. Haga clic en la pestaña **[!UICONTROL Elementos de datos]** y, a continuación, haga clic en **[!UICONTROL Crear nuevo elemento de datos]**.
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

1. Inicie sesión en la [IU de recopilación de datos](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas que desee implementar en el sitio.
1. Haga clic en **[!UICONTROL Crear nueva regla]** y asígnele el nombre `Global Rule`.
1. Haga clic en **[!UICONTROL Agregar]** junto a los eventos e introduzca la siguiente configuración:
   * Extensión: Core
   * Tipo de evento: Biblioteca cargada (Principio de página)
   * Nombre: Core - Biblioteca cargada (Principio de página)
   * Pedido: 50
1. Haga clic en **[!UICONTROL Mantener cambios]**.
1. En **[!UICONTROL Acciones]**, haga clic en **[!UICONTROL Agregar]** e introduzca la siguiente configuración:
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
1. Compruebe que tiene el evento y dos acciones definidas, y, a continuación, haga clic en **[!UICONTROL Guardar]**.

## Documentación y recursos adicionales

* [Documentación de la extensión de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=es): Documentación completa específica de la extensión de Adobe Analytics en etiquetas.
* [Introducción a etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=es): Documentación completa para etiquetas, incluida una guía de introducción más detallada
* [Canal de Adobe Experience Platform Launch](https://experienceleague.adobe.com/?tag=Launch&amp;lang=es#recommended/solutions/experience-platform): Aprenda a utilizar etiquetas a través de vídeos

## Pasos siguientes

[Añada la implementación de Analytics en su entorno de desarrollo](deploy-dev.md): Obtenga el código de Analytics que funcione en un entorno de prueba.
