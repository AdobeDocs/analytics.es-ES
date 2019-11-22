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



# props de lista

Las props de lista son una lista delimitada de valores que se pasan a una variable y, a continuación, se incluyen en los informes como elementos de línea individuales. Las props de lista generalmente se implementan en páginas que contienen valores seleccionables por el usuario como, por ejemplo, elementos enumerados con casillas de verificación o botones de opción. Resultan útiles para aquellos casos en los que desea definir varios valores en una variable sin enviar varias solicitudes de imagen.


<!-- 

list_props.xml

 -->

**Consideraciones**

* Las props de lista solo se activan en variables de tráfico ( [props](/help/implement/js-implementation/page-variables/propn.md)).
* No se puede habilitar el control de rutas ni las correlaciones para las props de lista.
* Analytics proporciona visitas y visitantes únicos prácticamente en todos los informes, incluidos los informes de props de lista.
* Las clasificaciones son compatibles con las props de lista.
* Cualquier variable de tráfico personalizado puede convertirse en una prop de lista. (Excepciones: [pageName](/help/implement/js-implementation/page-variables/pagename.md), [channel](/help/implement/js-implementation/page-variables/channel.md) y [server](/help/implement/js-implementation/page-variables/server.md)).

* Cuando se definen valores duplicados en la misma solicitud de página, no se anula la duplicación de instancias.

Una prop puede cambiarse a una prop de lista en la página Herramientas de administración &gt; Grupo de informes &gt; Variables de tráfico al habilitar la compatibilidad de lista y luego seleccionar un delimitador. Los delimitadores habituales son: dos puntos, punto y coma, coma o barra vertical. Técnicamente puede ser cualquiera de los primeros 127 caracteres ASCII.

**Ejemplos de implementación**

Cuando solicite la activación de props de lista, indique el delimitador que desea usar. Después de que la *`s.prop`* que elija se active, se pueden configurar múltiples valores en la variable tal como se muestra en los ejemplos siguientes:

Una prop de lista delimitada por una barra vertical que pasa dos valores:

```js
s.prop1="Banner ad impression|Sidebar impression"
```

Una prop de lista delimitada por una coma que pasa varios valores:

```js
s.prop2="cerulean,vermilion,saffron"
```

Las props de lista también se pueden enviar con un único valor:

```js
s.prop3="Single value"
```

El delimitador puede cambiarse en cualquier momento. No obstante, la implementación debe coincidir con el nuevo delimitador. Si no se usa el delimitador correcto, el valor de la prop de lista se tratará en los informes como un solo elemento de línea concatenado.

Como una prop de lista sigue siendo una variable de tráfico, está sujeta a las limitaciones de dichas variables. Las props de lista se limitan a 100 bytes de datos y se ven afectadas por la configuración de la distinción entre mayúsculas y minúsculas.

