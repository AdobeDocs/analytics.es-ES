---
title: Funciones y métodos
description: Descubra cómo puede utilizar las funciones y los métodos que Adobe ofrece en su implementación.
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3
workflow-type: ht
source-wordcount: '142'
ht-degree: 100%

---


# Funciones y métodos

Adobe ofrece varias funciones y métodos que puede usar en la implementación. Cuando hace referencia a estas funciones o métodos, realizan tareas comunes con una sola línea de código.

Algunas de estas líneas únicas de código pertenecen a las siguientes categorías:

* **Seguimiento de llamadas**: los métodos más comunes y vitales en muchas implementaciones. Incluyen los métodos [`t()`](t-method.md) y [`tl()`](tl-method.md).
* **Utilidades de AppMeasurement**: en versiones anteriores de AppMeasurement, las implementaciones tenían que escribir su propio código para realizar estas tareas. Adobe proporciona estos métodos de utilidad para racionalizar estas tareas comunes. Las utilidades de AppMeasurement incluyen [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md) y [`Util.getQueryParam()`](util-getqueryparam.md).
* **Registrar funciones**: puede escribir sus propias funciones y hacer que AppMeasurement las ejecute automáticamente antes o después de enviar una llamada de seguimiento a Adobe. Las variables incluidas en esta categoría son [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md) y [`registerPostTrackCallback()`](registerposttrackcallback.md).
