---
description: Las reglas de procesamiento se utilizan para mover valores desde variables de datos de contexto a props y eVars.
seo-description: Las reglas de procesamiento se utilizan para mover valores desde variables de datos de contexto a props y eVars.
seo-title: Copiar una variable de datos de contexto en una eVar
solution: Analytics
subtopic: Reglas de procesamiento
title: Copiar una variable de datos de contexto en una eVar
topic: Herramientas de administración
uuid: 1beaec4c-71e9-49ce-b154-78408cc532a3
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Copiar una variable de datos de contexto en una eVar

Las reglas de procesamiento se utilizan para mover valores desde variables de datos de contexto a props y eVars.

Las variables de datos de contexto se especifican en AppMeasurement con el formato siguiente:

```
 s.contextData['search_term']
```

La lista de [!UICONTROL variables de contexto] incluye todas las variables que se enviaron al grupo de informes durante los 30 días previos. Si conoce el nombre de la variable de datos de contexto pero no la ha enviado al grupo de informes actual, puede agregar un valor escribiendo el nombre de la variable y haciendo clic en **[!UICONTROL Agregar datos de contexto de nombre de variable]**:

![](assets/add-context-variable.png)

La siguiente definición de regla rellena una eVar en cada visita que contenga una variable de datos de contexto específica:

| Conjunto de reglas | Valor |
|---|---|
| Condición | Si los datos de contexto 'término_de_búsqueda' están definidos |
| Acción | Sobrescribir el valor de eVar3 por 'término_de_búsqueda' |

Por ejemplo:

![](assets/set-context-data.png)

Consulte [Variables de datos de contexto](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html) en la ayuda de implementación.
