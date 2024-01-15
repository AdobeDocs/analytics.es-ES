---
description: Puede rellenar una variable usando un parámetro de cadena de consulta.
subtopic: Processing rules
title: Rellenar un ID de campaña desde un parámetro de cadena de consulta
feature: Admin Tools
role: Admin
exl-id: 526d2727-b7f6-4b41-be86-e5f5bc5e6c2b
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
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
