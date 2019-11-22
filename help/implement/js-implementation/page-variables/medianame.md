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


# mediaName

Esta variable especifica el nombre del vídeo o elemento multimedia.


<!-- 

mediaName.xml

 -->

Solo está disponible mediante la [!UICONTROL API de inserción de datos] y la [!UICONTROL fuente de datos de procesamiento completo].

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 64 kB | pev3 | Videos; Siguiente flujo de vídeos; Anterior flujo de vídeos; Segmentos de vídeo vistos; Tiempo invertido en vídeo | Ninguna |

**Sintaxis y valores posibles** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**Método autoTrack:**

Si se usa [!UICONTROL s.Media.autoTrack], no es necesario implementar la variable *`mediaName`* explícitamente. El código de AppMeasurement para JavaScript la determina automáticamente.

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

```js
s.Media.close(mediaName)
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

```js
s.Media.close("de_bofr_1045Making_400k")
```

**Ejemplos** {#section_4B9584265B1A47289818141B2A88021D}

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
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**Problemas, preguntas y consejos** {#section_941A445BB52E4063B0F6920E61BB90DE}

* Debe llamar a los métodos de seguimiento de contenido multimedia únicamente si no puede realizar el seguimiento del reproductor mediante [!UICONTROL s.Media.autoTrack] = true.
* Esta variable se almacena como variable TEXT de mySQL al contrario que VARCHAR(100).
