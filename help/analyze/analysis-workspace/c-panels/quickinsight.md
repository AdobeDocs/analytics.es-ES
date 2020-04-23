---
description: Quick Insights Builder es una herramienta para nuevos usuarios de Workspace que les guía en la creación de tablas de datos y visualizaciones
title: Creador de perspectivas rápidas
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# Creador de perspectivas rápidas

>[!IMPORTANT]
>
>**[!UICONTROL Quick Insights]** está actualmente en pruebas beta y no está disponible para todos los clientes de Adobe Analytics.

[!UICONTROL Quick Insights] proporciona orientación a los no analistas y a los nuevos usuarios de [!UICONTROL Analysis Workspace] para que aprendan a responder preguntas comerciales de forma rápida y sencilla. También es una buena herramienta para usuarios avanzados que desean responder a una simple pregunta rápidamente sin tener que crear una tabla ellos mismos.

Al utilizar este [!UICONTROL Analysis Workspace], puede que se pregunte qué visualizaciones resultarían más útiles, qué dimensiones y métricas podrían facilitar la información, dónde arrastrar y soltar elementos, dónde crear un segmento, etc.

Para ayudarle con esto, y en función del uso que haga su propia compañía de los componentes de datos en [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] aprovecha un algoritmo que le presentará las dimensiones, métricas, segmentos e intervalos de fechas más populares que utiliza su compañía.

[!UICONTROL Quick Insights] ayuda a

* Cree correctamente una tabla de datos y la visualización que la acompaña en [!UICONTROL Analysis Workspace].
* Conozca la terminología y el vocabulario de los componentes y piezas de [!UICONTROL Analysis Workspace].
* Realice desgloses simples de dimensiones, agregue varias métricas o compare segmentos fácilmente dentro de un [!UICONTROL Freeform table].
* Cambie o pruebe varios tipos de visualización para encontrar la herramienta de búsqueda para su análisis de forma rápida e intuitiva.

## Terminología clave básica

A continuación se incluyen algunos de los términos básicos con los que debe estar familiarizado. Cada tabla de datos consta de dos o más bloques de creación (componentes) que se utilizan para contar el historial de datos.

| Bloque de creación (componente) | Definición |
|---|---|
| [!UICONTROL Dimension] | Las dimensiones son descripciones o características de los datos de métricas que se pueden ver, desglosar y comparar en un proyecto. Son valores no numéricos y fechas que se desglosan en elementos de dimensión. Por ejemplo, &quot;browser&quot; o &quot;page&quot; son dimensiones. |
| [!UICONTROL Dimension item] | Los elementos de dimensión son valores individuales para una dimensión. Por ejemplo, los elementos de dimensión para la dimensión del navegador serían &quot;Chrome&quot;, &quot;Firefox&quot;, &quot;Edge&quot;, etc. |
| [!UICONTROL Metric] | Las métricas son información cuantitativa sobre la actividad de visitantes, como vistas, pulsaciones, recargas, tiempo promedio empleado, unidades, pedidos, ingresos, etc. |
| [!UICONTROL Visualization] | Workspace oferta [una serie de visualizaciones](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) para crear representaciones visuales de los datos, como gráficos de barras, gráficos circulares, histogramas, gráficos de líneas, mapas, gráficos de dispersión, etc. |
| [!UICONTROL Breakdown] | Un desglose es una manera de desglosar literalmente una dimensión por otras dimensiones. En nuestro ejemplo, puede desglosar Estados de EE. UU. por Dispositivos portátiles para obtener las visitas de dispositivos móviles por estado, por tipo de dispositivo móvil o por regiones, por Campañas internas, etc. |
| [!UICONTROL Segment] | Los segmentos permiten identificar subconjuntos de visitantes en función de las características o las interacciones con el sitio web. Por ejemplo, puede generar [!UICONTROL Visitor] segmentos basados en atributos: tipo de explorador, dispositivo, número de visitas, país, sexo o según las interacciones: campañas, búsqueda de palabras clave, motor de búsqueda o en función de salidas y entradas: visitantes de Facebook, una página de aterrizaje definida, un dominio de referencia o basados en variables personalizadas: campo de formulario, categorías definidas, ID de cliente. |

## Introducción a Quick Insights

1. Inicie sesión en Adobe Analytics con las credenciales que se le han proporcionado.
1. Vaya a [!UICONTROL Workspace] y haga clic en **[!UICONTROL Create New Project]** y, a continuación, en **[!UICONTROL Quick Insights Builder]**.

   ![](assets/qibuilder.png)

1. Al salir del inicio por primera vez, lea el breve tutorial que le enseña algunos de los [!UICONTROL Quick Insights Builder] conceptos básicos. O bien, haga clic en **[!UICONTROL Skip Tutorial]**.
1. Seleccione los componentes (también conocidos como componentes): dimensiones (naranja), métricas (verde), segmentos (azul) o intervalos de fechas (púrpura) Debe seleccionar al menos una dimensión y una métrica para crear una tabla automáticamente.

   ![](assets/qibuilder2.png)

   Existen tres formas de seleccionar los componentes:
   * Arrástrelos y suéltelos desde el carril izquierdo.
   * Si sabe lo que está buscando: Inicio escribiendo el nombre y [!UICONTROL Quick Insights Builder] rellenará los espacios en blanco.
   * Haga clic en la lista desplegable y busque la lista.

1. Cuando haya agregado al menos una dimensión y una métrica, se creará lo siguiente:

   * Una tabla improvisada con la dimensión (aquí, Estados de EE.UU.) verticalmente y la métrica (aquí, Visitas) horizontalmente en la parte superior. Consulte esta tabla:
   ![](assets/qibuilder3.png)

   * Una visualización adjunta, en este caso un gráfico [de barras](/help/analyze/analysis-workspace/visualizations/bar.md). La visualización que se genera se basa en el tipo de datos agregados a la tabla. Para cambiar el tipo de visualización, haga clic en la flecha desplegable situada junto a **[!UICONTROL Bar]**.


1. (Opcional) Desglose las dimensiones y vea los elementos de dimensión haciendo clic en la flecha > derecha junto a la dimensión.

1. Intente agregar más refinamientos como se describe a continuación en &quot;Otras opciones útiles&quot;.

## Otras opciones útiles

En el [!UICONTROL Quick Insights Builder]informe aparecerán otras sugerencias útiles, algunas de ellas según la última acción.

* **Intente arrastrar y soltar**: Si, por ejemplo, ha utilizado la lista desplegable para seleccionar el bloque de creación, puede que aparezca:

   ![](assets/qibuilder4.png)

* **Cambiar la visualización**: le anima a probar distintas representaciones visuales de sus datos hasta encontrar la que realmente brille. Este es un ejemplo de gráfico de líneas:

   ![](assets/qibuilder8.png)

* **Desglose por**: Puede usar hasta 3 niveles de desgloses en dimensiones para explorar en profundidad los datos que realmente necesita.

   ![](assets/qibuilder5.png)

* **Añadir más métricas**: Puede agregar hasta dos métricas más utilizando el operador Y para agregarlas a la tabla.

   ![](assets/qibuilder6.png)

* **Añadir más segmentos**: Puede agregar hasta dos segmentos más utilizando los operadores Y u O para agregarlos a la tabla. Observe lo que sucede en la tabla cuando agrega Usuarios móviles O Visitantes fieles. Están uno al lado del otro, encima de las métricas. Si agregara Usuarios móviles Y Visitantes fieles, vería los resultados de ambos segmentos juntos y se apilarían uno encima del otro en la tabla.

   ![](assets/qibuilder7.png)

## Limitaciones conocidas

Si intenta editar directamente dentro de la tabla, hará que la [!UICONTROL Quick Insights Builder] (la herramienta de relleno de espacios en blanco) se quede sin sincronizar. Puede restaurarla a la configuración anterior de Quick Insight si ingresa a **[!UICONTROL Help > Tutorials]** o puede borrar la tabla haciendo clic **[!UICONTROL Resync Builder]** en la parte superior derecha del panel Quick Insights.

De lo contrario, la creación directa hará que la tabla ahora se comporte como una tabla improvisada tradicional, sin las funciones útiles para los nuevos usuarios.

