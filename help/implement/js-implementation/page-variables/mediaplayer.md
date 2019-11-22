---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# mediaPlayer

Esta variable especifica el reproductor que se utiliza para reproducir un vídeo o elemento multimedia.


<!-- 

mediaPlayer.xml

 -->

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | pev3 | Reproductores de vídeos | Ninguna |

**Sintaxis y valores posibles** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**Método autoTrack:**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**Método de seguimiento manual:**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valores posibles:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Ejemplos** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Problemas, preguntas y consejos** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

Debe llamar a los métodos de seguimiento de contenido multimedia únicamente si no puede realizar el seguimiento del reproductor mediante s.Media.autoTrack = true.

