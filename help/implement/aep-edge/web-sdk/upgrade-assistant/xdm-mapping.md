---
title: Asignación de XDM en el asistente de actualización de Web SDK
description: Asigne las variables de Adobe Analytics a los campos de un esquema XDM como parte de una migración de Web SDK.
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
source-git-commit: 212d38950264a33b925b7281c241992cadca2bfb
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 3%
---
# Asignación de XDM

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping"
>title="Asignación de XDM"
>abstract="Asigne las variables de Analytics seleccionadas a los campos de un esquema XDM. El asistente de actualización puede crear un nuevo esquema con asignaciones sugeridas por IA o puede asignar variables a un esquema que ya tenga. Revise todas las asignaciones antes de continuar."

<!-- markdownlint-enable MD034 -->

Web SDK envía datos mediante [modelos de datos de experiencia (XDM)](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/home) campos, de modo que cada variable de Analytics que transfiera desde [preparación del asignador](mapper-prep.md) necesita un campo coincidente en un esquema XDM. En este paso, elige un esquema y asigna las variables a sus campos.

## Elección de un esquema {#schema}

Puede crear la asignación de una de las dos maneras siguientes:

* **Crear un nuevo esquema**: el asistente de actualización analiza las variables de Analytics, sugiere un campo XDM para cada una y, a continuación, genera un esquema a partir de esas sugerencias para que lo revise.
* **Usar un esquema existente**: seleccione un esquema que ya exista en Experience Platform y asigne cada variable a un campo usted mismo.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping_fieldgroups"
>title="Preferencia del grupo de campos"
>abstract="Elija qué tipo de grupo de campos prefiere el asistente de actualización cuando crea el esquema. Adobe define los grupos de campos estándar. Su organización define los grupos de campos personalizados."

<!-- markdownlint-enable MD034 -->

Al crear un nuevo esquema, también puede elegir si el asistente de actualización prefiere los grupos de campos estándar o personalizados. Los grupos de campos estándar los define Adobe, mientras que los grupos de campos personalizados los define su organización. Consulte [Grupo de campos](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/schema/composition#field-group) en la documentación de XDM.

## Revisión de la asignación {#review}

La asignación enumera cada variable de Analytics junto al campo XDM al que se asigna, con una vista previa del esquema completo junto a ella. Seleccione parte del esquema para filtrar la lista a las variables que se asignan a él. Puede ajustar tanto las asignaciones individuales como el propio esquema.

El asistente de actualización utiliza IA para sugerir asignaciones, y es posible que los resultados no sean precisos o completos. Revise todas las asignaciones antes de continuar. El asistente de actualización no crea el esquema en Experience Platform hasta que [finalice la migración](final-review.md#finalize).

Cuando termines, selecciona **[!UICONTROL Guardar y continuar]** para guardar la asignación y ve a [Implementación de Web SDK](web-sdk-implementation.md). Para cambiar la asignación después de guardarla, selecciona **[!UICONTROL Editar]**, realiza los cambios y luego selecciona **[!UICONTROL Guardar y continuar]** de nuevo. Los cambios que no guarde de esta manera no se incluyen al finalizar la migración.
