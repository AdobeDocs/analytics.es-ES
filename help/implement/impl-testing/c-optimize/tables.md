---
description: Muchos exploradores web no comienzan a mostrar el contenido de una tabla hasta que el explorador ha compilado la tabla completa.
keywords: Implementación de Analytics
seo-description: Muchos exploradores web no comienzan a mostrar el contenido de una tabla hasta que el explorador ha compilado la tabla completa.
seo-title: Tablas
solution: Analytics
subtopic: Resolución de problemas
title: Tablas
topic: Desarrollador e implementación
uuid: f72d7894-38bd-4926-bce4-0c6af7278c63
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Tablas

Muchos exploradores web no comienzan a mostrar el contenido de una tabla hasta que el explorador ha compilado la tabla completa.

Si todo el contenido de la página está dentro de una tabla grande, el explorador debe compilar todo el contenido de la página antes de mostrarla.

Colocar la llamada al archivo de biblioteca JavaScript fuera de las etiquetas de tabla garantiza que la llamada a los servidores de Analytics no afectará a la visualización del contenido de la página.

> [!NOTE] El archivo debe colocarse en una posición legal para las imágenes y debe aparecer entre la etiqueta de apertura <body> y la de </body> cierre.

