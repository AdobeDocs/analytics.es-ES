---
title: hier
description: Implementar variables de jerarquía en Adobe Analytics.
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
source-git-commit: a71db2fac9333b70a55da91fe9a94b0cc8434b42
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 93%

---

# hier

Las variables de jerarquía son variables personalizadas que permiten ver la estructura de un sitio.

>[!TIP]
>
>Esta variable era más común en versiones anteriores de Adobe Analytics. Adobe recomienda usar [eVars](evar.md) y clasificaciones en su lugar.

>[!IMPORTANT]
>
>La jerarquía no es compatible con la recopilación de datos mediante XDM para Experience Edge.

Esta variable resulta útil para los sitios que tienen más de tres niveles en la estructura del sitio. Por ejemplo: un sitio de medios puede tener 4 niveles en la sección Deportes: `Sports`, `Local Sports`, `Baseball`, y `Team name`. Si alguien visita la página de béisbol, tanto deportes como deportes locales y béisbol reflejarán esa visita.

Adobe admite hasta 5 variables de jerarquía en la implementación. Al momento de habilitar la jerarquía, determine un delimitador para la variable y el número de niveles de la jerarquía. Por ejemplo, si el delimitador es una coma, la jerarquía tendría un aspecto similar al siguiente:

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

Asegúrese de que ninguno de los nombres de sección contenga un delimitador. Por ejemplo, si llama a una de las secciones `Coach Griffin, Jim`, elija un delimitador que no sea una coma. El límite total de variables es de 255 bytes. Los delimitadores pueden constar de varios caracteres, como `||` o `/|\`, que tienen menos probabilidades de aparecer en los valores de las variables.

## Ejemplos

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
