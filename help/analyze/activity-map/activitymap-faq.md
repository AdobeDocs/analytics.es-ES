---
description: Preguntas frecuentes sobre la instalación, configuración y utilización de las funciones de Activity Map.
title: Preguntas frecuentes sobre Activity Map
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: ec93137d0b5334e312fe0ec42953457243117d4a
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 24%

---


# Preguntas frecuentes sobre Activity Map

Preguntas frecuentes sobre la instalación, configuración y utilización de las funciones de Activity Map.

## ¿Todos los clientes de Analytics tienen acceso a la página de habilitación de Activity Map de las Herramientas de administración?

Las organizaciones con contrato para Adobe Analytics Standard, Premium y Ultimate tienen acceso a Activity Map.

## ¿Proporciona Activity Map datos sobre &quot;vistas&quot;?

No, Adobe no rastrea los vínculos que se vieron.

## ¿Qué exploradores y versiones admite Activity Map?

Activity Map admite la versión más reciente de la mayoría de los navegadores modernos.

## ¿Aumenta el Activity Map las llamadas al servidor?

Activity Map no envía llamadas al servidor por sí solo. En su lugar, las variables de datos de contexto de Activity Map se incluyen con las llamadas de vista de página de Analytics en la página siguiente.

## ¿Por qué faltan algunas superposiciones de elementos clasificados?**

Algunos vínculos clasificados, como los vínculos de submenú, están ocultos en la página. Como consecuencia, no se muestran las superposiciones de vínculos correspondientes. La clasificación se calcula para todos los vínculos de la página, incluidos los vínculos ocultos.

## ¿Cómo se determina la clasificación de vínculos en el informe Todos los vínculos?**

* **En el modo** Degradado y burbuja: La clasificación está determinada por la columna de métrica. En el caso de los vínculos con el mismo valor de métrica, la clasificación se basa también en el orden alfabético del ID de los vínculos.
* **En el modo** Ganador y Perdedor: La clasificación está determinada principalmente por la columna % de ganancia. Para los vínculos con la misma ganancia, la clasificación se basa en el orden alfabético del ID del vínculo.

## ¿Cómo funciona el Activity Map con las páginas que utilizan múltiples grupos de informes?

De forma predeterminada, Activity Map utiliza el grupo de informes asociado con la primera etiqueta que envía la página. Puede seleccionar otro grupo de informes etiquetado desde la ficha **[!UICONTROL Configuración de Activity Map]** > **[!UICONTROL Otros]**.

## ¿Cuánto tiempo explora el Activity Map para Adobe Analytics en la página?

El mapa de actividad busca la presencia de Adobe Analytics durante un máximo de 20 segundos después del evento de finalización de una página.

## ¿Cómo gestiona Activity Map el contenido dinámico?

El Activity Map comprueba cada 2 segundos si ha encontrado cambios en el estado de la página web, como:

* Contenido HTML que se ha vuelto visible
* Contenido HTML que se ha ocultado
* Contenido HTML nuevo que se ha insertado

Si el contenido se oculta o muestra, la aplicación cambia automáticamente el estado de los vínculos afectados (y, por lo tanto, realiza superposiciones) de oculto a mostrado o viceversa. Si se inserta contenido nuevo, la aplicación recupera los vínculos asociados, extrae datos de análisis para ellos y agrega superposiciones para estos vínculos.

## ¿En qué métrica se basa el informe Flujo de página?

Todos los datos mostrados se basan en vistas de página.

## ¿Puedo exportar variables de datos de contexto de Activity Map a través de fuentes de datos?

Las variables de datos de contexto de mapa de actividad no están disponibles en las fuentes de datos.

## ¿Funcionan los segmentos en el modo Activo?

No, los segmentos no funcionan en el modo Activo. La funcionalidad es equivalente a la del sistema de informes en tiempo real en Informes y análisis, que no admite la segmentación.

## ¿Es Activity Map compatible con los grupos de informes virtuales?

Sí. Sin embargo, debido a las limitaciones de los grupos de informes virtuales, el modo Activo de Activity Map no es compatible con los grupos de informes virtuales.
