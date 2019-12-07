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


# mediaLength

La variable especifica la longitud total del contenido multimedia que se está reproduciendo.


<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
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
   <td> Sin tamaño máximo para la solicitud pev3 completa; el tamaño se limita a la longitud de dirección URL máxima del explorador. </td> 
   <td> pev3 </td> 
   <td> Tiempo invertido en vídeo; <p>Segmentos de vídeo vistos </p> </td> 
   <td> Ninguna </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxis y valores posibles** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

**Método autoTrack:**

Si se usa [!UICONTROL s.Media.autoTrack], no es necesario implementar la variable [!UICONTROL mediaLength] explícitamente. El código de AppMeasurement para JavaScript la determina automáticamente.

**Método de seguimiento manual:**

Sintaxis:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valores posibles:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Ejemplos** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Problemas, preguntas y consejos** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* Debe llamar a los métodos de seguimiento de contenido multimedia únicamente si no puede realizar el seguimiento del reproductor mediante [!UICONTROL s.Media.autoTrack] = true.
* Si no realiza el seguimiento mediante [!UICONTROL autoTrack], asegúrese de configurar la longitud en segundos.

