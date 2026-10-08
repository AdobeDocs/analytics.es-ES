---
title: Resultados de la auditoría en el asistente de actualización de Web SDK
description: Revise y resuelva las recomendaciones de limpieza opcionales de los componentes de etiquetas antes de migrar a Web SDK.
feature: Implementation Basics
role: Admin, Developer, Leader
badge: Beta
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 629efca210346d32b8555c60f7db15d1d8285b20
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 2%
---
# Conclusiones de auditoría

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_auditfindings"
>title="Conclusiones de auditoría"
>abstract="Los resultados indican las reglas y los elementos de datos que es posible que desee limpiar antes de migrar, como los elementos de datos a los que no hace referencia nada. Acepte un resultado para incluir su cambio recomendado en la migración o rechácelo para dejar el componente tal cual. Este paso es opcional."

<!-- markdownlint-enable MD034 -->

El asistente de actualización comprueba las reglas y los elementos de datos seleccionados en [selección de componentes](component-selection.md) e indica los que es posible que desee limpiar antes de migrar:

* Duplicar reglas, o reglas que comparten eventos y condiciones, que se podrían consolidar
* Secuencias de acciones de reglas que podrían afectar a la precisión de los datos
* Elementos de datos duplicados que se pueden consolidar.
* Elementos de datos que pueden no usarse y que se pueden deshabilitar

Este paso es opcional. Puede resolver todos los hallazgos que quiera o continuar directamente con la [verificación del grupo de informes](rs-verification.md).

## Revisión de un resultado {#review}

Seleccione una búsqueda para ver sus detalles, que incluyen:

* Una descripción de la búsqueda
* La configuración actual del componente
* Dónde se utiliza el componente, tanto en la propiedad de etiquetas como en Adobe Analytics

Cada resultado incluye una acción recomendada, que depende del tipo de resultado. Por ejemplo, la acción recomendada para un elemento de datos al que no se hace referencia es deshabilitarlo.

>[!IMPORTANT]
>
>Se puede hacer referencia de forma dinámica o desde fuera de las etiquetas a un elemento de datos marcado como no utilizado. Antes de aceptar una búsqueda, compruebe sus cambios propuestos, código personalizado, orden de acción y referencias para confirmar que conservan el comportamiento deseado.

## Resolver conclusiones {#resolve}

Cuando se realiza la acción recomendada de una conclusión, se acepta la conclusión. El asistente de actualización agrega el cambio a la migración y lo aplica cuando [finaliza la migración](final-review.md#finalize). Si no desea realizar el cambio, rechace el resultado en su lugar.

Si cambia de opinión, puede volver a abrir un resultado aceptado o rechazado. Para actualizar varias conclusiones a la vez, selecciónelas en la lista.
