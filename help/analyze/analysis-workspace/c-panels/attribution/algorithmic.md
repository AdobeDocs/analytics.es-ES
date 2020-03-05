---
title: Atribución algorítmica
description: Detalles sobre el modelo de atribución algorítmica en Adobe Analytics.
translation-type: tm+mt
source-git-commit: 143cbed5f2159b7faab387e10896af836d0780f7

---


# Atribución algorítmica

El modelo [de](attribution.md) atribución algorítmica en Analysis Workspace difiere de otros modelos en que utiliza técnicas estadísticas para asignar crédito entre los valores de dimensión del informe o la tabla improvisada. Al igual que todos los demás modelos de atribución de Analysis Workspace, puede utilizarse en cualquier dimensión o métrica y admite segmentación y desgloses ilimitados y distribuye el 100 % de las conversiones a las dimensiones de la tabla (también conocida como atribución &quot;fraccional&quot;).

El algoritmo utilizado para la atribución se basa en el dividendo de Harsanyi de la teoría de juegos cooperativa. El dividendo de Harsanyi es una generalización de la solución del valor de Shapley (llamada así por Lloyd Shapley, economista ganador del Premio Nobel) para distribuir crédito entre los jugadores en un juego con contribuciones desiguales al resultado.

En un nivel elevado, el cálculo de atribución del crédito de conversión para cada punto de contacto considera cada uno de los puntos de contacto de marketing dentro de una ventana retrospectiva como una coalición de actores a los que debe distribuirse equitativamente un excedente. La distribución del superávit de cada coalición se determina de acuerdo con el superávit creado previamente por cada subcoalición (o los valores de dimensión que antes participaban) de manera recursiva. Para obtener más información, consulte los artículos originales de John Harsanyi y Lloyd Shapley:

* Shapley, Lloyd S. &quot;Un valor para los juegos en persona.&quot; *Contribuciones a la Teoría de los Juegos 2.28*, 1953, pp. 307-317.
* Harsanyi, John C. &quot;Un modelo de negociación simplificado para el juego cooperativo en persona&quot;. *International Economic Review 4.2*, 1963, págs. 194-220.

> [!NOTE] El resultado de la atribución algorítmica solo difiere de otros modelos cuando existen varios puntos de contacto dentro de la ventana retroactiva dada. Las conversiones con un solo punto de contacto reciben un 100% de crédito, independientemente del modelo de atribución.
