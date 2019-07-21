---
description: La variable s.products puede ser la variable sintácticamente más compleja que se usa en la recopilación de datos.
keywords: Implementación de Analytics
seo-description: La variable s.products puede ser la variable sintácticamente más compleja que se usa en la recopilación de datos.
seo-title: Errores comunes en la variable Products
solution: Analytics
subtopic: Resolución de problemas
title: Errores comunes en la variable Products
topic: Desarrollador e implementación
uuid: 94075 c 56-37 c 3-44 de-bf 37-1 dfd 228 c 6665
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Errores comunes en la variable Products

La variable s.products puede ser la variable sintácticamente más compleja que se usa en la recopilación de datos.

Los signos coma, punto y coma, barra vertical e igual juegan todos un papel específico en la variable. No tiene una longitud máxima general, pero cada entrada de producto individual no puede ser mayor que 100 bytes (incluidos los caracteres de bytes múltiples). Los errores en la implementación de esta variable son comprensibles, pero lamentablemente para los programadores, [!UICONTROL s.products] suele ser la variable más importante de un sitio porque permite el seguimiento de ingresos, unidades o nombres de productos, entre otros.

Estos son algunos errores extremadamente fáciles de cometer que pueden causar problemas en cualquier implementación.

Asegúrese de que los totales [!UICONTROL category], [!UICONTROL product name] y [!UICONTROL revenue] no contienen comas ni punto y coma. La coma se usa para separar las entradas de la cadena [!UICONTROL s.products]. Cuando hay dos productos en la misma transacción, se utiliza el punto y coma para delimitar los campos dentro de una entrada. Si utiliza una coma o punto y coma de otra manera, la recopilación de datos asume que está separando entradas de productos. Consideremos el siguiente ejemplo:

```js
s.products="widgets;large widget, 40′x40′;1;19.99,wugs;tiny wug;2;1,999.98";
```

En esta implementación, el programador probablemente pretendía que la recopilación de datos leyera esto de la siguiente manera:

Category 1: widgets

Product 1: large widget, 40′x40′

Units 1: 1

Revenue 1: 19.99

Category 2: wugs

Product 2: tiny wug

Units 2: 2

Revenue 2: 1,999.98

Observe las comas en las entradas Product 1 y Revenue 2. Indican una nueva entrada de producto. La recopilación de datos lo interpretaría de la siguiente manera:

Category 1: widgets

Product 1: large widget

Category 2: 40'x40'

Product 2: 1

Units 2: 19.99

Category 3: wugs

Product 3: tiny wug

Units 3: 2

Revenue 3: 1

Category 4: 999.98

Un error como este suele provocar valores numéricos imprevistos en el informe [!UICONTROL Productos] porque el campo de unidades se registra como nombre del producto. Si ve nombres de producto no válidos en su informe [!UICONTROL Productos], revise si en la implementación de la variable [!UICONTROL s.products] se han utilizado incorrectamente caracteres reservados, por ejemplo, la coma.

Los nombres de productos y categorías no deben contener caracteres no admitidos. Esto puede resultar especialmente difícil en la cadena [!UICONTROL s.products] porque los nombres de productos suelen contener caracteres como ™, © y ®. Estos caracteres deben eliminarse de los valores de producto y categoría antes de insertarse en [!UICONTROL s.products]. También debe asegurarse de no incluir símbolos de moneda en los valores de ingresos. Los caracteres admitidos son los números del 1 al 127 de la tabla ASCII.

Si no va a pasar una categoría de productos en la cadena de producto, asegúrese de incluir un punto y coma (;) en el lugar donde se muestra normalmente la categoría de productos, tal y como se muestra a continuación:

```js
s.products=";product name"
```

En este caso, el punto y coma representa un marcador de posición para la categoría de productos. Si no se incluye el punto y coma en la cadena de producto, se asumiría "product name" como categoría, el número de unidades para contar como nombre del producto, los ingresos como unidades, etc.
