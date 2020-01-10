---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.charSet

Analytics utiliza la propiedad charSet, que suele estar configurada en el archivo JavaScript, para convertir datos entrantes a UTF-8 para el almacenamiento y la creación de informes en Analytics.

>[!NNota: ]La propiedad charSet se necesita al enviar datos a un grupo de informes multibyte, y no se debe utilizar nunca con un grupo de informes estándar. Si se configura la propiedad charSet con un grupo de informes ISO estándar, es posible que aparezcan variables truncadas o que se produzca una conversión de caracteres inesperada.

El valor de la propiedad charSet debe coincidir con la codificación de la página web de la etiqueta meta o el encabezamiento http, aunque la sintaxis no sea exactamente la misma. Aunque la etiqueta meta puede utilizar un alias para la codificación, el valor de charSet debe utilizar el nombre preferido (u oficial) de la codificación.

La tabla siguiente contiene algunas de las codificaciones más comunes con su nombre preferido y alias.

| Nombre preferido | Alias |
|--- |--- |
| ISO-8859-1 | ISO_8859-1, CP819, latin1 |
| ISO-8859-2 | ISO_8859-2, latin2 |
| ISO-8859-5 | ISO_8859-5, cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

Dado que existen numerosos alias y codificaciones, contacte con su consultor de implementación o con Atención al cliente de Adobe para confirmar el valor correcto de charSet si no aparece en la tabla anterior.

Si un sitio tiene diferentes codificaciones web en páginas diferentes o si se utiliza un mismo archivo JavaScript para muchos sitios, se puede configurar la propiedad charSet con el valor predeterminado del archivo JavaScript y, luego, reconfigurarla en determinadas páginas donde se necesite para ignorar el valor predeterminado; por ejemplo: `s.charSet="UTF-8"` o `s.charSet="SJIS"`.

Cualquier valor no vacío del parámetro charSet hará que los datos se conviertan a UTF-8 para su almacenamiento. Todos los caracteres del rango 128–255 se convertirán a la secuencia de dos bytes de UTF-8 correspondiente y se almacenarán. Estos caracteres no se mostrarán correctamente en un grupo de informes estándar. Por lo tanto, la propiedad charSet no se debe utilizar nunca con un grupo de informes estándar.

Del mismo modo, si el parámetro charSet tiene un valor vacío, evitará el proceso de conversión de datos y todos los caracteres del rango 128–255 se almacenarán como bytes simples. Estos caracteres no se mostrarán correctamente en los grupos de informes multibyte, dado que los códigos de byte simple de estos caracteres no son válidos en UTF-8. Por lo tanto, el parámetro charSet siempre se debe utilizar con un grupo de informes multibyte. Además, se debe usar el valor correcto en relación con la codificación de la página web.

Si la variable *`charSet`* contiene un valor incorrecto, los datos de todas las demás variables se traducen incorrectamente. Si las variables JavaScript de la página (por ejemplo, *`pageName`*, [!UICONTROL prop1], o *`channel`*) solo contienen caracteres ASCII, *`charSet`* no se tendrá que definir. Sin embargo, si las variables de las páginas contienen caracteres que no sean ASCII, se debe rellenar la variable *`charSet`*.

## Parámetros

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| N/A | CE | N/A | "" |

## Sintaxis y valores posibles

```js
s.charSet="character_set"
```

## Ejemplos

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```
