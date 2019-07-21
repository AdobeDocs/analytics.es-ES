---
title: Implementación de Adobe Analytics en un entorno de desarrollo
seo-title: Implementación de Adobe Analytics en un entorno de desarrollo
description: Descubra cómo utilizar Adobe Experience Platform Launch para implementar Adobe Analytics en su entorno de desarrollo.
seo-description: Descubra cómo utilizar Adobe Experience Platform Launch para implementar Adobe Analytics en su entorno de desarrollo.
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# Validación de una implementación de desarrollo y publicación en producción

Una vez que la biblioteca de lanzamiento de Adobe Experience Platform se transfiere a la producción, su organización puede empezar a utilizar Adobe Analytics para extraer informes básicos.

## Requisitos previos

[Implemente su implementación de Analytics en su entorno de desarrollo](deploy-dev.md): Se debe publicar una implementación de Analytics en el entorno de desarrollo para poder seguir esta página.

## Validación de la implementación de desarrollo mediante el depurador de Experience Cloud

Experience Cloud Debugger es un complemento de Chrome que muestra todas las etiquetas de Experience Cloud presentes en una página.

1. Open [Chrome Web Browser](https://www.google.com/chrome/) and go to [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) on the Chrome Web Store to install the extension.
2. Vaya a su sitio web de desarrollo en el que ha implementado Iniciar activado.
3. Haga clic en el icono de depurador de Adobe Experience Cloud en la parte superior derecha de Chrome.
4. Si todo está correctamente implementado, debería ver contenido dentro de Adobe Analytics, Adobe Experience Platform Launch y el servicio de ID de visitante de Adobe Experience Cloud:

![depurador][assets/debugger.png]

## Implementación de la implementación de desarrollo en ensayo/prod

Una vez que haya validado los datos, puede insertar su implementación en la versión dinámica del sitio.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Haga clic en la propiedad Launch que desee implementar en el sitio.
3. Haga clic en la ficha Publicación y busque su biblioteca en la columna de desarrollo.
4. Haga clic en la lista desplegable de la biblioteca y, a continuación, seleccione Enviar para aprobación. Haga clic en Enviar en la ventana modal.
5. Vuelva a hacer clic en la lista desplegable de la biblioteca (ahora en la columna Enviado) y seleccione Generar para ensayo.
6. Después de unos minutos, la luz de color amarillo en la biblioteca se vuelve verde, lo que indica una compilación correcta.
7. Vuelva a hacer clic en la lista desplegable de la biblioteca y seleccione Aprobar para publicación.
8. Vuelva a hacer clic en la lista desplegable de la biblioteca (ahora en la columna Aprobado) y seleccione Generar y publicar en producción.
9. Vaya a la ficha Entornos y haga clic en Entorno de producción.
10. Copie el encabezado de producción + código de pie de página y envíelo a los propietarios de su sitio web. Solicite que implemente este código en el entorno de producción del sitio.

## Validar la implementación de producción

Confirme que está viendo los datos en la versión dinámica del sitio y comience la recopilación de datos oficiales para Adobe Analytics.

1. Una vez que haya confirmado a los propietarios de su sitio web que han insertado el código de inicio en la producción, navegue hasta la página principal de su sitio web en Chrome y abra el depurador de Adobe Experience Cloud.
2. Si todo funciona, debería ver datos similares a sus pruebas en el entorno de desarrollo. Actualmente, recopila datos en su sitio y ahora puede empezar a utilizar Adobe Analytics para los informes.

## Resolución de problemas

**No aparece ningún dato en el depurador.**

En el sitio, abra la consola de desarrollador del explorador (normalmente F 12). Observe el código fuente de la página y asegúrese de que se cumple lo siguiente:

* No hay errores de JavaScript en la consola. Trabaje con los propietarios del sitio web de su organización para asegurarse de que se resuelvan todos los errores de JS.
* Header code is properly implemented: Make sure the header code is inside the `<head>` tag, and that the file exists.
* Existe la biblioteca appmeasurement: Vaya directamente al origen JS para asegurarse de que el archivo JS contiene código. Si no, asegúrese de que se crea cada entorno y que la biblioteca se publique en su entorno respectivo.
* Interfiriendo complementos: Algunos complementos Chrome pueden impedir que se activen las solicitudes de imagen. Deshabilite los complementos que puedan detener la transferencia de datos a los servidores de Adobe.

## Pasos siguientes

Ahora que se ha configurado una implementación básica, su función dentro de su organización puede influir en la ruta que desee obtener más información sobre:

* [Cree un documento de diseño de solución](../prepare/solution-design.md): Realice un plan para saber cómo desea utilizar variables personalizadas y, a continuación, inclúyalas en su implementación
* [Empiece a utilizar Analysis Workspace](../../analyze/analysis-workspace/home.md): Sumérjase directamente en Adobe Analytics con la capacidad de señalización de la herramienta.
