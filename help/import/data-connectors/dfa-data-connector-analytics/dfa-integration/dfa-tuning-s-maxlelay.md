---
description: Lograr una implementación correcta de DFA implica optimizar s.maxDelay para el sitio específico.
keywords: DFA
seo-description: Lograr una implementación correcta de DFA implica optimizar s.maxDelay para el sitio específico.
seo-title: Ajuste de s.maxDelay
solution: Analytics
title: Ajuste de s.maxDelay
topic: Data Connectors
uuid: 7640 af 26-6 ac 6-427 e -9 cfc -932 c 86 session 5 ab
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Ajuste de s.maxDelay{#tuning-s-maxdelay}

Lograr una implementación correcta de DFA implica optimizar s.maxDelay para el sitio específico.

En general, la decisión de aumentar o disminuir *`s.maxDelay`* implica un equilibrio entre obtener más datos de visitantes DFA y poner en riesgo la recopilación de datos de visitantes de Adobe. Increasing *`s.maxDelay`* obtains more DFA visitor data, but (placed excessively high) could endanger the collection of Adobe visitor data. Al reducir s.maxDelay se garantiza la recopilación de datos del visitante de Adobe, pero podría perder datos del visitante de DFA.

*`s.maxDelay`* encapsula más que solo el tiempo en la comunicación de red para ponerse en contacto con DFA; también representa demoras del explorador para activar y evaluar el JavaScript desde el cual se basan estas comunicaciones. Esto se debe a que el módulo Integrate comienza el *`s.maxDelay`* temporizador después de haber insertado el elemento HTML en el DOM que extrae los datos del servidor de Floodlight DFA. La cantidad de tiempo que tarda el explorador en iniciar realmente la solicitud HTTP en función de este nuevo elemento HTML varía en función de otras imágenes o archivos JavaScript que se cargan simultáneamente, la velocidad del equipo del visitante e implementaciones específicas de exploradores. Además, cuando los datos de JSON se recuperan del servidor de Floodlight DFA, el explorador debe evaluar el JavaScript. El explorador nuevamente controla esto por completo y puede demorarlo si existe una gran cantidad de código JavaScript ejecutándose simultáneamente o muchas solicitudes JavaScript asincrónicas.

Teniendo en cuenta esto, *`s.maxDelay`* debe establecerse en función de la complejidad de la página de aterrizaje más la demora de red con DFA. En algunos sitios, una forma posible de reducir la complejidad es activar el código de recopilación de Adobe de forma anticipada en la carga de página, de modo que haya menos actividades en el explorador en el momento de realizar una solicitud al servidor de Floodlight.

La variable Timeout es absolutamente necesaria al ajustar *`s.maxDelay`*, porque se incrementa cada vez que se alcanza el tiempo de espera s.maxDelay. Cuando decida si desea aumentar o reducir *`s.maxDelay`* , le recomendamos que siga este proceso:

1. Recopile varios días de datos con *`s.maxDelay`* configurados en un valor concreto.
1. Ejecute un [!DNL Daily Unique Visitors Report] para el intervalo de tiempo.
1. Run the [!DNL Timeout Event Report] to check the number of timeouts that are coming through. Recuerde que un tiempo de espera se recopila una sola vez por visitante.

Ahora teniendo las figuras a mano, calcule

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

Observe que el Porcentaje de tiempo de espera está realmente considerando todos los visitantes del sitio. Algunos de estos visitantes no habrían estado unidos con DFA en absoluto. Por lo tanto, el tiempo de espera es confuso. Para mejorar este cálculo, otro análisis podría considerar solamente los visitantes únicos de las páginas con el `clickThroughParam` establecido (por ejemplo, `?CID=1`). Esto mostrará más exactitud.

Si el Porcentaje de tiempo de espera es muy bajo, considere la posibilidad de reducir *`s.maxDelay`*. Si es muy alto, incremente *`s.maxDelay`*. When decreasing *`s.maxDelay`*, you will want to rerun the [!DNL Timeout Report] to ensure that timeouts have not dramatically increased. When increasing *`s.maxDelay`*, you will want to run a [!DNL Page Views Report] to make sure page views aren’t falling out due to lost data. Each time *`s.maxDelay`* is changed observe the data for several days in order to ensure that the data represents a trend, and not just a day-to-day fluctuation.

The optimal setting for *`s.maxDelay`* is the point at which the timeout percentage is minimized while Page Views do not drop off.

Se espera que los tiempos de espera se reduzcan cuando pasa a la versión 2.0 de la integración, debido a las eliminaciones de redireccionamientos 302. Los hallazgos iniciales con clientes beta han demostrado una reducción coherente en los tiempos de espera, y así se recopilan más datos DFA.
