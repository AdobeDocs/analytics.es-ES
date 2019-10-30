---
description: La variable pageType solo se usa para designar una página de error 404 (Página no encontrada).
keywords: Implementación de Analytics
seo-description: La variable pageType solo se usa para designar una página de error 404 (Página no encontrada).
seo-title: Configuración correcta de la variable pageType
solution: Analytics
subtopic: Resolución de problemas
title: Configuración correcta de la variable pageType
topic: Desarrollador e implementación
uuid: eafaf58e-ba07-416f-89b9-694687cc4802
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Configuración correcta de la variable pageType

La variable pageType solo se usa para designar una página de error 404 (Página no encontrada).

Solo tiene un posible valor, que es errorPage.

```js
pageType="errorPage"
```

En una página de error 404, la variable *`pageName`* no debe rellenarse. La variable *`pageType`* solo debe rellenarse en una página de error 404 designada. Las páginas con contenido no deben tener nunca un valor en la variable *`pageType`*. Para las páginas con contenido, la variable se puede configurar de la siguiente manera:

```js
pageType=""
```

Es mejor eliminar la variable por completo en las páginas con contenido. Así se evitan confusiones con relación al propósito de la variable.
