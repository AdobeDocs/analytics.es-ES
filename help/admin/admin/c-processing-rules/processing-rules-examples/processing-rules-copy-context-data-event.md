---
description: Las reglas de procesamiento pueden activar eventos basados en variables de datos de contexto.
seo-description: Las reglas de procesamiento pueden activar eventos basados en variables de datos de contexto.
seo-title: Configurar un evento usando una variable de datos de contexto
solution: Analytics
subtopic: Reglas de procesamiento
title: Configurar un evento usando una variable de datos de contexto
topic: Herramientas de administración
uuid: 4 a 6018 eb -03 e 2-4 ec 8-874 b-e 48 bf 716 e 103
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Configurar un evento usando una variable de datos de contexto

Las reglas de procesamiento pueden activar eventos basados en variables de datos de contexto.

Las variables de datos de contexto se especifican en AppMeasurement con el formato siguiente:

```
 s.contextData['search_term']
```

La lista de [!UICONTROL variables de contexto] incluye todas las variables que se enviaron al grupo de informes durante los 30 días previos. Si conoce el nombre de la variable de datos de contexto pero no la ha enviado al grupo de informes actual, puede agregar un valor escribiendo el nombre de la variable y haciendo clic en **[!UICONTROL Agregar datos de contexto de nombre de variable]**:

![](assets/add-context-variable.png)

The following rule definition expands on the [Copy a Context Data Variable to an eVar](../../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7) rule to also set an event on every hit that contains a specific context data variable:

| Conjunto de reglas | Valor |
|---|---|
| Condición | Si los datos de contexto 'término_de_búsqueda' están definidos |
| Acción | Definir el evento "búsquedas" |

Por ejemplo:

![](assets/processing_rule_set_event.png)

Consulte [Variables de datos de contexto](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables) en la ayuda de implementación.
