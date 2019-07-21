---
description: La variable pageType solo se usa para designar una página de error 404 (Página no encontrada).
keywords: Implementación de Analytics
seo-description: La variable pageType solo se usa para designar una página de error 404 (Página no encontrada).
seo-title: Configuración incorrecta de la variable pagetype
solution: Analytics
subtopic: Resolución de problemas
title: Configuración incorrecta de la variable pagetype
topic: Desarrollador e implementación
uuid: eafaf 58 e-ba 07-416 f -89 b 9-694687 cc 4802
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Configuración incorrecta de la variable pagetype

La variable pageType solo se usa para designar una página de error 404 (Página no encontrada).

Solo tiene un posible valor, que es errorPage.

```js
pageType="errorPage"
```

En una página de error 404, la variable *`pageName`* no debe rellenarse. The *`pageType`* variable should be set only on a designated 404 error page. Any page containing content should never have a value in the *`pageType`* variable. Para las páginas con contenido, la variable se puede configurar de la siguiente manera:

```js
pageType=""
```

Es mejor eliminar la variable por completo en las páginas con contenido. Así se evitan confusiones con relación al propósito de la variable.
