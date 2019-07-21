---
description: Descripciones de los campos e información sobre variables al utilizar Dynamic Tag Management para implementar Adobe Analytics.
keywords: Administración dinámica de etiquetas; globales variables; server variable; evar; props; prefijo de variable dinámica; variable dinámica
seo-description: Descripciones de los campos e información sobre variables al utilizar Dynamic Tag Management para implementar Adobe Analytics.
seo-title: Variables globales
solution: Marketing Cloud, Analytics, Administración dinámica de etiquetas
title: Variables globales
uuid: d 759320 a -96 ee -4073-b 5 fd -5257 b 7033003
translation-type: tm+mt
source-git-commit: 3489f00bd7dddefda0420fc361056416f6f10d3f

---


# Variables globales

Descripciones de los campos e información sobre variables al utilizar Dynamic Tag Management para implementar Adobe Analytics.

Estas variables se activan en todas las señalizaciones de reglas de carga de página. Puede lograr el mismo efecto definiendo una [regla de carga de página](../../../implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md#task_69B41CB230EE4530A755D91233F73706) para que se active en todas las páginas. These variables might not fire in [Direct-Call](../../../implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md#task_85EB8F01775A402BA53B8298F0AADA09) and [Event-Based](../../../implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md#task_A122DE72110F4579A91F9D96D92D39FC) rules.

## Variables globales: descripciones de campos {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png)**[!UICONTROL Editar herramienta]** &gt; **[!UICONTROL Variables globales]**

| Elemento | Descripción |
|--- |--- |
| Servidor | La variable predefinida rellena la dimensión Servidores en Adobe Analytics. See [Page Variables](/help/implement/js-implementation/c-variables/page-variables.md) |
| eVars | [Las variables evar](/help/implement/js-implementation/c-variables/page-variables.md) se utilizan para generar informes de conversión personalizados. |
| Props | [Las variables Prop](/help/implement/js-implementation/c-variables/page-variables.md) se utilizan para generar informes de tráfico personalizados. |
| Prefijo de variable dinámica | Prefijo especial que se encuentra al principio del valor. El prefijo predeterminado es "D=". Consulte [Variables dinámicas](/help/implement/js-implementation/c-variables/dynvars-overview.md) |
