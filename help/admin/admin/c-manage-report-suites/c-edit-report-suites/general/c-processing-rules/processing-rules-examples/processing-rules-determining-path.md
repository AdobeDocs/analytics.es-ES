---
description: Puede copiar el valor de una eVar en una propiedad para permitir las rutas.
subtopic: Processing rules
title: Determinar una ruta copiando un valor eVar en una propiedad
feature: Admin Tools
role: Admin
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
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
