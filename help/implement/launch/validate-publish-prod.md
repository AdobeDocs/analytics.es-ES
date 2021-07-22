---
title: Validación de una implementación de desarrollo y publicación en producción
description: Aprenda a utilizar etiquetas de Adobe Experience Platform para implementar Adobe Analytics en su entorno de producción.
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 64%

---

# Validación de una implementación de desarrollo y publicación en producción

Una vez que la biblioteca de etiquetas se haya puesto en producción, su organización puede empezar a utilizar Adobe Analytics para extraer informes básicos.

>[!NOTE]
>Adobe Experience Platform Launch se ha convertido en un conjunto de tecnologías de recopilación de datos en Experience Platform. Como resultado, se han implementado varios cambios terminológicos en la documentación del producto. Consulte el siguiente [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) para obtener una referencia consolidada de los cambios terminológicos.

## Requisitos previos

[Integre la implementación de Analytics en su entorno de desarrollo](deploy-dev.md): Para poder seguir esta página, se debe publicar una implementación de Analytics en el entorno de desarrollo.

## Valide la implementación de desarrollo con Experience Cloud Debugger

Experience Cloud Debugger es un complemento de Chrome que muestra todas las etiquetas de Experience Cloud presentes en una página.

1. Abra el [Explorador web de Chrome](https://www.google.com/intl/es/chrome/) y vaya a [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) en la tienda web de Chrome para instalar la extensión.
2. Vaya al sitio web de desarrollo en el que haya implementado etiquetas.
3. Haga clic en el icono de Adobe Experience Cloud Debugger en la parte superior derecha de Chrome.
4. Si todo está correctamente implementado, debería ver el contenido dentro de Adobe Analytics, las etiquetas y el servicio de ID de visitante de Adobe Experience Cloud:

![Debugger][assets/debugger.png]

## Integrar la implementación de desarrollo en las fases de ensayo/producción

Una vez validado que está viendo los datos, puede insertar la implementación en la versión activa del sitio.

1. Vaya a [experience.adobe.com](https://experience.adobe.com) e inicie sesión cuando se le solicite.
1. Seleccione **[!UICONTROL Iniciar / Recopilación de datos]**.
1. Haga clic en **[!UICONTROL Ir a Launch / Data Collection]** y seleccione **[!UICONTROL Etiquetas]**.
1. Haga clic en la propiedad de etiqueta que desee implementar en el sitio.
1. Haga clic en la pestaña **[!UICONTROL Publishing]** y busque la biblioteca en la columna de desarrollo.
1. Haga clic en el menú desplegable de la biblioteca y, a continuación, seleccione **[!UICONTROL Enviar para aprobación]**. Haga clic en **[!UICONTROL Submit]** en la ventana modal.
1. Vuelva a hacer clic en el menú desplegable de la biblioteca (ahora en la columna Enviado) y seleccione **[!UICONTROL Generar para ensayo]**.
1. Después de unos momentos, la luz amarilla de color de la biblioteca se vuelve verde, lo que indica que la compilación se ha realizado correctamente.
1. Vuelva a hacer clic en el menú desplegable de la biblioteca y seleccione **[!UICONTROL Aprobar para publicación]**.
1. Vuelva a hacer clic en el menú desplegable de la biblioteca (ahora en la columna [!UICONTROL Approved]) y seleccione **[!UICONTROL Generar y publicar en producción]**.
1. Vaya a la pestaña Entornos y haga clic en **[!UICONTROL Entorno de producción]**.
1. Copie el código de encabezado y pie de página de producción y suministre este código a los propietarios del sitio web. Solicite la implementación de este código en el entorno de producción del sitio.

## Validar la implementación de producción

Confirme que está viendo los datos en la versión activa del sitio y comience la recopilación de datos oficiales para Adobe Analytics.

1. Una vez que los propietarios del sitio web hayan confirmado que han insertado el código de etiqueta en producción, vaya a la página principal del sitio web en Chrome y abra [!UICONTROL Adobe Experience Cloud debugger].
2. Si todo funciona, debería ver datos similares a los de las pruebas en su entorno de desarrollo. Llegados a este punto, está usted recopilando datos en su sitio y puede empezar a utilizar Adobe Analytics para crear informes.

## Resolución de problemas

**No aparecen datos en Debugger.**

En el sitio, abra la consola del desarrollador del explorador (normalmente F12). Observe el código fuente de la página y asegúrese de que se cumple lo siguiente:

* No hay errores de JavaScript en la consola. Póngase en contacto con los propietarios del sitio web de su organización para asegurarse de que se han resuelto todos los errores de JS.
* El código de encabezado está correctamente implementado: Asegúrese de que el código de encabezado se encuentra dentro de la etiqueta `<head>` y de que el archivo existe.
* La biblioteca AppMeasurement existe: Navegue directamente al origen de JS para asegurarse de que el archivo JS contiene código. Si no es así, asegúrese de que se crea cada entorno y de que la biblioteca se publica en el entorno correspondiente.
* Complementos de intervención: Algunos complementos de Chrome pueden evitar que se activen solicitudes de imagen Deshabilite los complementos que puedan impedir el envío de datos a los servidores de Adobe.

## Pasos siguientes

Ahora que se ha configurado una implementación básica, su función dentro de su organización puede influir en la ruta de acceso en la que desee obtener más información:

* [Crear un documento de diseño de solución](../prepare/solution-design.md): Planifique cómo desea utilizar las variables personalizadas e inclúyalas en la implementación
* [Introducción a Analysis Workspace](/help/analyze/analysis-workspace/home.md): Vaya directamente a Adobe Analytics mediante la función de señalización de la herramienta.
