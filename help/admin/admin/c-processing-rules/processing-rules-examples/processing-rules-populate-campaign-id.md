---
description: Puede rellenar una variable usando un parámetro de cadena de consulta.
subtopic: Processing rules
title: Rellenar un ID de campaña desde un parámetro de cadena de consulta
topic: Admin tools
uuid: 2bc61f9f-d8d2-41b7-bd39-4a9df30ff013
translation-type: ht
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440
workflow-type: ht
source-wordcount: '112'
ht-degree: 100%

---


# Rellenar un ID de campaña desde un parámetro de cadena de consulta

Puede rellenar una variable usando un parámetro de cadena de consulta.

En la mayoría de los casos, utiliza un complemento para rellenar variables desde la cadena de consulta. Si algún error tipográfico o un problema similar impide que se rellene el valor, puede rellenar la variable utilizando reglas de procesamiento.

Siempre debe comprobar si un valor está vacío o si contiene el valor esperado antes de sobrescribirlo.

| Conjunto de reglas | Valor |
|---|---|
| Condición | Campaña no está definida |
| Acción | Sobrescribir el valor de Campaña con el del parámetro de la cadena de consulta cpid |

Por ejemplo:

![](assets/set-campaign-conditionally.png)

