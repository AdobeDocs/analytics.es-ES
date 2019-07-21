---
description: Puede copiar el valor de una eVar en una propiedad para permitir las rutas.
seo-description: Puede copiar el valor de una eVar en una propiedad para permitir las rutas.
seo-title: Determinar una ruta copiando un valor evar en una prop
solution: Analytics
subtopic: Reglas de procesamiento
title: Determinar una ruta copiando un valor evar en una prop
topic: Herramientas de administración
uuid: 8 d 7647 c 7-aa 91-466 b -8 d 31-fb 4 dce 83 f 04 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Determinar una ruta copiando un valor evar en una prop

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

