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


# media.trackVars

La variable identifica qué variables deben enviarse con una visita multimedia.

<!-- 

media_trackVars.xml

 -->

Solo es aplicable con JavaScript y [!UICONTROL ActionSource].

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | s.Media.trackVars="None" |

**Sintaxis y valores posibles** {#section_7374684A7EB34AE685E8C40A66CFD289}

Nombres de variables como [!UICONTROL propN], *`eVarN`*, *`events`*, *`channel`*, etc.

**Ejemplos** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars="prop2,events,eVar3"
```

**Problemas, preguntas y consejos** {#section_615AE1B696124B00B78F651B03813EAB}

* Incluso aunque se especifique eVar3 en [!UICONTROL trackVars], se envía con la visita multimedia.

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

La variable controla el orden con el que se usan las cookies y las ID de suscriptor para identificar a los visitantes.

<!-- 

mobile.xml

 -->

Consulte [Protocolos de red móvil](/help/implement/js-implementation/c-additional-libraries/network-protocols.md).

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | /5/ o /1/ en la ruta de la dirección URL de la imagen | N.D. | Ninguna |

**Sintaxis y valores posibles** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**Problemas, preguntas y consejos** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

Utilice la identificación entre visitantes para mitigar los posibles picos en el tráfico de visitantes al utilizar la variable *`s.mobile`* con la implementación de cookies de JavaScript.
