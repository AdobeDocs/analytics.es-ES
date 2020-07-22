---
title: Prop
description: Dimensión personalizada que se puede utilizar en sistema de informes.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 26%

---


# Prop

*Esta página de ayuda describe cómo funcionan las props como dimensiones. For information on how to implement props, see[props](/help/implement/vars/page-vars/prop.md)in the Implement user guide.*

Las propiedades son variables personalizadas que se pueden utilizar como desee. No persisten más allá de la visita que se establece.

>[!TIP]
>
>Adobe recommends using [eVars](evar.md) in most cases. En versiones anteriores de Adobe Analytics, las props y las eVars tenían ventajas y desventajas entre sí. Sin embargo, Adobe ha mejorado las eVars y ahora sirven para todos los casos prácticos de las props.

Si tiene un documento [de diseño de](/help/implement/prepare/solution-design.md)soluciones, puede asignar estas dimensiones personalizadas a valores específicos de su organización. El número de propiedades disponibles depende del contrato con Adobe. Hay disponibles hasta 75 props si su contrato con Adobe lo admite.

## Rellenar propiedades con datos

Cada propiedad recopila datos de la cadena [`c1` - `c75` de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. Por ejemplo, el parámetro de cadena de `c1` consulta recopila datos para prop1, mientras que el parámetro de cadena de `c68` consulta recopila datos para prop68.

AppMeasurement, que compila variables JavaScript en una solicitud de imagen para la recopilación de datos, utiliza las variables `prop1` - `prop75`. Consulte [prop](/help/implement/vars/page-vars/prop.md) en la Guía del usuario de implementación para ver las directrices de implementación.

## Elementos de dimensión

Dado que las props contienen cadenas personalizadas en la implementación, la organización determina qué son los elementos de dimensión para cada propiedad. Asegúrese de registrar el propósito de cada propiedad y los elementos de dimensión típicos en un documento [de diseño de](/help/implement/prepare/solution-design.md)solución.

## Valor de las props sobre las eVars

Adobe recomienda utilizar eVars en la mayoría de los casos. Las excepciones a esta declaración son las siguientes:

* Puede utilizar props en informes en tiempo real. Las eVars tardan al menos 30 minutos en aparecer en el sistema de informes.
* Las props pueden convertirse en props de lista, que aceptan varios valores en la misma visita. Las variables de lista son una variable independiente y sólo hay tres variables de lista disponibles.
* Al habilitar las rutas en una propiedad, las dimensiones [Entrada](entry-dimensions.md) y [Salida](exit-dimensions.md) estarán disponibles inmediatamente. Si desea dimensiones de entrada y salida para eVars, puede crear manualmente un segmento.

Consulte [eVar](evar.md) para obtener más comparaciones entre props y eVars.
