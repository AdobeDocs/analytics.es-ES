---
title: Preguntas frecuentes sobre la identificación de visitantes entre dispositivos
description: Preguntas frecuentes sobre la identificación de visitantes entre dispositivos
exl-id: da972fee-fe6e-45b2-af01-50674989c375
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '190'
ht-degree: 100%

---

# Preguntas frecuentes sobre la identificación de visitantes entre dispositivos

Preguntas frecuentes sobre la identificación de visitantes entre dispositivos.

**¿Cuál es la diferencia entre la identificación de visitantes entre dispositivos y Cross-Device Analytics?**

La identificación de visitantes entre dispositivos utiliza la variable `visitorID` para unir dispositivos, con varias limitaciones importantes. Una de las mayores limitaciones de este método de identificación es que las visitas no autenticadas están aisladas a menos que el dispositivo ya se haya reconocido. Estas visitas no autenticadas pueden aumentar las cantidades de visitantes únicos.

Cross-Device Analytics es el método más innovador de identificación de visitantes entre dispositivos de Adobe. Utiliza el servicio de Experience Cloud ID y el gráfico de dispositivos para unir en forma retroactiva las visitas desde distintos dispositivos. CDA necesita el uso de la función `setCustomerIDs` para determinar qué dispositivos utiliza el mismo visitante.

**¿Cómo gestiona la identificación de visitantes entre dispositivos los segmentos?**

La identificación de visitantes entre dispositivos trata a los segmentos de manera similar a otras funciones. Examina cada visita individual para ver si coincide con los criterios del segmento e incluye esas visitas en los datos si coinciden. Los segmentos que utilizan contenedores basados en visitas y visitantes siguen mirando el ID de visitante. Asegúrese de que la implementación utiliza la variable `visitorID` siempre que sea posible para identificar de manera consistente a los visitantes únicos para la segmentación.
