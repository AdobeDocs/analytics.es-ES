---
title: Atribución algorítmica
description: Detalles sobre el modelo de atribución algorítmica.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 84%

---

# Atribución algorítmica

El [modelo de atribución](models.md) algorítmica en Analysis Workspace difiere de otros modelos en que utiliza técnicas estadísticas para asignar crédito entre los elementos de dimensión del informe o la tabla de forma libre. Al igual que todos los demás modelos de atribución en Analysis Workspace, puede utilizarse en cualquier dimensión o métrica y admite segmentación y desgloses ilimitados y distribuye el 100% de las conversiones a las dimensiones de la tabla (también conocida como atribución “fraccional”).


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Atribución algorítmica](https://video.tv.adobe.com/v/40049?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


El algoritmo utilizado para la atribución se basa en el dividendo de Harsanyi de la teoría de juegos cooperativa. El dividendo de Harsanyi es una generalización de la solución del valor de Shapley (llamada así por Lloyd Shapley, economista ganador del Premio Nobel) para distribuir crédito entre los jugadores en un juego con contribuciones desiguales al resultado.

En un nivel elevado, el cálculo de atribución del crédito de conversión para cada punto de contacto considera cada uno de los puntos de contacto de marketing dentro de una ventana retrospectiva como una coalición de actores a los que debe distribuirse equitativamente un excedente. La distribución del superávit de cada coalición se determina de acuerdo con el superávit creado previamente por cada subcoalición (o los elementos de dimensión que participaban antes) de manera recursiva. Para más detalles, vea los artículos originales de John Harsanyi y Lloyd Shapley:

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). Un modelo de negociación simplificado para un juego cooperativo de n personas. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>El resultado de la atribución algorítmica solo difiere de otros modelos cuando existen varios puntos de contacto dentro de la ventana retrospectiva establecida. Las conversiones con un solo punto de contacto reciben un 100% de crédito, independientemente del modelo de atribución.
