---
title: Comparación de diferentes métodos de exclusión de bots
description: Permite comparar diferentes métodos para excluir bots.
translation-type: tm+mt
source-git-commit: 76ee4a8db49765590e7cca864d6d4b152d7ba112
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 20%

---


# Comparación de diferentes métodos de exclusión de bots

La siguiente tabla muestra los diferentes métodos para excluir bots y cómo se apilan entre sí.

| Método | Reglas de bots | Excluir por dirección IP | Atributos del cliente | Segmentación | Puntuación de terceros + Segmentación | Suprimir la &#x200B; de &#x200B; de llamadas al servidor para bots en tiempo de ejecución | Regla de DB VISTA personalizada |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Descripción del método de exclusión de datos** | &#x200B; Excluir según el agente de usuario, la dirección IP o el intervalo de direcciones IP | Dirección IP | &#x200B; Un indicador en los atributos del cliente que identifica ECID como un bot | Criterios de &#x200B; en un segmento de Analytics que identifica bots conocidos según el comportamiento de bots | &#x200B; Un tercero, como [Perimeter X](https://www.perimeterx.com) o [Akamai Bot Manager](https://www.akamai.com/us/en/products/security/bot-manager.jsp) , asigna a cada vista de página una puntuación sobre la probabilidad de que sea un bot. La puntuación se envía a Analytics y los segmentos se pueden usar para filtrar los datos en función de la puntuación. | &#x200B; lógica de cliente impide que la llamada al servidor de Analytics se ejecute para bots. | &#x200B; Una regla de VISTA moverá el tráfico de bots que cumplen ciertos criterios a un grupo de informes independiente. |
| **¿&#x200B; nombres de bots están disponibles para el sistema de informes?** | Sí | No | No | No | No | No | Sí |
| **&#x200B; ¿Puede ver qué páginas están siendo visitadas por los bots?** | Sí | No | No | No | Sí | No | Sí |
| &#x200B; ¿**Incurre en el costo de llamadas al servidor para bots?** | Sí | Sí | Sí | Sí | Sí | No | Sí |
| **¿Los datos de bots están disponibles en las fuentes de datos?** | No | No | Sí | Sí | Sí | No | Sí |
| **¿Es posible &#x200B; informes sobre el tráfico de bots como si fueran llamadas reales al servidor?** | No | No | Sí | Sí | Sí | Sí | No |
| **¿Se pueden eliminar datos retroactivamente de un conjunto de datos?** | No | No | &#x200B; Sí, una vez implementados los ID declarados | Sí | Sí, una vez implementadas las puntuaciones | No | No |
| **¿Está sujeto a límites exclusivos en los criterios?** | No | No | No | Sí | No | No | No |
| **¿Está &#x200B; sujeto a un coste adicional?** | No | No | &#x200B; posiblemente, según el SKU de Analytics | No | Sí | No | &#x200B; Sí: costo para implementar y mantener una regla de VISTA |
