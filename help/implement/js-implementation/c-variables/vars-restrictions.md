---
description: Caracteres y cadenas que nunca se permiten en variables de JavaScript.
keywords: Implementación de Analytics
seo-description: Caracteres y cadenas que nunca se permiten en variables de JavaScript.
seo-title: Caracteres JavaScript ilegales
solution: Analytics
subtopic: Variables
title: Caracteres JavaScript ilegales
topic: Desarrollador e implementación
uuid: 04 e 3 b 4 b 4-7 ff 5-4673-8060-34302 b 6 ee 545
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Caracteres JavaScript ilegales

Caracteres y cadenas que nunca se permiten en variables de JavaScript.

* Tabulación (0x09)
* Retorno de carro (0x0D)
* Nueva línea (0x0A)
* Caracteres ASCII con códigos superiores a 127 (a menos que estén habilitados los caracteres de bytes múltiples y  *`charSet`* esté correctamente relleno)
* HTML tags (e.g. <b></b> or &amp;#153)

Muchas variables, especialmente products, hierarchy y events, tienen limitaciones o requisitos de sintaxis adicionales. Para consultar las limitaciones y requisitos de sintaxis de cada variable, consulte la sección correspondiente a los parámetros de la variable  *`s_account`*.
