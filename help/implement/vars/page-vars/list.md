---
title: list
description: Variables personalizadas que contienen varios valores en la misma visita.
feature: Appmeasurement Implementation
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
role: Admin, Developer
TQID: https://experienceleague.adobe.com/LpUX55ZGYgm7Z2-P4uAwH-rV88JMbi2661i4f9RYd-Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 74%

---

# list

Las variables “list” (lista) son variables personalizadas que se pueden utilizar como desee. Funcionan de manera similar a las eVars, excepto que pueden contener varios valores en la misma visita. Las variables de lista no tienen un límite de caracteres.

Asegúrese de registrar la forma en que utiliza cada variable de lista y su lógica en el [documento de diseño de la solución](../../prepare/solution-design.md).

>[!NOTE]
>
>Las variables de lista almacenan los valores más recientes por visitante, según su configuración de [!UICONTROL Valores máximos] en [Configuración del grupo de informes](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md). Se admiten hasta 250 valores. Si hay más valores únicos de los que permite la configuración [!UICONTROL Valores máximos], los valores más antiguos no se atribuyen a las métricas.

## Configure variables de lista en la configuración del grupo de informes

Asegúrese de configurar cada variable de lista en la configuración del grupo de informes antes de usarla en la implementación. Consulte [Variables de conversión](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md) en la guía de administración. Este paso se aplica a todos los métodos de implementación.

## Variables de lista mediante el SDK web

Si se usa el [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), las variables de lista usan los campos XDM `xdm._experience.analytics.customDimensions.lists.list1.list[]` a `xdm._experience.analytics.customDimensions.lists.list3.list[]`. Cada elemento de matriz contiene un objeto `"value"` que engloba cada cadena. No es necesario proporcionar un delimitador; los servidores de recopilación de datos de Adobe detectan e incluyen automáticamente el delimitador correcto establecido en [Configuración del grupo de informes](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md).

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

Si se usa el [**objeto de datos**](/help/implement/aep-edge/data-var-mapping.md), las variables de lista usan de `data.__adobe.analytics.list1` a `data.adobe.analytics.list3` según la sintaxis de AppMeasurement. Asegúrese de usar el conjunto de delimitadores correcto en [Configuración del grupo de informes](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md).

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

Cada variable de lista es una cadena que contiene valores personalizados específicos de su organización. Esta variable no tiene un número máximo de bytes; sin embargo, cada valor individual tiene un límite máximo de 255 bytes. El delimitador que utilice se determina al configurar la variable en la [configuración del grupo de informes](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md). No utilice espacios al delimitar varios elementos.

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
