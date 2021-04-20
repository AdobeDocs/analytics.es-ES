---
description: Puede copiar el valor de una eVar en una propiedad para permitir las rutas.
subtopic: Processing rules
title: Determinar una ruta copiando un valor eVar en una propiedad
feature: Admin Tools
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '130'
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
