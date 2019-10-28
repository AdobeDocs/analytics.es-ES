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
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
