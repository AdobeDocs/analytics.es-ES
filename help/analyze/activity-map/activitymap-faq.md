---
description: Preguntas frecuentes sobre la instalación, configuración y utilización de las funciones de Activity Map.
title: Preguntas frecuentes sobre Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 98%

---

# Preguntas frecuentes sobre Activity Map

Preguntas frecuentes sobre la instalación, configuración y utilización de las funciones de Activity Map.

+++¿Todos los clientes de Analytics tienen acceso a la página de habilitación de ActivityMap de las Herramientas de administración?
Las organizaciones con un contrato para Adobe Analytics Standard, Premium y Ultimate tienen acceso a Activity Map.
+++

+++¿Cómo es compatible Activity Map con las aplicaciones de una sola página (SPA)?
Cada pocos segundos, Activity Map analiza la página web en busca de cambios en la página. ActivityMap encuentra contenido nuevo en la página sin necesidad de cargar una página nueva, pero este contenido nuevo siempre se atribuye al primer nombre de página que se encuentra cuando se carga la página.

* Activity Map comprueba si la visibilidad de los vínculos que conoce ha cambiado. Si se encuentra un cambio en la visibilidad, la columna Presente de la tabla Vínculos en la página para ese vínculo se actualiza con [!UICONTROL Mostrado] u [!UICONTROL Oculto].

* Cuando la interacción del usuario crea contenido nuevo, cualquier elemento nuevo que AppMeasurement encuentre como vínculo se añadirá a la tabla [!UICONTROL Vínculos en la página]. Activity Map envía una nueva solicitud de datos que incluye estos nuevos vínculos. Los nuevos vínculos deben aparecer en la tabla [!UICONTROL Vínculos en la página] cuando la IU gestione la solicitud de datos.
+++

+++¿Activity Map proporciona datos sobre “vistas”?
No, Adobe no realiza el seguimiento de los vínculos que se visualizaron.
+++

+++¿Qué exploradores y versiones admite Activity Map?
Activity Map es compatible con la última versión de la mayoría de los exploradores modernos.
+++

+++¿Activity Map aumenta las llamadas al servidor?
Activity Map no envía llamadas al servidor por sí solo. En su lugar, las variables de datos de contexto de Activity Map se incluyen con las llamadas de vista de páginas de Analytics en la página siguiente.
+++

+++¿Por qué faltan algunas superposiciones de elementos clasificados?
Algunos vínculos clasificados, como los vínculos de submenú, están ocultos en la página. Como consecuencia, las superposiciones de vínculos correspondientes no se verán. La clasificación se calcula para todos los vínculos de la página, incluidos los vínculos ocultos.
+++

+++¿Cómo se determina la clasificación de vínculos en el informe Todos los vínculos?**
* **En los modos Degradación y Burbujas**: La clasificación se determina mediante la columna de métrica. En el caso de los vínculos con el mismo valor de métrica, la clasificación se basa también en el orden alfabético del ID de los vínculos.
* **En el modo Ganadores y perdedores**: La clasificación se determina, principalmente, mediante la columna % de ganancia. En el caso de los vínculos con la misma ganancia, la clasificación se basa también en el orden alfabético del ID de los vínculos.
+++

+++¿Cómo funciona Activity Map con las páginas que usan varios grupos de informes?
De forma predeterminada, Activity Map usa el grupo de informes asociado a la primera etiqueta que la página envía. Puede seleccionar otro grupo de informes etiquetado desde la ficha **[!UICONTROL Configuración de Activity Map]** > **[!UICONTROL Otros]**.
+++

+++¿Durante cuánto tiempo Activity Map analiza Adobe Analytics en la página?
Activity Map busca la presencia de Adobe Analytics durante un máximo de 20 segundos tras un evento de página completa.
+++

+++¿Cómo gestiona Activity Map el contenido dinámico?
Activity Map comprueba cada dos segundos si hay cambios en el estado de la página web, por ejemplo:

* Contenido HTML que se ha vuelto visible
* Contenido HTML que se ha ocultado
* Contenido HTML nuevo que se ha insertado

Si el contenido se oculta o muestra, la aplicación cambia automáticamente el estado de los vínculos afectados (y, por lo tanto, realiza superposiciones) de oculto a mostrado o viceversa. Si se inserta contenido nuevo, la aplicación recupera los vínculos asociados, extrae de ellos los datos de análisis y añade superposiciones para los vínculos.
+++

+++¿En qué métrica se basa el informe Flujo de página?
Todos los datos mostrados se basan en las vistas de página.
+++

+++¿Puedo exportar variables de datos de contexto de Activity Map a través de fuentes de datos?
Sí. Las [Columnas de datos](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) que usa Activity Map son `clickmaplink`, `clickmaplinkbyregion`, `clickmappage` y `clickmapregion`.
+++

+++¿Los segmentos funcionan en el modo Activo?
No, los segmentos no funcionan en el modo Activo.
+++

+++¿Es compatible Activity Map con los grupos de informes virtuales?
Sí. Sin embargo, debido a las limitaciones de los grupos de informes virtuales, el modo Activo de Activity Map no es compatible con los grupos de informes virtuales.
+++

+++¿Cómo puedo deshabilitar Activity Map?
Existen tres opciones:

* Elimine la función `AppMeasurement_Module_ActivityMap` desde el archivo JS
* Añada un código personalizado que reescriba la función anterior con un cuerpo vacío, por ejemplo:

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

* Configure AppMeasurement estableciendo `s.trackClickMap` y `s.trackInlineStats` a `false`
+++
