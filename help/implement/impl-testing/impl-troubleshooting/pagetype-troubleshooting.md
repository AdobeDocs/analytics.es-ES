---
description: La variable pageType solo se usa para designar una página de error 404 (Página no encontrada).
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Configuración correcta de la variable pageType
topic: Developer and implementation
uuid: eafaf58e-ba07-416f-89b9-694687cc4802
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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
