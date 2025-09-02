---
title: Implementar Adobe Analytics con Adobe Experience Platform Edge
description: Información general sobre el uso de datos XDM de Experience Platform en Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 0ea86e7628e3cebe6f5fe1c4f584da1186b8cb83
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 16%

---

# Implementación de Adobe Analytics con la red Edge de Adobe Experience Platform

La red Edge de Adobe Experience Platform le permite enviar datos destinados a varios productos a una ubicación centralizada. La red Edge reenvía la información adecuada a los productos deseados. Este concepto le permite consolidar los esfuerzos de implementación, especialmente abarcando varias soluciones de datos. Adobe Analytics es uno de los productos a los que puede enviar datos mediante Edge Network.

## Cómo gestiona Adobe Analytics los datos de la red Edge

Dado que los datos enviados a Edge Network y a AppMeasurement funcionan de forma diferente, la carga útil de Edge Network determina cómo Adobe Analytics gestiona la visita. Consulte [Tipos de eventos de Edge Network en Adobe Analytics](hit-types.md) para obtener más información.

Los datos enviados a Adobe Experience Platform Edge Network pueden tener tres formatos: **objeto XDM**, **objeto de datos** y **datos de contexto**. Cuando un conjunto de datos reenvía datos a Adobe Analytics, se traducen a un formato que Adobe Analytics puede gestionar.

## `xdm` objeto

Se ajustan a los esquemas que cree en función de [XDM](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/home) (modelo de datos de experiencia). XDM le proporciona flexibilidad en los campos que se definen como parte de los eventos. Si desea utilizar un esquema predefinido específico de Adobe Analytics, puede agregar el [grupo de campos de esquema Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) a su esquema. Una vez agregado, puede rellenar este esquema con el objeto `xdm` en Web SDK para enviar datos a un grupo de informes. Cuando los datos llegan a Edge Network, traducen el objeto XDM a un formato que Adobe Analytics comprende.

Consulte [Asignación de variables de objeto XDM a Adobe Analytics](xdm-var-mapping.md) para obtener una referencia completa de los campos XDM y cómo se asignan a las variables de Analytics.

>[!TIP]
>
>Si planea pasar a [Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-landing) en el futuro, Adobe aconseja no usar el grupo de campos de esquema de Adobe Analytics. En su lugar, Adobe recomienda [crear su propio esquema](https://experienceleague.adobe.com/es/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect) y usar la asignación de secuencia de datos para rellenar las variables de Analytics que desee. Esta estrategia no le bloquea en un esquema de props y eVars cuando está listo para realizar el movimiento a Customer Journey Analytics.

## `data` objeto

Como alternativa al uso del objeto `xdm`, puede usar el objeto `data` en su lugar. El objeto de datos está dirigido a implementaciones que actualmente utilizan AppMeasurement, lo que facilita la actualización a Web SDK. Edge Network detecta la presencia de campos específicos de Adobe Analytics sin necesidad de ajustarse a un esquema.

Consulte [Asignación de variables de objetos de datos a Adobe Analytics](data-var-mapping.md) para obtener una referencia completa de los campos de objetos de datos y cómo se asignan a las variables de Analytics.

## Variables de datos de contexto

Envíe datos a Edge Network en el formato que desee. Los campos que no se asignen automáticamente a los campos de objeto `xdm` o `data` se incluyen como [variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) cuando se reenvían a Adobe Analytics. Debe usar [Reglas de procesamiento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md) para asignar los campos deseados a sus respectivas variables de Analytics.

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

A continuación, estos campos son las claves de datos de contexto disponibles en la interfaz de reglas de procesamiento:

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
