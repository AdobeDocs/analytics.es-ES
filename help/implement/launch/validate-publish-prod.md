---
title: Validación de una implementación de desarrollo y publicación en producción
description: Aprenda a utilizar Adobe Experience Platform Launch para implementar Adobe Analytics en su entorno de producción.
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 93%

---


# Validación de una implementación de desarrollo y publicación en producción

Una vez que la biblioteca de Adobe Experience Platform Launch se haya puesto en producción, su organización puede empezar a utilizar Adobe Analytics para extraer informes básicos.

## Requisitos previos

[Integre la implementación de Analytics en su entorno de desarrollo](deploy-dev.md): Para poder seguir esta página, se debe publicar una implementación de Analytics en el entorno de desarrollo.

## Valide la implementación de desarrollo con Experience Cloud Debugger

Experience Cloud Debugger es un complemento de Chrome que muestra todas las etiquetas de Experience Cloud presentes en una página.

1. Abra el [Explorador web de Chrome](https://www.google.com/intl/es/chrome/) y vaya a [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) en la tienda web de Chrome para instalar la extensión.
2. Vaya al sitio web de desarrollo en el que haya implementado Launch.
3. Haga clic en el icono de Adobe Experience Cloud Debugger en la parte superior derecha de Chrome.
4. Si todo está correctamente implementado, debe ver el contenido dentro de Adobe Analytics, Adobe Experience Platform Launch y el servicio de ID de visitante de Adobe Experience Cloud:

![Debugger][assets/debugger.png]

## Integrar la implementación de desarrollo en las fases de ensayo/producción

Una vez validado que está viendo los datos, puede insertar la implementación en la versión activa del sitio.

1. Vaya a [Adobe Experience Platform Launch](https://launch.adobe.com) e inicie sesión si se le solicita.
2. Haga clic en la propiedad de Launch que desee implementar en el sitio.
3. Haga clic en la pestaña Publicación y busque la biblioteca en la columna de desarrollo.
4. Haga clic en el menú desplegable de la biblioteca y seleccione Enviar para aprobación. Haga clic en Enviar en la ventana modal.
5. Vuelva a hacer clic en el menú desplegable de la biblioteca (ahora en la columna Enviados) y seleccione Generar para ensayo.
6. Después de unos momentos, la luz amarilla de color de la biblioteca se vuelve verde, lo que indica que la compilación se ha realizado correctamente.
7. Vuelva a hacer clic en el menú desplegable de la biblioteca y seleccione Aprobar para publicación.
8. Vuelva a hacer clic en el menú desplegable de la biblioteca (ahora en la columna Aprobado) y seleccione Generar y enviar para producción.
9. Vaya a la pestaña Entornos y haga clic en Entorno de producción.
10. Copie el código de encabezado y pie de página de producción y suministre este código a los propietarios del sitio web. Solicite la implementación de este código en el entorno de producción del sitio.

## Validar la implementación de producción

Confirme que está viendo los datos en la versión activa del sitio y comience la recopilación de datos oficiales para Adobe Analytics.

1. Una vez que los propietarios del sitio web hayan confirmado que han insertado el código de Launch en producción, vaya a la página principal del sitio web en Chrome y abra Adobe Experience Cloud Debugger.
2. Si todo funciona, debería ver datos similares a los de las pruebas en su entorno de desarrollo. Llegados a este punto, está usted recopilando datos en su sitio y puede empezar a utilizar Adobe Analytics para crear informes.

## Resolución de problemas

**No aparecen datos en Debugger.**

En el sitio, abra la consola del desarrollador del explorador (normalmente F12). Observe el código fuente de la página y asegúrese de que se cumple lo siguiente:

* No hay errores de JavaScript en la consola. Póngase en contacto con los propietarios del sitio web de su organización para asegurarse de que se han resuelto todos los errores de JS.
* El código de encabezado está correctamente implementado: Asegúrese de que el código de encabezado se encuentra dentro de la etiqueta `<head>` y de que el archivo existe.
* La biblioteca AppMeasurement existe: Navegue directamente al origen de JS para asegurarse de que el archivo JS contiene código. Si no es así, asegúrese de que se crea cada entorno y de que la biblioteca se publica en el entorno correspondiente.
* Complementos de intervención: Algunos complementos de Chrome pueden evitar que se activen solicitudes de imagen Deshabilite los complementos que puedan impedir el envío de datos a los servidores de Adobe.

## Pasos siguientes

Ahora que se ha configurado una implementación básica, su función dentro de la organización puede influir en la ruta de acceso en la que desee obtener más información:

* [Crear un documento de diseño de solución](../prepare/solution-design.md): Planifique cómo desea utilizar las variables personalizadas e inclúyalas en la implementación
* [Introducción a Analysis Workspace](/help/analyze/analysis-workspace/home.md): Vaya directamente a Adobe Analytics mediante la función de señalización de la herramienta.
