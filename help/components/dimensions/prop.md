---
title: Prop
description: Dimensión personalizada que se puede utilizar en sistema de informes.
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '467'
ht-degree: 100%

---

# Prop

*Esta página de ayuda describe cómo funcionan las propiedades (props) como una dimensión. Para obtener información sobre cómo implementar props, consulte [props](/help/implement/vars/page-vars/prop.md) en la guía del usuario sobre implementación.*

Las propiedades son variables personalizadas que se pueden utilizar como desee. No se mantienen más allá de la visita en la que están configuradas.

>[!TIP]
>
>Adobe recomienda utilizar [eVars](evar.md) en la mayoría de los casos. En versiones anteriores de Adobe Analytics, las props y las eVars tenían ventajas y desventajas entre sí. Sin embargo, Adobe ha mejorado las eVars y ahora sirven para todos los casos prácticos de las props.

Si tiene un [documento de diseño de soluciones](/help/implement/prepare/solution-design.md), puede asignar estas dimensiones personalizadas a valores específicos de su organización. El número de propiedades disponibles depende del contrato con Adobe. Hay disponibles hasta 75 props si su contrato con Adobe lo admite.

## Rellenar props con datos

Cada propiedad recopila datos de las cadenas de consulta [`c1` - `c75` ](/help/implement/validate/query-parameters.md) en solicitudes de imagen. Por ejemplo, el parámetro de cadena de consulta `c1` recopila datos para prop1, mientras que el parámetro de cadena de consulta `c68` recopila datos para prop68.

AppMeasurement, que compila variables JavaScript en una solicitud de imagen para la recopilación de datos, utiliza las variables `prop1` - `prop75`. Consulte [prop](/help/implement/vars/page-vars/prop.md) en la Guía del usuario sobre implementación para ver las directrices de implementación.

## Elementos de dimensión

Dado que las props contienen cadenas personalizadas en la implementación, la organización determina los elementos de dimensión de cada propiedad. Asegúrese de registrar el propósito de cada prop y los valores de dimensión típicos en un [documento de diseño de solución](/help/implement/prepare/solution-design.md).

## Distinción entre mayúsculas y minúsculas

De forma predeterminada, las props no distinguen entre mayúsculas y minúsculas. Si envía el mismo valor en casos diferentes (por ejemplo, `"DOG"` y `"Dog"`), Analysis Workspace los agrupa en el mismo elemento de dimensión. Se utiliza el caso del primer valor visto al comienzo del mes de creación de informes. Data Warehouse muestra el primer valor que se encuentra durante el período de solicitud.

Puede hacer que cualquier prop distinga mayúsculas de minúsculas. También puede deshabilitar la distinción entre mayúsculas y minúsculas en cualquier prop una vez que esté habilitada. Póngase en contacto con el Servicio de atención al cliente de Adobe con el ID del grupo de informes y las variables deseadas para alternar la distinción entre mayúsculas y minúsculas.

>[!IMPORTANT]
>
>Alternar la distinción entre mayúsculas y minúsculas puede acotar los elementos de dimensión, provocar resultados inesperados con los segmentos y causar problemas con los filtros. Adobe recomienda encarecidamente alternar esta configuración entre dos periodos de tiempo principales, como el inicio de un mes o año.

## Valor de las props sobre las eVars

Adobe recomienda utilizar eVars en la mayoría de los casos. Las excepciones a esta declaración son las siguientes:

* Puede utilizar props en informes en tiempo real. Las eVars tardan al menos 30 minutos en aparecer en el sistema de informes.
* Las props pueden convertirse en props de lista, que aceptan varios valores en la misma visita. Las variables de lista son una variable independiente y sólo hay tres variables de lista disponibles.
* Al habilitar las rutas en una propiedad, las dimensiones [Entrada](entry-dimensions.md) y [Salida](exit-dimensions.md) estarán disponibles inmediatamente. Si desea dimensiones de entrada y salida para eVars, puede crear manualmente un segmento.

Consulte [eVar](evar.md) para ver más comparaciones entre props y eVars.
