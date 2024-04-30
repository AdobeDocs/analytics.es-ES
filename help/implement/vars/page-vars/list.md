---
title: list
description: Variables personalizadas que contienen varios valores en la misma visita.
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
role: Admin, Developer
source-git-commit: 7c8ffe8f4ccf0577136e4d7ee96340224897d2a4
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 74%

---

# list

Las variables “list” (lista) son variables personalizadas que se pueden utilizar como desee. Funcionan de manera similar a las eVars, excepto que pueden contener varios valores en la misma visita. Las variables de lista no tienen un límite de caracteres.

Asegúrese de registrar la forma en que utiliza cada variable de lista y su lógica en el [documento de diseño de la solución](../../prepare/solution-design.md).

>[!NOTE]
>
>Las variables de lista almacenan los valores más recientes por visitante en función de su [!UICONTROL Valores máximos] configuración en [Configuración del grupo de informes](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). Se admiten hasta 250 valores. Si hay más valores únicos que lo que [!UICONTROL Valores máximos] La configuración de permite que los valores más antiguos no se atribuyan a las métricas.

## Configure variables de lista en la configuración del grupo de informes

Asegúrese de configurar cada variable de lista en la configuración del grupo de informes antes de usarla en la implementación. Consulte [Variables de conversión](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md) en la guía de administración. Este paso se aplica a todos los métodos de implementación.

## Variables de lista mediante el SDK web

Si se usa la variable [**Objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), las variables de lista utilizan los campos XDM `xdm._experience.analytics.customDimensions.lists.list1.list[]` hasta `xdm._experience.analytics.customDimensions.lists.list3.list[]`. Cada elemento de matriz contiene un objeto `"value"` que engloba cada cadena. No es necesario proporcionar un delimitador; los servidores de recopilación de datos de Adobe detectan e incluyen automáticamente el delimitador correcto establecido en [Configuración del grupo de informes](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md).

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

>[!NOTE]
>
>El esquema XDM de Adobe contiene objetos `key`, además de objetos `value` en cada matriz `list[]`. Adobe no emplea estos objetos `key` al enviar datos a Adobe Analytics.

Si se usa la variable [**objeto de datos**](/help/implement/aep-edge/data-var-mapping.md), las variables de lista utilizan `data.__adobe.analytics.list1` - `data.adobe.analytics.list3` siguiente sintaxis de AppMeasurement. Asegúrese de utilizar el delimitador correcto establecido en [Configuración del grupo de informes](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md).

```json
"data": {
  "__adobe": {
    "analytics": {
      "list1": "Example value 1,Example value 2,Example value 3"
    }
  }
}
```

## Variables de lista mediante la extensión de Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.list1 - s.list3 en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Cada variable de lista es una cadena que contiene valores personalizados específicos de su organización. Esta variable no tiene un número máximo de bytes; sin embargo, cada valor individual tiene un límite máximo de 255 bytes. El delimitador que utilice se determina al configurar la variable en la [configuración del grupo de informes](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). No utilice espacios al delimitar varios elementos.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Si establece valores duplicados en la misma visita, Adobe anula la duplicación de todas las instancias de esos valores. Por ejemplo, si se establece `s.list1 = "Brick,Brick";`, en los informes se cuenta como una instancia.

## Comparar props de lista con variables de lista

Las props de lista y las variables de lista pueden contener varios valores en una misma visita. Sin embargo, existen varias diferencias clave entre estos dos tipos de variables.

* Cualquier propiedad puede convertirse en una prop de lista. Puede tener hasta 75 props de lista si todas las propiedades son props de lista. Solo hay tres variables de lista disponibles.
* Las props de lista tienen un límite de 100 bytes para toda la variable. Las variables de lista tienen un límite de 255 bytes por valor y no tienen un límite de bytes total.
* Las props de lista no se mantienen más allá de la visita en la que están configuradas. A las variables de lista se les puede incluir en la configuración la caducidad que se desee. Sin embargo, con el [procesamiento del tiempo de los informes](/help/components/vrs/vrs-report-time-processing.md), puede aplicar un atributo personalizado tanto a las props de lista como a las variables de lista.
