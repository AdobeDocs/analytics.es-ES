---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: d5804b411c28270ef910eec5a815532c067a4642

---


# media.trackEvents

La variable identifica qué eventos deben enviarse con una visita multimedia.

<!-- 

media_trackEvents.xml

 -->

Solo es aplicable con JavaScript y [!UICONTROL ActionSource].

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | s.Media.trackEvents="None" |

**Sintaxis y valores posibles** {#section_66A978EF56914BEAAE73359A268A1B4A}

Nombres de evento como event1 o purchase.

**Ejemplos** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents="event1,purchase"
```

**Problemas, preguntas y consejos** {#section_030B11C64EE84D46A85CA550DB732D28}

Asegúrese de rellenar [!UICONTROL trackVars] con "events" siempre que se rellene esta variable.
