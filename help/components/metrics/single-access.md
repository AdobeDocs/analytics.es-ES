---
title: Acceso único
description: Número de veces que un elemento de dimensión no ha cambiado en una visita.
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '339'
ht-degree: 100%

---

# Acceso único

La métrica “Acceso único” muestra el número de visitas en las que el elemento de la dimensión solo contenía un valor único para toda la visita. Esta métrica es útil en el contexto de cualquier dimensión en la que desee ver qué elementos de dimensión se estancan durante una visita.

## Cálculo de esta métrica

Esta métrica cuenta las visitas en las que el elemento de dimensión contenía un valor único. Puede establecer el elemento de dimensión varias veces o hacer que persista y siga contando como un solo acceso. Tan pronto como un elemento de dimensión cambia a un segundo valor único, la visita ya no se califica como un acceso único.

## Diferencia entre “Acceso único” y “Visita de página única”

En el contexto de la dimensión [Página](../dimensions/page.md), “Acceso único” y “Visitas de página única” son exactamente iguales. Sus diferencias surgen cuando se usan otras dimensiones.

* **Acceso único**: Muestra el número de visitas en las que el elemento de dimensión dado no cambió para toda la visita. Es contextual para la dimensión que se utiliza en el proyecto.
* **Visita de página única**: Muestra el número de visitas en las que la dimensión “Página” no cambió durante toda la visita. Aunque utilice otra dimensión en el informe, aún cuenta las visitas que contienen un solo elemento de dimensión “Página” único.

En el siguiente ejemplo, se muestran dos visitas individuales. La dimensión del informe es la [sección del sitio](../dimensions/site-section.md).

* Un visitante visita dos páginas, pero ambas están en la misma sección del sitio. Dado que la sección del sitio permaneció igual durante la visita, se considera un acceso único. No se cuenta como una visita de página única porque la visita contiene más de un elemento de dimensión de página único.
* Un visitante visita dos páginas en diferentes secciones del sitio, pero ambas páginas tienen el mismo nombre. La visita no cuenta como un acceso único porque había dos valores de sección del sitio únicos. Se cuenta como una visita a una página única porque había un solo elemento de dimensión de página único.
