---
title: Acceso único
description: Número de veces que un valor de dimensión no ha cambiado en una visita.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---


# Acceso único

La métrica &quot;Acceso único&quot; muestra el número de visitas en las que el valor de la dimensión solo contenía un valor único para toda la visita. Esta métrica es útil en el contexto de cualquier dimensión en la que desee ver qué valores de dimensión se estancan durante una visita.

## Cómo se calcula esta métrica

Esta métrica cuenta las visitas en las que el valor de dimensión contenía un único valor. Puede establecer el valor de dimensión varias veces o hacer que persista y siga contando como un solo acceso. Tan pronto como un valor de dimensión cambia a un segundo valor único, la visita ya no se califica como un acceso único.

## Diferencia entre &#39;Acceso único&#39; y &#39;Visita a una sola página&#39;

En el contexto de la dimensión [Página](../dimensions/page.md) , &#39;Acceso único&#39; y &#39;Visitas a una sola página&#39; son exactamente iguales. Sus diferencias surgen cuando se usan otras dimensiones.

* **Acceso**&#x200B;único: Muestra el número de visitas en las que el valor de dimensión dado no cambió para toda la visita. Es contextual para la dimensión que se utiliza en el proyecto.
* **Visita** a una sola página: Muestra el número de visitas en las que la dimensión &#39;Página&#39; no cambió durante toda la visita. Aunque utilice otra dimensión en el informe, aún cuenta las visitas que contienen un único valor de dimensión &#39;Página&#39; único.

Por ejemplo: considere el siguiente ejemplo de dos visitas individuales. La dimensión del informe es la sección [](../dimensions/site-section.md)Sitio.

* Un visitante visita dos páginas, pero ambas están en la misma sección del sitio. Dado que la sección del sitio permaneció igual durante la visita, se considera un acceso único. No se cuenta como una visita a una sola página porque la visita contiene más de un valor de dimensión de página único.
* Un visitante visita dos páginas en diferentes secciones del sitio, pero ambas páginas tienen el mismo nombre. La visita no cuenta como un acceso único porque había dos valores de sección del sitio únicos. Se cuenta como una visita a una sola página porque había un solo valor de dimensión de página único.
