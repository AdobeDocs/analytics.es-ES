---
description: 'null'
title: Generador de perspectivas rápidas
translation-type: tm+mt
source-git-commit: 77b126b2add78113c266265f413240f27f89bced

---


# Generador de perspectivas rápidas

>[!IMPORTANT]
>
>Quick Insights está actualmente en pruebas beta y todavía no está disponible para todos los clientes de Adobe Analytics.

Quick Insights proporciona consejos a los no analistas y a los nuevos usuarios de Análisis Workspace para aprender a responder preguntas comerciales de forma rápida y sencilla. También es una buena herramienta para usuarios avanzados que desean responder a una simple pregunta rápidamente sin tener que crear una tabla ellos mismos.

Cuando inicio por primera vez el uso de este espacio de trabajo de Análisis, puede preguntarse qué visualizaciones serían más útiles, qué dimensiones y métricas podrían facilitar las perspectivas, dónde arrastrar y soltar elementos, dónde crear un segmento, etc.

Para ayudarle, en función del uso que haga su propia compañía de los componentes de datos en el espacio de trabajo de Análisis, Quick Insights aprovecha un algoritmo que le presentará las dimensiones, métricas, segmentos e intervalos de fechas más populares que utilice su compañía.

Las perspectivas rápidas le ayudan

* Cree correctamente una tabla de datos y la visualización adjunta en Análisis Workspace.
* Obtenga información sobre la terminología y el vocabulario de los componentes básicos y las piezas de Análisis Workspace.
* Realice desgloses simples de dimensiones, agregue varias métricas o compare segmentos fácilmente dentro de una tabla improvisada.
* Cambie o pruebe varios tipos de visualización para encontrar la herramienta de búsqueda para su análisis de forma rápida e intuitiva.

## Terminología clave básica

A continuación se incluyen algunos de los términos básicos con los que debe estar familiarizado. Cada tabla de datos consta de dos o más bloques de creación que se utilizan para contar el historial de datos.

| Bloque de creación | Definición |
|---|---|
| Dimensión | Las dimensiones son descripciones o características de los datos de métricas que se pueden ver, desglosar y comparar en un proyecto. Son valores no numéricos y fechas que se desglosan en elementos de dimensión. Por ejemplo, &quot;browser&quot; o &quot;page&quot; son dimensiones. |
| Elemento de dimensión | Los elementos de dimensión son valores individuales para una dimensión. Por ejemplo, los elementos de dimensión para la dimensión del navegador serían &quot;Chrome&quot;, &quot;Firefox&quot;, &quot;Edge&quot;, etc. |
| Métrica | Las métricas son información cuantitativa sobre la actividad de visitantes, como vistas, pulsaciones, recargas, tiempo promedio empleado, unidades, pedidos, ingresos, etc. |
| Visualización | Workspace oferta [varias visualizaciones](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) para crear representaciones visuales de los datos. |
| Segmento | Los segmentos permiten identificar subconjuntos de visitantes en función de las características o las interacciones con el sitio web. Por ejemplo, puede generar segmentos de Visitante basados en atributos: tipo de explorador, dispositivo, número de visitas, país, sexo o según las interacciones: campañas, búsqueda de palabras clave, motor de búsqueda o en función de salidas y entradas: visitantes de Facebook, una página de aterrizaje definida, un dominio de referencia o basados en variables personalizadas: campo de formulario, categorías definidas, ID de cliente. |

## Introducción a Quick Insights

1. Inicie sesión en Adobe Analytics con las credenciales que se le han proporcionado.
1. Vaya a [!UICONTROL Workspace] y haga clic en **[!UICONTROL Create New Project]** y, a continuación, en **[!UICONTROL Quick Insights Builder]**.

   ![](assets/qibuilder.png)

1. Cuando termine el inicio por primera vez, consulte el breve tutorial que le enseña algunos de los conceptos básicos de Quick Insight Builder. O bien, haga clic en **[!UICONTROL Skip Tutorial]**.
1. Seleccione los componentes (también conocidos como componentes): dimensiones (naranja), métricas (verde), segmentos (azul) o intervalos de fechas (púrpura) Debe seleccionar al menos una dimensión y una métrica para crear una tabla automáticamente.

   ![](assets/qibuilder2.png)

   Existen tres formas de seleccionar los componentes:
   * Arrástrelos y suéltelos desde el carril izquierdo
   * Si sabe lo que está buscando: Inicio que escribe el nombre y Quick Insights le rellenará los espacios en blanco
   * Haga clic en la lista desplegable y busque la lista

1. Cuando haya agregado al menos una dimensión y una métrica, se creará lo siguiente:

   * Una tabla improvisada con la dimensión a la izquierda (vertical) y la métrica en la parte superior (horizontal). Consulte esta tabla:

1. (Opcional) Desglose las dimensiones y vea los elementos de dimensión haciendo clic en la flecha > derecha junto a la dimensión.



## Limitaciones conocidas

Si intenta editar directamente dentro de la tabla, el generador de perspectiva rápida (la herramienta de relleno de espacios en blanco) no estará sincronizado. Puede restaurarla a la configuración anterior de Insight rápida, pero si no lo hace, la creación directa hará que la tabla se comporte ahora como una tabla improvisada tradicional.

