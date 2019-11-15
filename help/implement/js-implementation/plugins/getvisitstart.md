---
description: Determina si está empezando una nueva visita.
keywords: Analytics Implementation
solution: Analytics
title: getVisitStart
topic: Developer and implementation
uuid: 7dd3e51f-2f73-4452-a9fb-cac513cd28eb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# getVisitStart

Determina si está empezando una nueva visita.

**Variables de configuración**

Ninguna

**Parámetros**

c = (cadena) nombre de la cookie para el seguimiento.

**Devuelve**

(entero) 1 en la primera página de la visita; de lo contrario, 0.

**Llamadas de muestra**

```
s.eVar50 = s.getVisitStart("s_visit");
```

