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
source-git-commit: 4e3e164f5c28290ac280343d95cf5cb1186e09cd

---


# Copiar una variable de datos de contexto en una eVar

Las reglas de procesamiento se utilizan para mover valores de variables de datos de contexto a props y eVars. Sin reglas de procesamiento, las variables de datos de contexto no tienen sentido y no rellenan ningún informe en Analytics.

La lista de [!UICONTROL variables de contexto] incluye todas las variables que se enviaron al grupo de informes durante los 30 días previos. Si conoce el nombre de la variable de datos de contexto pero no la ha enviado al grupo de informes actual, puede agregar un valor escribiendo el nombre de la variable y haciendo clic en **[!UICONTROL Agregar datos de contexto de nombre de variable]**:

![Agregue](assets/add-context-variable.png)

El ejemplo siguiente toma la variable de datos de `search_term` contexto y coloca su valor en `eVar3`:

![Establezca](assets/set-context-data.png)

El ejemplo anterior funciona bien cuando solo hay unas pocas eVars que rellenar. Si su organización tiene cientos de variables de datos de contexto que cada una necesita su propia eVar, puede utilizar afirmaciones condicionales. Docenas de afirmaciones condicionales pueden caber dentro de una sola regla de procesamiento, lo que permite a la organización completar todas las eVars en un grupo de informes sin tener que entrar en el límite de reglas de procesamiento de 150 reglas.

El ejemplo siguiente se rellena `prop7` con la variable de datos de contexto `testhierarchy`, pero solo si `testhierarchy` está configurada:

![Condicional](assets/add-conditional.png)

Para obtener más información sobre la implementación de variables de datos de contexto, consulte Variables [de datos de](/help/implement/js-implementation/c-variables/context-data-variables.md) contexto en la guía de usuario Implementación.
