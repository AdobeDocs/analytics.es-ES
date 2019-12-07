---
description: La longitud de las variables de Analytics puede afectar al tamaño del fragmento de código HTML, el archivo de biblioteca JavaScript y la solicitud de imagen.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Longitud de las variables
topic: Developer and implementation
uuid: 87deabb3-2acb-4797-9a65-769d9e2fbd62
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Longitud de las variables

La longitud de las variables de Analytics puede afectar al tamaño del fragmento de código HTML, el archivo de biblioteca JavaScript y la solicitud de imagen.

Si un cliente tiene muchas variables largas (60 caracteres o más), los valores se pueden reemplazar por identificadores más cortos. Se pueden usar clasificaciones de datos o reglas de VISTA para traducir los identificadores a nombres descriptivos.

> [!NOTE] La mayoría de las variables de Analytics tienen un máximo de 100 caracteres (las eVars tienen un máximo de 255). Internet Explorer permite un máximo de 2.048 caracteres en una dirección URL de solicitud de imagen GET. El límite de la solicitud de imagen se aplica no solo a las variables, también a la información sobre el explorador, el sistema operativo y los complementos del explorador (solo Netscape/Mozilla).

