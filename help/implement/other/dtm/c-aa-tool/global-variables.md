---
description: Descripciones de los campos e información sobre variables al utilizar Dynamic Tag Management para implementar Adobe Analytics.
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
solution: Experience Cloud,Analytics
title: Variables globales
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: tm+mt
source-git-commit: a4542164031fc9f181dfdc471a1d54b5056b1223
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 100%

---


# Variables globales

Descripciones de los campos e información sobre variables al utilizar Dynamic Tag Management para implementar Adobe Analytics.

Estas variables se activan en todas las señalizaciones de reglas de carga de página. Puede lograr el mismo efecto definiendo una [regla de carga de página](/help/implement/other/dtm/c-rules/t-rules-page-conditions.md) para que se active en todas las páginas. Es posible que estas variables no se activen en reglas de [llamada directa](/help/implement/other/dtm/c-rules/t-rules-direct-conditions.md) y [basadas en eventos](/help/implement/other/dtm/c-rules/t-rules-event-conditions.md).

## Variables globales: descripciones de campos {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** > ![](assets/settings_gear.png)**[!UICONTROL  Editar herramienta ]** > **[!UICONTROL  Variables globales ]**

| Elemento | Descripción |
|--- |--- |
| Servidor | La variable predefinida rellena la dimensión de servidores en Adobe Analytics. Consulte [Servidor](../../../vars/page-vars/server.md) |
| eVars | Las [variables eVar](../../../vars/page-vars/evar.md) se utilizan para generar informes de conversión personalizados. |
| Propriétés | Las [variables de propiedad (prop)](../../../vars/page-vars/prop.md) se utilizan para generar informes de tráfico personalizados. |
| Prefijo de variable dinámica | Prefijo especial que se encuentra al principio del valor. El prefijo predeterminado es &quot;D=&quot;. Consulte [Variables dinámicas](../../../vars/page-vars/dynamic-variables.md). |
