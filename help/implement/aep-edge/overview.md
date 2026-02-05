---
title: Implementar Adobe Analytics con Adobe Experience Platform Edge
description: Información general sobre el uso de datos XDM de Experience Platform en Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9845f1bc73b6cf5fd932c6896a50379ddd008c20
workflow-type: ht
source-wordcount: '550'
ht-degree: 100%

---

# Implementación de Adobe Analytics con la red Edge de Adobe Experience Platform

La red Edge de Adobe Experience Platform le permite enviar datos destinados a varios productos a una ubicación centralizada. La red Edge reenvía la información adecuada a los productos deseados. Este concepto le permite consolidar los esfuerzos de implementación, especialmente abarcando varias soluciones de datos. Adobe Analytics es uno de los productos a los que puede enviar datos mediante Edge Network.

## Cómo gestiona Adobe Analytics los datos de Edge Network

Dado que los datos enviados a Edge Network y a AppMeasurement funcionan de forma diferente, la carga útil de Edge Network determina cómo Adobe Analytics gestiona la visita. Consulte [Tipos de eventos de Edge Network en Adobe Analytics](hit-types.md) para obtener más información.

Los datos enviados a Adobe Experience Platform Edge Network pueden tener tres formatos: **objeto XDM**, **objeto de datos** y **datos de contexto**. En el momento en que la secuencia de datos reenvía datos a Adobe Analytics, se traducen a un formato que Adobe Analytics puede gestionar.

## Objeto `xdm`

Conformar esquemas que cree basados en [XDM](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/home) (modelo de datos de experiencia). XDM le proporciona flexibilidad en los campos que se definen como parte de los eventos. Si desea utilizar un esquema predefinido específico de Adobe Analytics, puede añadir el [grupo de campos de esquema Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) a su esquema. Una vez añadido, puede rellenar este esquema con el objeto `xdm` en SDK web para enviar datos a un grupo de informes. Cuando los datos llegan a Edge Network, traducen el objeto XDM a un formato que Adobe Analytics comprende.

Consulte [Asignación de variables de objeto XDM a Adobe Analytics](xdm-var-mapping.md) para obtener una referencia completa de los campos XDM y cómo se asignan a las variables de Analytics.

>[!TIP]
>
>Si planea pasar a [Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-landing) en el futuro, Adobe aconseja no usar el grupo de campos de esquema de Adobe Analytics. En su lugar, Adobe recomienda [crear su propio esquema](https://experienceleague.adobe.com/es/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect) y usar la asignación de secuencia de datos para rellenar las variables de Analytics que desee. Esta estrategia no le limita a un esquema de props y eVars cuando está listo para pasar a Customer Journey Analytics.

## Objeto `data`

Como alternativa al uso del objeto `xdm`, puede usar el objeto `data` en su lugar. El objeto de datos está dirigido a implementaciones que actualmente utilizan AppMeasurement, lo que facilita la actualización a SDK web. Edge Network detecta la presencia de campos específicos de Adobe Analytics sin necesidad de ajustarse a un esquema.

Consulte [Asignación de variables de objeto de datos a Adobe Analytics](data-var-mapping.md) para obtener una referencia completa de los campos de objetos de datos y cómo se asignan a las variables de Analytics.

## Variables de datos de contexto

Envíe datos a Edge Network en el formato que desee. Los campos que no se asignen automáticamente a los campos de objeto `xdm` o `data` se incluyen como [variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) cuando se reenvían a Adobe Analytics. Debe usar [Reglas de procesamiento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) para asignar los campos deseados a sus respectivas variables de Analytics.

Por ejemplo, si tuviera un esquema XDM personalizado con el siguiente aspecto:

```json
{
  "xdm": {
    "key": "value",
    "animal": {
      "species": "Raven",
      "size": "13 inches"
    },
    "array": [
      "v0",
      "v1",
      "v2"
    ],
    "objectArray":[{
      "ad1": "300x200",
      "ad2": "60x240",
      "ad3": "600x50"
    }]
  }
}
```

Entonces, estos campos serían las claves de datos de contexto disponibles en la interfaz de reglas de procesamiento:

```javascript
a.x.key // value
a.x.animal.species // Raven
a.x.animal.size // 13 inches
a.x.array.0 // v0
a.x.array.1 // v1
a.x.array.2 // v2
a.x.objectarray.0.ad1 // 300x200
a.x.objectarray.1.ad2 // 60x240
a.x.objectarray.2.ad3 // 600x50
```

El tamaño máximo de una carga útil de variable de datos de contexto determinada (incluidas claves y valores) es 32 KB. Puede reducir el tamaño de esta carga útil ajustando los campos relevantes para que Adobe Analytics los reconozca en los objetos [`xdm`](xdm-var-mapping.md) o [`data`](data-var-mapping.md).
