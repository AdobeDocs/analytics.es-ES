---
description: Colocar la llamada al archivo de biblioteca JavaScript en la parte superior de la página garantiza que la imagen estará entre los primeros elementos que se descarguen.
keywords: Implementación de Analytics
seo-description: Colocar la llamada al archivo de biblioteca JavaScript en la parte superior de la página garantiza que la imagen estará entre los primeros elementos que se descarguen.
seo-title: Ubicación y concurrencia del archivo JavaScript
solution: Analytics
subtopic: Resolución de problemas
title: Ubicación y concurrencia del archivo JavaScript
topic: Desarrollador e implementación
uuid: ed 5118 a 8-b 142-4 fab -8 aa 1-92 d 931 cc 1439
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Ubicación y concurrencia del archivo JavaScript

Colocar la llamada al archivo de biblioteca JavaScript en la parte superior de la página garantiza que la imagen estará entre los primeros elementos que se descarguen.

La mayoría de los exploradores web descargan las imágenes de forma simultánea. Normalmente se pueden descargar de tres a cuatro imágenes simultáneamente.

Debido a que la mayoría de los exploradores web descargan los elementos de forma simultánea, la barra de estado de muchos exploradores (incluido Internet Explorer) no refleja exactamente qué elemento está intentando cargar el explorador. Por ejemplo, la barra de estado puede notificar que el explorador está esperando para descargar la imagen 1. Las pruebas de paquetes de red muestran que el explorador ya ha recibido la imagen 1 y que está esperando la imagen 2.

>[!NOTE]
>
>Puesto que los proveedores de auditoría de rendimiento de Internet de terceros (como Keynote Systems) descargan elementos de imagen de página secuencialmente, no imitan la experiencia típica del usuario.

