---
description: Puede hacer coincidir los valores con los errores de escritura más comunes y actualizarlos de modo que aparezcan correctamente en los informes.
subtopic: Processing rules
title: Limpiar los valores de un informe
feature: Herramientas de administración
uuid: fcd72afc-3a3c-47a9-a5e4-53389dba7d83
exl-id: 109005a3-2ea4-4b61-a733-d1019218ec56
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 100%

---

# Limpiar los valores de un informe

Puede hacer coincidir los valores con los errores de escritura más comunes y actualizarlos de modo que aparezcan correctamente en los informes.

Si se desea garantizar que no coincidirán con otros valores de forma involuntaria, debe utilizarse la opción de coincidencia disponible más restrictiva. Puede ejecutar un informe en la variable (Prop1 en el ejemplo anterior) y buscar los términos que desea reemplazar para asegurarse de que no coinciden con valores no deseados. Al comparar cadenas, no se distingue entre mayúsculas y minúsculas.

| Conjunto de reglas | Valor |
|---|---|
| Condición | Si prop1 Comienza con Compra |
| Acción | Sobrescribir el valor de prop1 con el valor personalizado Compra |

Por ejemplo:

![](assets/clean-up-values-in-report.png)
