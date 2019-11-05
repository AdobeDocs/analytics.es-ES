---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de Analytics
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.trackDownLoadLinks

Configure como 'true' si desea realizar el seguimiento de los vínculos a archivos descargables del sitio.

Si *`trackDownloadLinks`* tiene el valor “true”, *`linkDownloadFileTypes`* se utiliza para determinar qué vínculos son archivos descargables.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | True |

La variable *`trackDownloadLinks`* solo debe configurarse como 'false' si no hay vínculos a archivos descargables en el sitio o si no le importa realizar el seguimiento del número de clics en archivos descargables. Si *`trackDownloadLinks`* tiene el valor “true” cuando se hace clic en un vínculo de descarga de archivos, los datos se envían inmediatamente a [!DNL Analytics]. Los datos que se envían con un vínculo de descarga incluyen la dirección URL de descarga del vínculo y los datos del mapa de clics de visitantes para dicho vínculo. Si *`trackDownloadLinks`* tiene el valor “false”, probablemente los datos del mapa de clics de visitantes para los vínculos a archivos descargables del sitio no estén completos.

## Sintaxis y valores posibles

Se espera que la variable *`trackDownloadLinks`* sea 'true' o 'false'.

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

Ninguna

## Problemas, preguntas y consejos

* Cuando *`trackDownloadLinks`* tiene el valor “false”, probablemente los vínculos que se usan para descargar archivos en el sitio no estén completos en el mapa de clics de visitantes.

* Cuando *`trackDownloadLinks`* tiene el valor “true”, los datos se envían cada vez que un visitante hace clic en un vínculo de descarga de archivos.
