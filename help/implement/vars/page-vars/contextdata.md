---
title: contextData
description: Las variables de datos de contexto permiten definir variables personalizadas en cada página que puedan leer las reglas de procesamiento.
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '431'
ht-degree: 100%

---

# contextData

Las variables de datos de contexto permiten definir variables personalizadas en cada página que puedan leer las reglas de procesamiento. En lugar de asignar explícitamente valores a variables de Analytics en el código, puede enviar datos en variables de datos de contexto. Las reglas de procesamiento toman valores de variables de datos de contexto y los pasan a las variables de Analytics correspondientes. Consulte [Reglas de procesamiento](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) en la guía de usuario de administración.

Las variables de datos de contexto son útiles para que los equipos de desarrollo recopilen datos en elementos con nombre en lugar de variables numeradas. Por ejemplo, en lugar de solicitar que los equipos de desarrollo asignen al autor de la página a `eVar10`, puede solicitar que se asigne a `s.contextData["author"]`. Un administrador de Analytics de su organización puede crear reglas de procesamiento para asignar variables de datos de contexto a variables de análisis para los informes. En última instancia, los equipos de desarrollo solo se preocuparían por las variables de datos de contexto en lugar de por las variables de página que ofrece Adobe.

## Variables de datos de contexto en Adobe Experience Platform Launch

Launch no tiene una ubicación dedicada para establecer variables de datos de contexto. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.contextData en el editor de código personalizado de AppMeasurement y Launch

La variable `s.contextData` no toma directamente un valor. En su lugar, establezca las propiedades de esta variable en una cadena.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Las variables válidas de datos de contexto solo contienen caracteres alfanuméricos, guiones bajos y puntos. Adobe no garantiza la recopilación de datos en las reglas de procesamiento si se incluyen otros caracteres, como guiones.
* No inicie variables de datos de contexto con `"a."`. Adobe reserva y utiliza este prefijo. Por ejemplo, no utilice `s.contextData["a.InstallEvent"]`.
* Las variables de datos de contexto no distinguen entre mayúsculas y minúsculas. Las variables `s.contextData["example"]` y `s.contextData["EXAMPLE"]` son idénticas.

## Usar reglas de procesamiento para rellenar variables de análisis

>[!IMPORTANT]
>
>Las variables de datos de contexto se descartan después de ejecutar las reglas de procesamiento. Si no tiene reglas de procesamiento activas que coloquen valores en variables, esos datos se pierden de forma permanente.

1. Actualice la implementación para establecer los nombres y valores de las variables de datos de contexto.
2. Inicie sesión en Adobe Analytics y vaya a Administración > Grupos de informes.
3. Seleccione el grupo de informes correcto y, a continuación, vaya a Editar configuración > General > Reglas de procesamiento.
4. Cree una regla de procesamiento que establezca una variable de Analytics en el valor de la variable de datos de contexto.
5. Guarde los cambios.

Las reglas de procesamiento se aplican inmediatamente una vez guardadas. No se aplican a los datos históricos.

## Enviar datos de contexto en una llamada de seguimiento de vínculos

Incluya la variable de datos de contexto como una propiedad de `contextData` en [`s.linkTrackVars`](../config-vars/linktrackvars.md):

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```

## Incremento de eventos mediante variables de datos de contexto

Al crear reglas de procesamiento, puede asignar variables de datos de contexto a eventos.

* Si una variable de datos de contexto contiene cualquier tipo de texto, el evento se incrementa en uno.
* Si una variable de datos de contexto contiene un número entero, el evento se incrementa en esa cantidad total.

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
