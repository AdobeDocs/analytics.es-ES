---
description: Determina si está empezando una nueva visita.
keywords: Implementación de Analytics
seo-description: Determina si está empezando una nueva visita.
seo-title: getVisitStart
solution: Analytics
title: getVisitStart
topic: Desarrollador e implementación
uuid: 7dd3e51f-2f73-4452-a9fb-cac513cd28eb
translation-type: ht
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

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

