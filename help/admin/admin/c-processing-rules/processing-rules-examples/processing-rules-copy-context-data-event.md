---
description: Las reglas de procesamiento pueden activar eventos basados en variables de datos de contexto.
subtopic: Processing rules
title: Definir un evento con una variable de datos de contexto
topic: Admin tools
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# Definir un evento con una variable de datos de contexto

Las reglas de procesamiento pueden activar eventos basados en variables de datos de contexto.

Las variables de datos de contexto se especifican en AppMeasurement con el formato siguiente:

```
 s.contextData['search_term']
```

The [!UICONTROL Context Variables] list contains all variables that were sent to the report suite in the previous 30 days. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

La siguiente definición de regla se expande en la regla [Copiar una variable de datos de contexto a una eVar](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) para establecer también un evento en cada visita que contenga una variable de datos de contexto específica:

| Conjunto de reglas | Valor |
|---|---|
| Condición | Si los datos de contexto &#39;término_de_búsqueda&#39; están definidos |
| Acción | Definir el evento &quot;búsquedas&quot; |

Por ejemplo:

![](assets/processing_rule_set_event.png)

Consulte [Variables de datos de contexto](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) en la ayuda de implementación.
