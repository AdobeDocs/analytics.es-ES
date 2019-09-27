---
description: Las reglas de procesamiento pueden activar eventos basados en variables de datos de contexto.
seo-description: Las reglas de procesamiento pueden activar eventos basados en variables de datos de contexto.
seo-title: Definir un evento con una variable de datos de contexto
solution: Analytics
subtopic: Reglas de procesamiento
title: Definir un evento con una variable de datos de contexto
topic: Herramientas de administración
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Definir un evento con una variable de datos de contexto

Las reglas de procesamiento pueden activar eventos basados en variables de datos de contexto.

Las variables de datos de contexto se especifican en AppMeasurement con el formato siguiente:

```
 s.contextData['search_term']
```

La lista de [!UICONTROL variables de contexto] incluye todas las variables que se enviaron al grupo de informes durante los 30 días previos. Si conoce el nombre de la variable de datos de contexto pero no la ha enviado al grupo de informes actual, puede agregar un valor escribiendo el nombre de la variable y haciendo clic en **[!UICONTROL Agregar datos de contexto de nombre de variable]**:

![](assets/add-context-variable.png)

La siguiente definición de regla se expande en la regla [Copiar una variable de datos de contexto a una regla eVar](../../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7) para establecer también un evento en cada visita que contenga una variable de datos de contexto específica:

| Conjunto de reglas | Valor |
|---|---|
| Condición | Si los datos de contexto 'término_de_búsqueda' están definidos |
| Acción | Definir el evento "búsquedas" |

Por ejemplo:

![](assets/processing_rule_set_event.png)

Consulte [Variables de datos de contexto](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html) en la ayuda de implementación.
