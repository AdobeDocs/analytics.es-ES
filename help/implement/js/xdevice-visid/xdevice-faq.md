---
title: Preguntas frecuentes sobre la identificación de visitantes entre dispositivos
description: Preguntas frecuentes sobre la identificación de visitantes entre dispositivos
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
role: Developer
TQID: https://experienceleague.adobe.com/h3kyR8lnSdl5rQKj9kmVXBt6rspjsALfUUaEh2-cAhM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 80%

---

# Preguntas frecuentes sobre la identificación de visitantes entre dispositivos

Preguntas frecuentes sobre la identificación de visitantes entre dispositivos.

+++¿Cuál es la diferencia entre la identificación de visitantes entre dispositivos y Cross-Device Analytics?
La identificación de visitantes entre dispositivos utiliza la variable `visitorID` para unir dispositivos, con varias limitaciones importantes. Una de las mayores limitaciones de este método de identificación es que las visitas no autenticadas están aisladas a menos que el dispositivo ya se haya reconocido. Estas visitas no autenticadas pueden aumentar las cantidades de visitantes únicos.

Cross-Device Analytics es el método más innovador de identificación de visitantes entre dispositivos de Adobe. Utiliza el servicio de Experience Cloud ID y la vinculación basada en el campo para unir de forma retroactiva las visitas desde distintos dispositivos. CDA necesita el uso de la función `setCustomerIDs` para determinar qué dispositivos utiliza el mismo visitante.
+++

+++¿Cómo gestiona la identificación de visitantes entre dispositivos los segmentos?
La identificación de visitantes entre dispositivos trata a los segmentos de manera similar a otras funciones. Examina cada visita individual para ver si coincide con los criterios del segmento e incluye esas visitas en los datos si coinciden. Los segmentos que utilizan contenedores basados en visitas y visitantes siguen mirando el ID de visitante. Asegúrese de que la implementación utiliza la variable `visitorID` siempre que sea posible para identificar de manera consistente a los visitantes únicos para la segmentación.
+++
