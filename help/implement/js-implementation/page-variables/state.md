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


# state

Las variables y son variables de conversión.


<!-- 

state.xml

 -->

Son similares a las eVars en cuando a que capturan eventos pero, a diferencia de estas, no persisten. La variable *`zip`* y *`state`* son como las eVars, que caducan inmediatamente.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 50 bytes | state | Conversión &gt; Perfil del visitante &gt; Estado de visitante | "" |

Debido a que *`state`* y *`zip`* caducan de inmediato, los únicos eventos asociados a ellas son los que se activan en la misma página en la que se rellenan. Por ejemplo: si está utilizando *`state`* para comparar las tasas de conversión por estado, debe llenar la variable *`state`* en cada página del proceso de cierre de compra. Para los sitios de conversión, Adobe recomienda usar la dirección de facturación como fuente del código postal, pero puede elegir usar la dirección de envío en su lugar (suponiendo que solo haya una dirección de envío para el pedido). Un sitio multimedia puede elegir usar *`zip`* y *`state`* para el registro o seguimiento de pulsaciones.

**Sintaxis y valores posibles** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

La variable *`state`* no impone ningún valor especial o restricciones de formato. No existen limitaciones de *`state`* además de las limitaciones estándar de las variables.

**Ejemplos** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**Parámetros de configuración** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

Ninguna

**Problemas, preguntas y consejos** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* Rellene *`state`* en todas las páginas en las que se activó un evento relevante (todas las páginas del proceso de cierre de compra).
* Las variables *`zip`* y *`state`* actúan como eVars que caducan en la vista de las páginas.
