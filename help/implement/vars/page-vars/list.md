---
title: list
description: Variables personalizadas que contienen varios valores en la misma visita.
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# list

Las variables de lista son variables personalizadas que se pueden utilizar como desee. Funcionan de manera similar a las eVars, excepto que pueden contener varios valores en la misma visita. Las variables de lista no tienen un límite de caracteres.

Asegúrese de registrar la forma en que utiliza cada variable de lista y su lógica en el documento [de diseño de la](../../prepare/solution-design.md)solución.

> [!NOTE] Las variables de lista almacenan los últimos 250 valores por visitante. Si hay más de 250 valores únicos para un visitante determinado, los valores más antiguos no se atribuyen a las métricas.

## Configuración de variables de lista en la configuración del grupo de informes

Asegúrese de configurar cada variable de lista en la configuración del grupo de informes antes de usarla en la implementación. See [Conversion variables](/help/admin/admin/conversion-var-admin/list-var-admin.md) in the Admin guide.

## Mostrar variables en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.list1 - s.list3 en el editor de código personalizado de AppMeasurement e Launch

Cada variable de lista es una cadena que contiene valores personalizados específicos de su organización. No tienen un recuento máximo de bytes; sin embargo, cada valor individual tiene un máximo de 255 bytes. El delimitador que utilice se determina al configurar la variable en la configuración del grupo de informes. No utilice espacios al delimitar varios elementos.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

> [!TIP] Si establece valores duplicados en la misma visita, Adobe anula la duplicación de todas las instancias de esos valores. Por ejemplo, si se establece `s.list1 = "Example,Example";`, en los informes se cuenta una instancia.

## Comparar props de lista con variables de lista

Las props de lista y las variables de lista pueden contener varios valores en la misma visita. Sin embargo, existen varias diferencias clave entre estos dos tipos de variables.

* Cualquier propiedad puede convertirse en una prop de lista. Puede tener hasta 75 props de lista si cada prop es una prop de lista. Solo hay 3 variables de lista disponibles.
* Las props de lista tienen un límite de 100 bytes para toda la variable. Las variables de lista tienen un límite de 255 bytes por valor y no tienen un límite de bytes total.
* Las props de lista no persisten más allá de la visita que están configuradas. Las variables de lista tienen cualquier configuración de caducidad que desee. Sin embargo, con el procesamiento [del tiempo de los](/help/components/vrs/vrs-report-time-processing.md)informes, puede aplicar una atribución personalizada tanto a las propiedades de lista como a las variables de lista.
