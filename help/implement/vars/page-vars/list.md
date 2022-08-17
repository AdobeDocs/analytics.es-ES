---
title: list
description: Variables personalizadas que contienen varios valores en la misma visita.
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
source-git-commit: e8a6400895110a14306e2dc9465e5de03d1b5d73
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 62%

---

# list

Las variables “list” (lista) son variables personalizadas que se pueden utilizar como desee. Funcionan de manera similar a las eVars, excepto que pueden contener varios valores en la misma visita. Las variables de lista no tienen un límite de caracteres.

Asegúrese de registrar la forma en que utiliza cada variable de lista y su lógica en el [documento de diseño de la solución](../../prepare/solution-design.md).

>[!NOTE]
>
>Las variables de lista almacenan los últimos 250 valores por visitante. Si hay más de 250 valores únicos para un visitante determinado, los valores más antiguos no se atribuyen a las métricas.

## Configure variables de lista en la configuración del grupo de informes

Asegúrese de configurar cada variable de lista en la configuración del grupo de informes antes de usarla en la implementación. Consulte [Variables de conversión](/help/admin/admin/conversion-var-admin/list-var-admin.md) en la guía de administración. Este paso se aplica a todos los métodos de implementación.

>[!NOTE]
>
>Las variables de lista implementadas mediante campos asignados en el SDK web utilizan el delimitador predeterminado de una coma (&#39;`,`&quot;).

## Enumerar variables mediante el SDK web

Las variables de lista son [asignado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=es) en los campos XDM `_experience.analytics.customDimensions.lists.list1.list[]` a `_experience.analytics.customDimensions.lists.list3.list[]`. Cada elemento de matriz contiene un `"value"` objeto que contiene cada cadena. Por ejemplo, el siguiente objeto XDM rellena la variable `list1` con `"Example value 1,Example value 2,Example value 3"`.

```json
"xdm": {
    "_experience": {
        "analytics": {
            "customDimensions": {
                "lists": {
                    "list1": {
                        "list": [
                            {
                                "value": "Example value 1"
                            },
                            {
                                "value": "Example value 2"
                            },
                            {
                                "value": "Example value 3"
                            }
                        ]
                    }
                }
            }
        }
    }
}
```

Si su organización requiere un delimitador diferente que una coma (&quot;`,`&#39;), puede pasar toda la cadena de lista, incluidos los delimitadores deseados, a un campo XDM personalizado. Asegúrese de que la variable de lista esté configurada para aceptar el delimitador deseado en [Configuración del grupo de informes](/help/admin/admin/conversion-var-admin/list-var-admin.md).

```json
"xdm": {
    "custom_object": {
        "custom_path": {
            "custom_listvar": "Example value 1|Example value 2|Example value 3"
        }
    }
}
```

A continuación, puede:

* Asigne el campo XDM personalizado a la variable de lista deseada en Adobe Experience Edge; o
* Cree una regla de procesamiento para sobrescribir la variable de lista deseada con la variable de datos de contexto. Consulte [Asignación de otros campos XDM a variables de Analytics](../../aep-edge/variable-mapping.md#mapping-other-xdm-fields-to-analytics-variables).

## Enumerar variables mediante la extensión de Adobe Analytics

No hay un campo específico en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.list1 - s.list3 en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Cada variable de lista es una cadena que contiene valores personalizados específicos de su organización. No tienen un máximo de bytes; sin embargo, cada valor individual tiene un máximo de 255 bytes. El delimitador que utilice se determina al configurar la variable en [Configuración del grupo de informes](/help/admin/admin/conversion-var-admin/list-var-admin.md). No utilice espacios al delimitar varios elementos.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Si establece valores duplicados en la misma visita, Adobe anula la duplicación de todas las instancias de esos valores. Por ejemplo, si se establece `s.list1 = "Brick,Brick";`, en los informes se cuenta como una instancia.

## Comparar props de lista con variables de lista

Las props de lista y las variables de lista pueden contener varios valores en una misma visita. Sin embargo, existen varias diferencias clave entre estos dos tipos de variables.

* Cualquier propiedad puede convertirse en una prop de lista. Puede tener hasta 75 props de lista si todas las propiedades son props de lista. Solo hay 3 variables de lista disponibles.
* Las props de lista tienen un límite de 100 bytes para toda la variable. Las variables de lista tienen un límite de 255 bytes por valor y no tienen un límite de bytes total.
* Las props de lista no se mantienen más allá de la visita en la que están configuradas. A las variables de lista se les puede incluir en la configuración la caducidad que se desee. Sin embargo, con el [procesamiento del tiempo de los informes](/help/components/vrs/vrs-report-time-processing.md), puede aplicar un atributo personalizado tanto a las props de lista como a las variables de lista.
