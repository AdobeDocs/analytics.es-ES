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


# maxDelay

La variable s.maxDelay se usa principalmente en integraciones de DFA de Genesis para determinar el tiempo de espera al contactar con el host DFA. Si Adobe no recibe una respuesta de los servidores DFA en el período configurado en la variable  la conexión se interrumpe y los datos se procesan normalmente. Implemente esta variable si le preocupa el tiempo de respuesta de DFA en cada página. Se recomienda experimentar con este valor para determinar el tiempo de espera óptimo.


<!-- 

maxDelay.xml

 -->

**Ejemplo de implementación**

```
s.maxDelay="750";
```

**Propiedades**

* Esta variable es una métrica de evento opcional que se rellena mediante el código JavaScript implementado en el sitio.
* Si el host DFA no responde en el tiempo especificado, se ejecuta el evento designado para Timeout (que se asigna mediante el asistente para la integración con Genesis).
* Esta variable solo puede contener un valor numérico.
* La cantidad de tiempo especificada se mide en milisegundos.
* Al aumentar el tiempo de espera se recopilan más datos de DFA, pero también aumenta el riesgo de perder datos de visitas de Analytics.

   Los datos de visitas de Analytics se perderían si el usuario sale de la página durante el tiempo de *`s.maxDelay`*.

* Reducir el tiempo de espera reducirá el riesgo de perder datos de visitas de Analytics, pero puede reducir la cantidad de datos de DFA que se envían con los datos de visitas.

   La pérdida de datos de integración de DFA se produce cuando el período de *`s.maxDelay`* no concede el tiempo suficiente para que el host de DFA responda.

> [!NOTE] Adobe no controla el tiempo de respuesta de DFA. Si experimenta problemas continuos incluso después de aumentar el tiempo de demora máximo a un valor razonable, consulte con el administrador de cuentas DFA de su organización.
