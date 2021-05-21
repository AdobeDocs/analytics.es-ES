---
description: El análisis de contribución es un proceso de aprendizaje automatizado intensivo diseñado para descubrir qué contribuye a una anomalía observada en Adobe Analytics. El propósito es ayudar al usuario a descubrir las áreas de interés u oportunidades para un análisis adicional de forma más rápida de lo que sería posible de otro modo.
title: Técnicas estadísticas utilizadas en los análisis de contribución
uuid: f77eb4e4-4fd6-4397-b8a8-a063f199b676
feature: Herramientas de IA
role: Business Practitioner, Administrator
exl-id: 1e19b154-c6d2-48fe-9baf-db4e47789321
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '332'
ht-degree: 100%

---

# Técnicas estadísticas utilizadas en los análisis de contribución

El análisis de contribución es un proceso de aprendizaje automatizado intensivo diseñado para descubrir qué contribuye a una anomalía observada en Adobe Analytics. El propósito es ayudar al usuario a descubrir las áreas de interés u oportunidades para un análisis adicional de forma más rápida de lo que sería posible de otro modo.

El análisis de contribución lo consigue mediante la realización de un algoritmo en dos partes en cada elemento de dimensión disponible para el informe de análisis de contribución del usuario. El algoritmo opera en este orden:

1. Para cada dimensión, calcula la estadística de prueba V de Cramer. En el siguiente ejemplo, observe una tabla de contingencia con vistas de página por países en dos periodos de tiempo:

   ![](assets/contingency_table.png)

   En la tabla 1, se puede utilizar la V de Cramer para medir la asociación entre las vistas de página por países para el periodo 1 (por ejemplo, histórico) y el periodo 2 (por ejemplo, el día en el que se produjo la anomalía). Un valor de V de Cramer bajo implica un bajo nivel de asociación. La V de Cramer va desde 0 (sin asociación) a 1 (asociación completa). La estadística de V de Cramer puede calcularse:

   ![](assets/cramers-v.png)

1. Para cada elemento de dimensión, se utiliza la residual de persona (PR) para medir la asociación entre la métrica anómala y cada elemento de dimensión. PR sigue un estándar de distribución normal, el cual permite que el algoritmo compare las PR de dos variables aleatorias incluso si las desviaciones no son comparables. En la práctica, el error no es conocido y se calcula utilizando una corrección de muestra infinita.

   En el ejemplo anterior de la tabla 1, la PR, con corrección de muestra finita por país “i” y un periodo de tiempo 2 está determinado por

   ![](assets/persons-residual.png)

   Aquí,

   ![](assets/pr-example.png)

   (Se puede obtener una fórmula similar para el periodo de tiempo 1).

   Para los resultados finales, la puntuación de cada elemento de dimensión se pondera mediante la medición de V de Cramer y se modifica la escala a un número entre 0 y 1 para proporcionar su puntuación de contribución.
