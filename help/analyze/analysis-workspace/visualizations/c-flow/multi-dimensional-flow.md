---
description: Un flujo interdimensional le permite examinar las rutas del usuario entre diversas dimensiones.
title: Flujos interdimensionales
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizaciones
role: Business Practitioner, Administrator
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '306'
ht-degree: 100%

---

# Flujos interdimensionales

Un flujo interdimensional le permite examinar las rutas del usuario entre diversas dimensiones.

Existe una etiqueta de dimensión en la parte superior de cada columna Flujo que hace que el uso de varias dimensiones en una visualización de flujo sea más intuitivo:

![](assets/flow.png)

Observaremos dos casos de uso: un caso de uso de aplicación y un caso de uso web.

## Caso de uso uno: app {#section_3D31D37B9C9F4134AE46C96291E41294}

La dimensión [!UICONTROL Nombre de la acción] se ha añadido al flujo, donde el principal elemento devuelto es [!UICONTROL ItemAdded]:

![](assets/multi-dimensional-flow.png)

Para explorar la interacción entre pantallas/páginas y acciones en esta aplicación, puede arrastrar la dimensión de página a múltiples lugares, en función de qué desee explorar:

* Arrástrela al final de la zona de colocación (dentro de la zona rectangular enmarcada en negro que aparece) para **sustituir** a los principales resultados en los extremos:

   ![](assets/multi-dimensional-flow2.png) ![](assets/multi-dimensional-flow3.png)

* Arrástrela al espacio en blanco al final (observe el horquillado negro) para **añadir en** la visualización:

   ![](assets/multi-dimensional-flow4.png)

Este es el resultado si decide sustituir el elemento ItemScaled de la columna derecha por la dimensión Página. El resultado principal ahora cambia por el resultado principal de la dimensión Página:

![](assets/multi-dimensional-flow5.png)

Ahora puede ver cómo se mueven los clientes entre las acciones y páginas. Puede explorar aún más el flujo si hace clic en distintos nodos:

![](assets/multi-dimensional-flow6.png)

Esto es lo que sucede si añade otra dimensión Nombre de la acción al final de la visualización:

![](assets/multi-dimensional-flow7.png)

Esto permite obtener información exhaustiva y realizar posibles cambios a la aplicación que está analizando.

## Caso de uso dos: web {#section_8D55983FA0C84926995270052AE01CD8}

Este caso de uso le muestra cómo puede analizar qué campañas obtienen el máximo número de entradas al sitio web.

Arrastre la dimensión Nombre de campaña a un nuevo flujo:

![](assets/multi-dimensional-flow8.png)

Ahora deseo ver a qué páginas están impulsando el tráfico estas campañas, por lo que arrastro la dimensión Página a la derecha de los resultados de flujo para añadirlos a la visualización:

![](assets/multi-dimensional-flow9.png)
