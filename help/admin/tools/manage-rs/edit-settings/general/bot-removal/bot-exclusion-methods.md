---
title: Comparación de diferentes métodos de exclusión de bots
description: Permite comparar diferentes métodos para excluir bots.
exl-id: c54ba98a-b396-479e-bfe8-dc6211b26f61
role: Admin
feature: Bot Removal
TQID: https://experienceleague.adobe.com/zm3kClXgzo6sKMk20XKWGI66s2kjk4VZ2ohDj41JAes
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 46%

---

# Comparación de diferentes métodos de exclusión de bots

En la tabla siguiente se muestran diferentes métodos para excluir bots y cómo se comparan entre sí.

| Método | Reglas de bots | Excluir por dirección IP | Atributos del cliente | Segmentación | Puntuación de terceros + Segmentación | Suprimir la llamada al servidor para bots en tiempo de ejecución | Regla VISTA de DB personalizada |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Descripción del método de exclusión de datos** | Excluir en función del usuario-agente, la dirección IP o el intervalo de direcciones IP | Dirección IP | Un indicador en atributos del cliente que identifica el ECID como un bot | Criterios en un segmento de Analytics que identifica bots conocidos en función del comportamiento de bots | Un tercero, como [Perímetro X](https://www.perimeterx.com) o [Administrador de bots de Akamai](https://www.akamai.com/es/es/products/security/bot-manager.jsp), asigna a cada vista de página una puntuación sobre la probabilidad de que sea un bot. La puntuación se envía a Analytics y los segmentos se pueden utilizar para filtrar los datos en función de la puntuación. | La lógica del lado del cliente impide que la llamada al servidor de Analytics se ejecute para bots. | Una regla VISTA moverá el tráfico de bots que cumplan determinados criterios a un grupo de informes independiente. |
| **Los nombres de bots están disponibles para la creación de informes?** | Sí | No | No | No | No | No | Sí |
| **¿Es posible ver qué páginas están visitando los bots?** | Sí | No | No | No | Sí | No | Sí |
| **Incurre en el costo de llamadas al servidor para bots?** | Sí | Sí | Sí | Sí | Sí | No | Sí |
| **¿Están disponibles los datos de bots en las fuentes de datos?** | No | No | Sí | No | Sí | No | Sí |
| **¿Es posible informar sobre el tráfico de bots como si fueran llamadas reales al servidor?** | No | No | Sí | Sí | Sí | No | No |
| **¿Se pueden quitar datos de un conjunto de datos de forma retroactiva?** | No | No | Sí, una vez implementados los ID declarados | Sí | Sí, una vez implementadas las puntuaciones | No | No |
| **¿Está sujeto a límites exclusivos en los criterios?** | No | No | No | Sí | No | No | No |
| **¿Está sujeto a un costo adicional?** | No | No | Es posible, en función del SKU de Analytics | No | Sí | No | Sí, coste para implementar y mantener una regla VISTA |
