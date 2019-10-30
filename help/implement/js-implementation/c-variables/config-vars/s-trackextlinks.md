---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de Analytics
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.trackExternalLinks

Si es “true”, se usan y para determinar si alguno de los vínculos en los que se hizo clic es un vínculo de salida.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | True |

La variable *`trackExternalLinks`* solo debe configurarse como 'false' si no hay vínculos de salida en el sitio o si no le importa realizar el seguimiento del número de clics en esos vínculos de salida. Un vínculo de salida es cualquier vínculo que conduce al visitante fuera del sitio. Si *`trackExternalLinks`* Tiene el valor “true”, los datos de seguimiento se envían inmediatamente al hacer clic en un vínculo de salida. Los datos que se envían con un vínculo de salida incluyen la dirección URL, el nombre y los datos del mapa de clics de visitantes para dicho vínculo. Si *`trackExternalLinks`* tiene el valor “False”, probablemente los datos del mapa de clics de visitantes para los vínculos de salida no estén completos.

## Sintaxis y valores posibles

Se espera que la variable *`trackExternalLinks`* sea 'true' o 'false'.

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

Ninguna

## Problemas, preguntas y consejos

* Cuando *`trackExternalLinks`* tiene el valor es “False”, probablemente los vínculos que conducen al usuario fuera del sitio no estén completos en el mapa de clics de visitantes.

* Cuando *`trackExternalLinks`* tiene el valor “True”, se envían datos cada vez que un visitante hace clic en un vínculo de salida (antes de que se cargue el destino del vínculo).
