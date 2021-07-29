---
title: maxDelay
description: Determine la cantidad máxima de tiempo que AppMeasurement espera una respuesta de DFA antes de enviar una solicitud de imagen.
exl-id: 154f7e34-39e7-4390-ae36-d4fbc998787f
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 92%

---

# maxDelay

La variable `s.maxDelay` se usa principalmente en Data Connectors de DFA para determinar el tiempo de espera al contactar con el host de DFA. Si Adobe no recibe una respuesta de los servidores de DFA en el período especificado en la esta variable, la conexión se interrumpe y los datos se procesan normalmente. Incluya esta variable en su implementación si le preocupa el tiempo de respuesta de DFA en cada página. Adobe recomienda experimentar con este valor para determinar el período de tiempo de espera óptimo.

Esta variable solo se utiliza en implementaciones que utilizan Data Connectors de DFA. Incluso en implementaciones que utilizan DFA, esta variable es opcional.

## Retraso máximo con etiquetas en Adobe Experience Platform

No hay un campo dedicado en la interfaz de usuario de recopilación de datos para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.maxDelay en el editor de código personalizado de AppMeasurement y 

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
