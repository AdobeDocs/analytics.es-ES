---
title: maxDelay
description: Determine la cantidad máxima de tiempo que AppMeasurement espera una respuesta de DFA antes de enviar una solicitud de imagen.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 100%

---


# maxDelay

La variable `s.maxDelay` se usa principalmente en Data Connectors de DFA para determinar el tiempo de espera al contactar con el host de DFA. Si Adobe no recibe una respuesta de los servidores de DFA en el período especificado en la esta variable, la conexión se interrumpe y los datos se procesan normalmente. Incluya esta variable en su implementación si le preocupa el tiempo de respuesta de DFA en cada página. Adobe recomienda experimentar con este valor para determinar el período de tiempo de espera óptimo.

Esta variable solo se utiliza en implementaciones que utilizan Data Connectors de DFA. Incluso en implementaciones que utilizan DFA, esta variable es opcional.

## Retraso máximo en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado, según la sintaxis de AppMeasurement.

## s.maxDelay en el editor de código personalizado de AppMeasurement y Launch

La variable `s.maxDelay` es un entero que representa el número de milisegundos que AppMeasurement espera una respuesta de DFA. Si AppMeasurement no recibe una respuesta de DFA a tiempo, se envía una solicitud de imagen a Adobe sin datos de DFA.

```js
s.maxDelay = 750;
```

## Propiedades

* Al aumentar el tiempo de espera se recopilan más datos de DFA, pero también aumenta el riesgo de perder datos de visitas de Analytics. Los datos de visitas de Analytics se pierden si el usuario sale de la página durante el tiempo de `s.maxDelay`.
* Reducir el tiempo de espera reduce el riesgo de perder datos de visitas de Analytics, pero puede reducir la cantidad de datos de DFA que se envían con los datos de visitas.
* La pérdida de datos de integración de DFA se produce cuando el período de `s.maxDelay` no concede el tiempo suficiente para que el host de DFA responda.

>[!NOTE]
>
>Adobe no controla el tiempo de respuesta de DFA. Si experimenta problemas continuos incluso después de aumentar el tiempo de retraso máximo a un valor razonable, consulte con el administrador de cuentas DFA de su organización.
