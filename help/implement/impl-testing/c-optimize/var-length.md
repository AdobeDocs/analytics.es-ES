---
description: La longitud de las variables de Analytics puede afectar al tamaño del fragmento de código HTML, el archivo de biblioteca JavaScript y la solicitud de imagen.
keywords: Implementación de Analytics
seo-description: La longitud de las variables de Analytics puede afectar al tamaño del fragmento de código HTML, el archivo de biblioteca JavaScript y la solicitud de imagen.
seo-title: Longitud de variable
solution: Analytics
subtopic: Resolución de problemas
title: Longitud de variable
topic: Desarrollador e implementación
uuid: 87 deabb 3-2 acb -4797-9 a 65-769 d 9 e 2 fbd 62
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Longitud de variable

La longitud de las variables de Analytics puede afectar al tamaño del fragmento de código HTML, el archivo de biblioteca JavaScript y la solicitud de imagen.

Si un cliente tiene muchas variables largas (60 caracteres o más), los valores se pueden reemplazar por identificadores más cortos. Se pueden usar clasificaciones de datos o reglas de VISTA para traducir los identificadores a nombres descriptivos.

>[!NOTE]
>
>La mayoría de las variables de Analytics tienen un máximo de 100 caracteres (las evars tienen un máximo de 255). Internet Explorer permite un máximo de 2.048 caracteres en una dirección URL de solicitud de imagen GET. El límite de la solicitud de imagen se aplica no solo a las variables, también a la información sobre el explorador, el sistema operativo y los complementos del explorador (solo Netscape/Mozilla).

