---
description: Puede rellenar una variable usando un parámetro de cadena de consulta.
seo-description: Puede rellenar una variable usando un parámetro de cadena de consulta.
seo-title: Rellene un ID de campaña desde un parámetro de cadena de consulta
solution: Analytics
subtopic: Reglas de procesamiento
title: Rellene un ID de campaña desde un parámetro de cadena de consulta
topic: Herramientas de administración
uuid: 2 bc 61 f 9 f-d 8 d 2-41 b 7-bd 39-4 a 9 df 30 ff 013
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rellene un ID de campaña desde un parámetro de cadena de consulta

Puede rellenar una variable usando un parámetro de cadena de consulta.

En la mayoría de los casos, utiliza un plug-in para rellenar variables desde la cadena de consulta. Si algún error tipográfico o un problema similar impide que se rellene el valor, puede rellenar la variable utilizando reglas de procesamiento.

Siempre debe comprobar si un valor está vacío o si contiene el valor esperado antes de sobrescribirlo.

| Conjunto de reglas | Valor |
|---|---|
| Condición | Campaña no está definida |
| Acción | Sobrescribir el valor de Campaña con el del parámetro de la cadena de consulta cpid |

Por ejemplo:

![](assets/set-campaign-conditionally.png)

