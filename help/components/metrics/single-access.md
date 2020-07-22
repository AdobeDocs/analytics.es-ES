---
title: Acceso único
description: Número de veces que un elemento de dimensión no ha cambiado en una visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---


# Acceso único

La métrica &#39;Acceso único&#39; muestra el número de visitas donde el elemento de dimensión contenía solamente un valor único para toda la visita. Esta métrica es útil en el contexto de cualquier dimensión en la que desee ver qué elementos de dimensión se estancan durante una visita.

## Cómo se calcula esta métrica

Esta métrica cuenta las visitas en las que el elemento de dimensión contenía un único valor. Puede configurar el elemento de dimensión varias veces o hacer que persista y siga contando como un solo acceso. Tan pronto como un elemento de dimensión cambia a un segundo valor único, la visita ya no se califica como un acceso único.

## Diferencia entre &#39;Acceso único&#39; y &#39;Visita a una sola página&#39;

En el contexto de la dimensión [Página](../dimensions/page.md) , &#39;Acceso único&#39; y &#39;Visitas a una sola página&#39; son exactamente iguales. Sus diferencias surgen cuando se usan otras dimensiones.

* **Acceso**&#x200B;único: Muestra el número de visitas en las que el elemento de dimensión dado no cambió durante toda la visita. Es contextual para la dimensión que se utiliza en el proyecto.
* **Visita** a una sola página: Muestra el número de visitas en las que la dimensión &#39;Página&#39; no cambió durante toda la visita. Aunque utilice otra dimensión en el informe, aún cuenta las visitas que contienen un único elemento de dimensión &#39;Página&#39; único.

Por ejemplo: considere el siguiente ejemplo de dos visitas individuales. La dimensión del informe es la sección [](../dimensions/site-section.md)Sitio.

* Un visitante visita dos páginas, pero ambas están en la misma sección del sitio. Dado que la sección del sitio permaneció igual durante la visita, se considera un acceso único. No se cuenta como una visita a una sola página porque la visita contiene más de un elemento de dimensión de página único.
* Un visitante visita dos páginas en diferentes secciones del sitio, pero ambas páginas tienen el mismo nombre. La visita no cuenta como un acceso único porque había dos valores de sección del sitio únicos. Se cuenta como una visita a una sola página porque había un solo elemento de dimensión de página único.
