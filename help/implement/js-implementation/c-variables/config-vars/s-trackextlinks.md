---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.trackExternalLinks

Si es 'true' y se utilizan para determinar si un vínculo en el que se hizo clic es un vínculo de salida.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | True |

La variable *`trackExternalLinks`* solo debe configurarse como 'false' si no hay vínculos de salida en el sitio o si no le importa realizar el seguimiento del número de clics en esos vínculos de salida. Un vínculo de salida es cualquier vínculo que conduce al visitante fuera del sitio. Si *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. Los datos que se envían con un vínculo de salida incluyen la dirección URL, el nombre y los datos del mapa de clics de visitantes para dicho vínculo. Si *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

## Sintaxis y valores posibles

La sintaxis de la variable *`trackExternalLinks`* se espera que sea 'true' o 'false'.

```
js
s.trackExternalLinks=true|false
```

## Ejemplos

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

## Parámetros de configuración

Ninguno.

## Problemas, preguntas y consejos

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.

* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).
