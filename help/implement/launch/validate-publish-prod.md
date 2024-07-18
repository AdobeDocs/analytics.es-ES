---
title: Validación de una implementación de desarrollo y publicación en producción
description: Descubra cómo utilizar etiquetas de Adobe Experience Platform para implementar Adobe Analytics en su entorno de producción.
feature: Tags
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
role: Admin, Developer
source-git-commit: e35210582e94037cf286b98e7e0a6b06040a8c6f
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 72%

---

# Validación de una implementación de desarrollo y publicación en producción

Una vez que la biblioteca de etiquetas se haya puesto en producción, su organización puede empezar a utilizar Adobe Analytics para extraer informes básicos.

## Requisitos previos

[Integre la implementación de Analytics en su entorno de desarrollo](deploy-dev.md): Para poder seguir esta página, se debe publicar una implementación de Analytics en el entorno de desarrollo.

## Valide la implementación de desarrollo con Experience Cloud Debugger

El depurador de Experience Cloud es una extensión que muestra todas las etiquetas de Experience Cloud presentes en una página.

1. Instale la extensión para [Chrome](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) o Firefox.
2. Vaya al sitio web de desarrollo en el que haya implementado etiquetas.
3. Haga clic en el icono de Adobe Experience Cloud Debugger en el navegador.
4. Si todo está correctamente implementado, debe ver el contenido dentro de Adobe Analytics, etiquetas y el servicio de ID de visitante de Adobe Experience Cloud.

## Integrar la implementación de desarrollo en las fases de ensayo/producción

Una vez que haya validado que está viendo los datos, puede insertar la implementación en la versión activa del sitio.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas que desee implementar en el sitio.
1. Haga clic en la pestaña **[!UICONTROL Publicación]** y busque la biblioteca en la columna de desarrollo.
1. Haga clic en la lista desplegable de la biblioteca y seleccione **[!UICONTROL Enviar para aprobación]**. Haga clic en **[!UICONTROL Enviar]** en la ventana modal.
1. Vuelva a hacer clic en la lista desplegable de la biblioteca (ahora en la columna Enviados) y seleccione **[!UICONTROL Generar para ensayo]**.
1. Después de unos momentos, la luz amarilla de color de la biblioteca se vuelve verde, lo que indica que la compilación se ha realizado correctamente.
1. Vuelva a hacer clic en la lista desplegable de la biblioteca y seleccione **[!UICONTROL Aprobar para publicación]**.
1. Vuelva a hacer clic en la lista desplegable de la biblioteca (ahora en la columna [!UICONTROL Aprobado]) y seleccione **[!UICONTROL Generar y Publish en producción]**.
1. Vaya a la pestaña Entornos y haga clic en **[!UICONTROL Entorno de producción]**.
1. Copie el código de instalación de producción y suministre este código a los propietarios del sitio web. Solicite la implementación de este código en el entorno de producción del sitio.

## Validar la implementación de producción

Confirme que está viendo los datos en la versión activa del sitio y comience la recopilación de datos oficiales para Adobe Analytics.

1. Una vez que los propietarios del sitio web hayan confirmado que han insertado el código de etiquetas en producción, vaya a la página principal del sitio web en Chrome y abra [!UICONTROL Adobe Experience Cloud Debugger].
2. Si todo funciona, debería ver datos similares a los de las pruebas en su entorno de desarrollo. Llegados a este punto, está usted recopilando datos en su sitio y puede empezar a utilizar Adobe Analytics para crear informes.

## Resolución de problemas

**No aparecen datos en Debugger.**

En el sitio, abra la consola del desarrollador del explorador (normalmente F12). Observe el código fuente de la página y asegúrese de que se cumple lo siguiente:

* No hay errores de JavaScript en la consola. Póngase en contacto con los propietarios del sitio web de su organización para asegurarse de que se han resuelto todos los errores de JS.
* El código de encabezado está correctamente implementado: Asegúrese de que el código de encabezado se encuentra dentro de la etiqueta `<head>` y de que el archivo existe.
* La biblioteca AppMeasurement existe: Navegue directamente al origen de JS para asegurarse de que el archivo JS contiene código. Si no es así, asegúrese de que se crea cada entorno y de que la biblioteca se publica en el entorno correspondiente.
* Interferir extensiones: Algunas extensiones, como los bloqueadores de anuncios, pueden evitar que se activen solicitudes de imagen. Deshabilite las extensiones que puedan impedir el envío de datos al Adobe.

## Pasos siguientes

Ahora que se ha configurado una implementación básica, su función dentro de su organización puede influir en la ruta de acceso en la que desee obtener más información:

* [Crear un documento de diseño de solución](../prepare/solution-design.md): Planifique cómo desea utilizar las variables personalizadas e inclúyalas en la implementación
* [Introducción a Analysis Workspace](/help/analyze/analysis-workspace/home.md): Vaya directamente a Adobe Analytics mediante la función de señalización de la herramienta.
