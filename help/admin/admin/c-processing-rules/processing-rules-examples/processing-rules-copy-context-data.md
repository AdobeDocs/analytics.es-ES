---
description: Las reglas de procesamiento se utilizan para mover valores desde variables de datos de contexto a props y eVars.
seo-description: Las reglas de procesamiento se utilizan para mover valores desde variables de datos de contexto a props y eVars.
seo-title: Copia de una variable de datos de contexto a una evar
solution: Analytics
subtopic: Reglas de procesamiento
title: Copia de una variable de datos de contexto a una evar
topic: Herramientas de administración
uuid: 1 beaec 4 c -71 e 9-49 ce-b 154-78408 cc 532 a 3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Copia de una variable de datos de contexto a una evar

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

Consulte [Variables de datos de contexto](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables) en la ayuda de implementación.
