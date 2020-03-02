---
description: 'null'
title: Atribución algorítmica
uuid: bb345642-4f45-4fb8-82d0-803248dd52ea
translation-type: tm+mt
source-git-commit: b5418e6321b09ddbab36e0052f75f36067086e3e

---


# Atribución algorítmica

![Algoritmo](assets/algorithmic.png)

El modelo [de](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html#attribution-models) atribución algorítmica en Analysis Workspace difiere de otros modelos dentro de IQ de atribución en que utiliza técnicas estadísticas para asignar crédito entre los valores de dimensión del informe o la tabla improvisada. Al igual que todos los demás modelos de atribución de Analysis Workspace, puede utilizarse en cualquier dimensión o métrica y admite segmentación y desgloses ilimitados y distribuye el 100 % de las conversiones a las dimensiones de la tabla (también conocida como atribución &quot;fraccional&quot;).

El algoritmo utilizado para la atribución se basa en el dividendo de Harsanyi de la teoría de juegos cooperativa. El dividendo de Harsanyi es una generalización de la solución del valor de Shapley (llamada así por Lloyd Shapley, economista ganador del Premio Nobel) para distribuir crédito entre los jugadores en un juego con contribuciones desiguales al resultado.

En un nivel elevado, el cálculo de atribución del crédito de conversión para cada punto de contacto considera cada uno de los puntos de contacto de marketing dentro de una ventana retrospectiva como una coalición de actores a los que debe distribuirse equitativamente un excedente. La distribución del superávit de cada coalición se determina de acuerdo con el superávit creado previamente por cada subcoalición (o los valores de dimensión que antes participaban) de manera recursiva. Para obtener más información, por favor consulte los artículos originales de John Harsanyi y Lloyd Shapley:

* Shapley, Lloyd S. &quot;Un valor para los juegos en persona.&quot; Contribuciones a la Teoría de los Juegos 2.28 (1953): 307-317.

* Harsanyi, John C. &quot;Un modelo de negociación simplificado para el juego cooperativo en persona&quot;. Examen Económico Internacional 4.2 (1963): 194-220.

*Nota: El resultado de la atribución algorítmica solo difiere de otros modelos cuando existen varios puntos de contacto dentro de la ventana retroactiva dada. Por ejemplo, con un solo punto de contacto, el 100 % del crédito se asignará a ese valor independientemente del modelo de atribución seleccionado.*