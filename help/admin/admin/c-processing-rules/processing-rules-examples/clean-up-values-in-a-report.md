---
description: Puede hacer coincidir los valores con los errores de escritura más comunes y actualizarlos de modo que aparezcan correctamente en los informes.
subtopic: Processing rules
title: Limpiar los valores de un informe
topic: Admin tools
uuid: fcd72afc-3a3c-47a9-a5e4-53389dba7d83
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: ht
source-wordcount: '113'
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

