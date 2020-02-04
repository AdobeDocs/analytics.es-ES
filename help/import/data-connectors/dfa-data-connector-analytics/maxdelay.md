---
title: maxDelay
description: Determine la cantidad máxima de tiempo que AppMeasurement espera una respuesta de DFA antes de enviar una solicitud de imagen.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# maxDelay

The `s.maxDelay` variable is used in the DFA data connector to determine the timeout period in contacting the DFA host. Si Adobe no recibe una respuesta de los servidores de DFA dentro del período especificado en esta variable, la conexión se interrumpe y los datos se procesan normalmente. Incluya esta variable en la implementación si le preocupa el tiempo de respuesta de DFA en cada página. Adobe recomienda experimentar con este valor para determinar el período de tiempo de espera óptimo.

Esta variable solo se utiliza en implementaciones que utilizan el conector de datos DFA. Incluso con implementaciones que utilizan DFA, esta variable es opcional.

## Retraso máximo en el lanzamiento de Adobe Experience Platform

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.maxDelay en el editor de código personalizado AppMeasurement e Launch

La `s.maxDelay` variable es un entero que representa el número de milisegundos que AppMeasurement espera una respuesta de DFA. Si AppMeasurement no recibe una respuesta de DFA a tiempo, se envía una solicitud de imagen a Adobe sin datos de DFA.

```js
s.maxDelay = 750;
```

## Propiedades

* Al aumentar el tiempo de espera se recopilan más datos de DFA, pero también aumenta el riesgo de perder datos de visitas de Analytics. Losing Analytics hit data happens when the user navigates away from the page during the `s.maxDelay` period.
* La disminución del tiempo de espera reduce el riesgo de perder datos de visitas de Analytics, pero puede reducir la cantidad de datos de DFA enviados con datos de visitas.
* Losing DFA integration data happens when the `s.maxDelay` period does not accommodate enough time for the DFA host to respond.

> [!NOTE] Adobe no controla el tiempo de respuesta de DFA. Si observa problemas constantes incluso después de aumentar el período de demora máximo a un intervalo de tiempo razonable, consulte al administrador de cuentas de DFA de su organización.
