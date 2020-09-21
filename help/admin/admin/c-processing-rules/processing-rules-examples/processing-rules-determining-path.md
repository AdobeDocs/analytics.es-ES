---
description: Puede copiar el valor de una eVar en una propiedad para permitir las rutas.
subtopic: Processing rules
title: Determinar una ruta copiando un valor eVar en una propiedad
topic: Admin tools
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: ht
source-wordcount: '128'
ht-degree: 100%

---


# Determinar una ruta copiando un valor eVar en una propiedad

Puede copiar el valor de una eVar en una propiedad para permitir las rutas.

Al definir valores, la variable de la izquierda recibe el valor (incluso si está vacío) de la variable de la derecha.

| Conjunto de reglas | Valor |
|---|---|
| Condición | Ninguno (ejecutar siempre) |
| Acción | Sobrescribir el valor de Prop1 con eVar1 |

Puede modificar esta regla para configurar el valor de Prop1, pero solamente si todavía no contiene un valor, de modo similar al siguiente:

| Conjunto de reglas | Valor |
|---|---|
| Condición | Si Prop1 no está definido |
| Acción | Sobrescribir el valor de Prop1 con eVar1 |

Por ejemplo:

![](assets/overwrite-empty-prop.png)

