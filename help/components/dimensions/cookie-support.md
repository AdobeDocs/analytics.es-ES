---
title: Compatibilidad con cookies
description: Determina si el explorador admite cookies.
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '187'
ht-degree: 100%

---

# Compatibilidad con cookies

La dimensión “Compatibilidad con cookies” informa sobre si el explorador admite cookies para una visita determinada. Es útil determinar la proporción de visitantes que utilizan exploradores que admiten cookies y los que las deshabilitan intencionalmente.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de la [`k`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement intenta establecer una cookie llamada `s_cc`, y luego detecta si existe. El resultado es el valor del parámetro de cadena de consulta `Y` (si el explorador admite y tiene las cookies habilitadas) o `N` (si el explorador tiene las cookies deshabilitadas). Si utiliza AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `k` en cada visita individual con el valor `Y` o `N`.

## Elementos de dimensión

Los elementos de dimensión incluyen `Enabled`, `Disabled` y `Unknown`.

* **`Enabled`**: El explorador admite cookies y las tiene habilitadas.
* **`Disabled`**: El explorador no admite cookies o el visitante las ha deshabilitado.
* **`Unknown`**: AppMeasurement no pudo determinar la compatibilidad con cookies. La cadena de consultas `k` no estaba presente en la solicitud de imagen.
