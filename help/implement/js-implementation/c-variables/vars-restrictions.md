---
description: Caracteres y cadenas que nunca se permiten en variables de JavaScript.
keywords: Analytics Implementation
subtopic: Variables
title: Caracteres JavaScript no permitidos
topic: Developer and implementation
uuid: 04e3b4b4-7ff5-4673-8060-34302b6ee545
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Caracteres JavaScript no permitidos

Caracteres y cadenas que nunca se permiten en variables de JavaScript.

* Tabulación (0x09)
* Retorno de carro (0x0D)
* Nueva línea (0x0A)
* Caracteres ASCII con códigos superiores a 127 (a menos que estén habilitados los caracteres de bytes múltiples y *`charSet`* esté correctamente relleno)
* Etiquetas HTML (por ejemplo, <b></b> o &amp;#153)

Muchas variables, especialmente products, hierarchy y events, tienen limitaciones o requisitos de sintaxis adicionales. Para consultar las limitaciones y requisitos de sintaxis de cada variable, consulte la sección correspondiente a los parámetros de la variable *`s_account`*.
