---
title: Comparación de diferentes métodos de exclusión de bots
description: Permite comparar diferentes métodos para excluir bots.
exl-id: c54ba98a-b396-479e-bfe8-dc6211b26f61
role: Admin
feature: Bot Removal
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 94%

---

# Comparación de diferentes métodos de exclusión de bots

En la tabla siguiente se muestran diferentes métodos para excluir bots y cómo se comparan entre sí.

| Método | Reglas de bots | Excluir por dirección IP | Atributos del cliente | Segmentación | Puntuación de terceros + Segmentación | Suprimir la llamada al servidor para bots en tiempo de ejecución | Regla VISTA de DB personalizada |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Descripción del método de exclusión de datos** | Excluir en función del usuario-agente, la dirección IP o el intervalo de direcciones IP | Dirección IP | Un indicador en atributos del cliente que identifica el ECID como un bot | Criterios en un segmento de Analytics que identifica bots conocidos en función del comportamiento de bots | Un tercero, como [Perímetro X](https://www.perimeterx.com) o [Administrador de bots de Akamai](https://www.akamai.com/es/es/products/security/bot-manager.jsp), asigna a cada vista de página una puntuación sobre la probabilidad de que sea un bot. La puntuación se envía a Analytics y los segmentos se pueden utilizar para filtrar los datos en función de la puntuación. | La lógica del lado del cliente impide que la llamada al servidor de Analytics se ejecute para bots. | Una regla VISTA moverá el tráfico de bots que cumplan determinados criterios a un grupo de informes independiente. |
| **¿Hay nombres de bots disponibles para la creación de informes?** | Sí | No | No | No | No | No | Sí |
| **¿Es posible ver qué páginas están visitando los bots?** | Sí | No | No | No | Sí | No | Sí |
| **¿Se incurre en costes por llamadas al servidor para bots?** | Sí | Sí | Sí | Sí | Sí | No | Sí |
| **¿Están disponibles los datos de bots en las fuentes de datos?** | No | No | Sí | Sí | Sí | No | Sí |
| **¿Es posible informar sobre el tráfico de bots como si fueran llamadas reales al servidor?** | No | No | Sí | Sí | Sí | No | No |
| **¿Se pueden quitar datos de un conjunto de datos de forma retroactiva?** | No | No | Sí, una vez implementados los ID declarados | Sí | Sí, una vez implementadas las puntuaciones | No | No |
| **¿Está sujeto a límites exclusivos en los criterios?** | No | No | No | Sí | No | No | No |
| **¿Está sujeto a un coste adicional?** | No | No | Es posible, en función del SKU de Analytics | No | Sí | No | Sí, coste para implementar y mantener una regla VISTA |
