---
title: hier
description: Implementar variables de jerarquía en Adobe Analytics.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# hier

Las variables de jerarquía son variables personalizadas que permiten ver la estructura de un sitio.

>[!TIP] Esta variable era más común en versiones anteriores de Adobe Analytics. Adobe recomienda usar [eVars](evar.md) y clasificaciones en su lugar.

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
