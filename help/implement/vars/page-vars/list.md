---
title: list
description: Variables personalizadas que contienen varios valores en la misma visita.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '363'
ht-degree: 100%

---


# list

Las variables “list” (lista) son variables personalizadas que se pueden utilizar como desee. Funcionan de manera similar a las eVars, excepto que pueden contener varios valores en la misma visita. Las variables de lista no tienen un límite de caracteres.

Asegúrese de registrar la forma en que utiliza cada variable de lista y su lógica en el [documento de diseño de la solución](../../prepare/solution-design.md).

>[!NOTE]
>
>Las variables de lista almacenan los últimos 250 valores por visitante. Si hay más de 250 valores únicos para un visitante determinado, los valores más antiguos no se atribuyen a las métricas.

## Configure variables de lista en la configuración del grupo de informes

Asegúrese de configurar cada variable de lista en la configuración del grupo de informes antes de usarla en la implementación. Consulte [Variables de conversión](/help/admin/admin/conversion-var-admin/list-var-admin.md) en la guía de administración.

## Variables de lista en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## “s.list1 - s.list3” en el editor de código personalizado de AppMeasurement y Launch

Cada variable de lista es una cadena que contiene valores personalizados específicos de su organización. No tienen un máximo de bytes; sin embargo, cada valor individual tiene un máximo de 255 bytes. El delimitador que utilice se determina al configurar la variable en la configuración del grupo de informes. No utilice espacios al delimitar varios elementos.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Si establece valores duplicados en la misma visita, Adobe anula la duplicación de todas las instancias de esos valores. Por ejemplo, si se establece `s.list1 = "Example,Example";`, en los informes se cuenta como una instancia.

## Comparar props de lista con variables de lista

Las props de lista y las variables de lista pueden contener varios valores en una misma visita. Sin embargo, existen varias diferencias clave entre estos dos tipos de variables.

* Cualquier propiedad puede convertirse en una prop de lista. Puede tener hasta 75 props de lista si todas las propiedades son props de lista. Solo hay 3 variables de lista disponibles.
* Las props de lista tienen un límite de 100 bytes para toda la variable. Las variables de lista tienen un límite de 255 bytes por valor y no tienen un límite de bytes total.
* Las props de lista no se mantienen más allá de la visita en la que están configuradas. A las variables de lista se les puede incluir en la configuración la caducidad que se desee. Sin embargo, con el [procesamiento del tiempo de los informes](/help/components/vrs/vrs-report-time-processing.md), puede aplicar un atributo personalizado tanto a las props de lista como a las variables de lista.
