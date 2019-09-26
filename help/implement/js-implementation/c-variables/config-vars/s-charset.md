---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.charSet

The charSet property, which is normally set in the JavaScript file, is used by Analytics to convert incoming data into UTF-8 for storage and reporting by Analytics.

>[!N] Nota: La propiedad charSet es obligatoria al enviar datos a un grupo de informes de byte múltiple y nunca debe usarse con un grupo de informes estándar. Si se configura la propiedad charSet con un grupo de informes ISO estándar, es posible que aparezcan variables truncadas o que se produzca una conversión de caracteres inesperada.

El valor de la propiedad charSet debe coincidir con la codificación de la página web de la etiqueta meta o el encabezamiento http, aunque la sintaxis no sea exactamente la misma. Aunque la etiqueta meta puede utilizar un alias para la codificación, el valor de charSet debe utilizar el nombre preferido (u oficial) de la codificación.

La tabla siguiente contiene algunas de las codificaciones más comunes con su nombre preferido y alias.

| Nombre preferido | Alias |
|--- |--- |
| ISO-8859-1 | ISO_8859-1, CP819, latin1 |
| ISO-8859-2 | ISO_8859-2, latin2 |
| ISO-8859-5 | ISO_8859-5, cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

Dado que existen numerosas codificaciones y alias, póngase en contacto con el consultor de implementación o con el servicio de atención al cliente de Adobe para confirmar el valor correcto de charSet si no aparece en la tabla anterior.

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

Cualquier valor no vacío del parámetro charSet hará que los datos se conviertan a UTF-8 para su almacenamiento. Todos los caracteres del rango 128–255 se convertirán a la secuencia de dos bytes de UTF-8 correspondiente y se almacenarán. Estos caracteres no se mostrarán correctamente en un grupo de informes estándar. Por lo tanto, la propiedad charSet no se debe utilizar nunca con un grupo de informes estándar.

Del mismo modo, si el parámetro charSet tiene un valor vacío, evitará el proceso de conversión de datos y todos los caracteres del rango 128–255 se almacenarán como bytes simples. Estos caracteres no se mostrarán correctamente en los grupos de informes multibyte, dado que los códigos de byte simple de estos caracteres no son válidos en UTF-8. Por lo tanto, el parámetro charSet siempre se debe utilizar con un grupo de informes multibyte. Además, se debe usar el valor correcto en relación con la codificación de la página web.

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. However, if the variables on your pages contain non-ASCII characters, the *`charSet`* variable must be populated.

## Parámetros

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| N.D. | CE | N.D. | "" |

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
