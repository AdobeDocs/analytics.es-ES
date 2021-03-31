---
description: Preguntas frecuentes sobre la instalación, configuración y utilización de las funciones de Activity Map.
title: Preguntas frecuentes sobre Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: Profesional empresarial, administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 25%

---


# Preguntas frecuentes sobre Activity Map

Preguntas frecuentes sobre la instalación, configuración y utilización de las funciones de Activity Map.

## ¿Todos los clientes de Analytics tienen acceso a la página de habilitación de Activity Map de las herramientas de administración?

Las organizaciones con un contrato para Adobe Analytics Standard, Premium y Ultimate tienen acceso a Activity Map.

## ¿Proporciona el Activity Map datos sobre &quot;vistas&quot;?

No, Adobe no realiza el seguimiento de los vínculos que se vieron.

## ¿Qué exploradores y versiones admite Activity Map?

Activity Map es compatible con la última versión de la mayoría de los navegadores modernos.

## ¿El Activity Map aumenta las llamadas al servidor?

Activity Map no envía llamadas al servidor por sí solo. En su lugar, las variables de datos de contexto de Activity Map se incluyen con las llamadas de vista de página de Analytics en la página siguiente.

## ¿Por qué faltan algunas superposiciones de elementos clasificados?**

Algunos vínculos clasificados, como los vínculos de submenú, están ocultos en la página. Como consecuencia, no se muestran las superposiciones de vínculos correspondientes. La clasificación se calcula para todos los vínculos de la página, incluidos los vínculos ocultos.

## ¿Cómo se determina la clasificación de vínculos en el informe Todos los vínculos?**

* **En el modo** Degradación y Burbujas : La clasificación se determina mediante la columna de métrica. En el caso de los vínculos con el mismo valor de métrica, la clasificación se basa también en el orden alfabético del ID de los vínculos.
* **En el modo** Ganador y perdedor: La clasificación viene determinada principalmente por la columna % de ganancia. En el caso de los vínculos con la misma ganancia, la clasificación se basa también en el orden alfabético del ID de los vínculos.

## ¿Cómo funciona el Activity Map con las páginas que usan varios grupos de informes?

De forma predeterminada, Activity Map utiliza el grupo de informes asociado con la primera etiqueta que envía la página. Puede seleccionar otro grupo de informes etiquetado desde la ficha **[!UICONTROL Configuración de Activity Map]** > **[!UICONTROL Otros]**.

## ¿Durante cuánto tiempo analiza el Activity Map para Adobe Analytics en la página?

Activity Map busca la presencia de Adobe Analytics durante un máximo de 20 segundos tras un evento de página completa.

## ¿Cómo gestiona el Activity Map el contenido dinámico?

El Activity Map comprueba cada 2 segundos si se han encontrado cambios en el estado de la página web, por ejemplo:

* Contenido HTML que se ha vuelto visible
* Contenido HTML que se ha ocultado
* Contenido HTML nuevo que se ha insertado

Si el contenido se oculta o muestra, la aplicación cambia automáticamente el estado de los vínculos afectados (y, por lo tanto, realiza superposiciones) de oculto a mostrado o viceversa. Si se inserta contenido, la aplicación recupera los vínculos asociados, extrae los datos de análisis correspondientes y añade superposiciones para estos vínculos.

## ¿En qué métrica se basa el informe Flujo de página?

Todos los datos mostrados se basan en las vistas de páginas.

## ¿Puedo exportar variables de datos de contexto de Activity Map a través de fuentes de datos?

Las variables de datos de contexto de Activity Map no están disponibles en las fuentes de datos.

## ¿Los segmentos funcionan en el modo Activo?

No, los segmentos no funcionan en el modo Activo. La funcionalidad es equivalente a la de los informes en tiempo real de Reports &amp; Analytics, que no admiten segmentación.

## ¿Es Activity Map compatible con los grupos de informes virtuales?

Sí. Sin embargo, debido a las limitaciones de los grupos de informes virtuales, el modo Activo de Activity Map no es compatible con los grupos de informes virtuales.
