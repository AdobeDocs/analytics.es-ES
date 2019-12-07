---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# mediaSession

Esta variable especifica los segmentos de un vídeo o elemento multimedia consumidos.


<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 255 bytes </td> 
   <td> pev3 </td> 
   <td> Tiempo invertido en vídeo <p>Segmentos de vídeo vistos </p> </td> 
   <td> Ninguna </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxis y valores posibles** {#section_9A63266633C4427CB4A6549E4D887B85}

**Método autoTrack:**

Si se usa [!UICONTROL s.Media.autoTrack], no es necesario implementar la *`mediaName`* explícitamente. El código de AppMeasurement para JavaScript la determina automáticamente.

**Método de seguimiento manual:**

Sintaxis:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

Valores posibles:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**Ejemplos** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**Problemas, preguntas y consejos** {#section_1BCEB037AB724B6EBE87420BD3604B88}

Debe llamar a los métodos de seguimiento de contenido multimedia únicamente si no puede realizar el seguimiento del reproductor mediante [!UICONTROL s.Media.autoTrack] = true.
