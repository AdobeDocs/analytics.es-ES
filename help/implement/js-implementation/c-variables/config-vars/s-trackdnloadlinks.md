---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.trackDownLoadLinks

Configure como 'true' si desea realizar el seguimiento de los vínculos a archivos descargables del sitio.

Si *`trackDownloadLinks`* 'true', *`linkDownloadFileTypes`* se utiliza para determinar qué vínculos son archivos descargables.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | True |

La variable *`trackDownloadLinks`* solo debe configurarse como 'false' si no hay vínculos a archivos descargables en el sitio o si no le importa realizar el seguimiento del número de clics en archivos descargables. If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. Los datos que se envían con un vínculo de descarga incluyen la dirección URL de descarga del vínculo y los datos del mapa de clics de visitantes para dicho vínculo. Si *`trackDownloadLinks`* is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.

## Sintaxis y valores posibles

La sintaxis de la variable *`trackDownloadLinks`* se espera que sea 'true' o 'false'.

## Ejemplos

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

## Parámetros de configuración

Ninguno.

## Problemas, preguntas y consejos

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.

* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.