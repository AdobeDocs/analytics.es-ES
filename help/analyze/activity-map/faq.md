---
title: Preguntas frecuentes sobre Activity Map
description: Preguntas frecuentes relacionadas con Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: f242ec6613cf046224f76f7edc7813a34c65fff8
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 22%

---

# Preguntas frecuentes sobre Activity Map

Preguntas frecuentes relacionadas con Activity Map.

+++¿Cómo concedo permisos a Activity Map?

Los permisos para usar Activity Map y sus dimensiones asociadas se gestionan en [Adobe Admin Console](/help/admin/admin-console/home.md).

Los [elementos de permiso](/help/admin/admin-console/permissions/product-profile.md) necesarios para Activity Map incluyen:

* **[!UICONTROL Herramientas de Analytics]** > **[!UICONTROL Activity Map]**
* **[!UICONTROL Herramientas de Analytics]** > **[!UICONTROL Publicación de segmentos]**
* **[!UICONTROL Dimensiones]** > **[!UICONTROL Alcance de desplazamiento de Activity Map]**
* **[!UICONTROL Dimensiones]** > **[!UICONTROL Vínculo De Activity Map Por Región]**
* **[!UICONTROL Dimensiones]** > **[!UICONTROL Región de Activity Map]**
* **[!UICONTROL Dimensiones]** > **[!UICONTROL Vínculo de Activity Map]**
* **[!UICONTROL Dimensiones]** > **[!UICONTROL Página de Activity Map]**

Consulte [Permisos de perfil de productos para las herramientas de Analytics](/help/admin/admin-console/permissions/analytics-tools.md) para obtener más información.

+++

+++¿Todos los clientes de Analytics tienen acceso a Activity Map?

Las organizaciones con un contrato para Adobe Analytics Standard, Premium y Ultimate tienen acceso a Activity Map. Estos tipos de contrato representan la mayoría de los clientes de Adobe Analytics.

+++

+++¿Cómo es compatible Activity Map con las aplicaciones de una sola página (SPA)?

Cada pocos segundos, Activity Map analiza la página web en busca de cambios. Activity Map encuentra contenido nuevo en la página sin requerir una recarga, pero este contenido nuevo siempre se atribuye al primer valor de dimensión de página.

* Activity Map comprueba si la visibilidad de los vínculos que conoce ha cambiado. Si se encuentra un cambio en la visibilidad, la columna Presente de la tabla Vínculos en la página para ese vínculo se actualiza con [!UICONTROL Mostrado] u [!UICONTROL Oculto].

* Cuando la interacción del usuario crea contenido nuevo, cualquier elemento nuevo que AppMeasurement determine como vínculo se agrega a la tabla [!UICONTROL Vínculos en la página]. Activity Map envía una nueva solicitud de datos que incluye estos nuevos vínculos. Los nuevos vínculos aparecen en la tabla [!UICONTROL Vínculos en la página] cuando se devuelve la solicitud de datos.

+++

+++¿Activity Map proporciona datos sobre los vínculos que se ven pero no se pulsan?

No, Adobe no realiza un seguimiento automático de los vínculos que solo se visualizaron.

+++

+++¿Qué exploradores y versiones admite Activity Map?

Activity Map es compatible con la última versión de la mayoría de los navegadores modernos.

+++

+++¿Activity Map aumenta las llamadas al servidor?

Activity Map no envía llamadas al servidor por sí solo. En su lugar, las variables de datos de contexto de Activity Map se incluyen con las llamadas de vista de páginas de Analytics en la página siguiente. Sin embargo, algunas versiones anteriores de Activity Map en Web SDK envían una llamada independiente para los datos de Activity Map. Si su versión de Web SDK es la más reciente, los datos de Activity Map se combinan con el siguiente evento.

+++

+++¿Por qué faltan algunos números de clasificación en la superposición?

Algunos vínculos, como los que se incluyen en los menús, están ocultos en la página. Como resultado, las superposiciones de vínculos correspondientes no se muestran. La clasificación se calcula para todos los vínculos de la página, incluidos los vínculos ocultos.

+++

+++¿Cómo se determina la clasificación de vínculos en el informe Todos los vínculos?

* **En los modos Degradación y Burbujas**: La columna de métrica determina la clasificación. En el caso de los vínculos con el mismo valor de métrica, la clasificación se basa también en el orden alfabético del ID de los vínculos.
* **En modo Ganadores y perdedores**: La columna de porcentaje ganado determina la clasificación. En el caso de los vínculos con la misma ganancia, la clasificación se basa también en el orden alfabético del ID de los vínculos.

+++

+++¿Cómo funciona Activity Map con las páginas que usan varios grupos de informes?

De forma predeterminada, Activity Map utiliza el grupo de informes asociado a la primera etiqueta de la página. Puede seleccionar otro grupo de informes en la ficha **[!UICONTROL Configuración de Activity Map]** > **[!UICONTROL Otros]**.

+++

+++¿Durante cuánto tiempo analiza Activity Map para Adobe Analytics en la página?

Activity Map busca la presencia de Adobe Analytics durante un máximo de 20 segundos tras un evento de página completa.

+++

+++¿Cómo gestiona Activity Map el contenido dinámico?

Activity Map comprueba cada dos segundos si hay cambios en el estado de la página web, por ejemplo:

* Contenido HTML que se ha vuelto visible
* Contenido HTML que se ha ocultado
* Contenido HTML nuevo que se ha insertado

Si el contenido se oculta o muestra, la extensión cambia automáticamente el estado de los vínculos afectados (y, por lo tanto, las superposiciones) de oculto a mostrado o viceversa. Si se inserta contenido nuevo, la aplicación recupera los vínculos asociados, extrae de ellos los datos de análisis y añade superposiciones para los vínculos.

+++

+++¿En qué métrica se basa el informe Flujo de página?

Todos los datos mostrados se basan en las vistas de página.

+++

+++¿Puedo exportar datos de Activity Map a través de fuentes de datos?

Sí. Las [columnas de fuentes de datos](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) que utiliza Activity Map son:

* Vínculo de Activity Map: `clickmaplink`
* Página de Activity Map: `clickmappage`
* Región de Activity Map: `clickmapregion`
* Vínculo de Activity Map por región: `clickmaplinkbyregion`

+++

+++¿Los segmentos funcionan en el modo Activo?

No, los segmentos no funcionan en el modo Activo.

+++

+++¿Es compatible Activity Map con los grupos de informes virtuales?

Sí. Sin embargo, debido a las limitaciones de los grupos de informes virtuales, el modo Activo de Activity Map no es compatible con los grupos de informes virtuales.

+++

+++¿Cómo puedo deshabilitar Activity Map?

El método para deshabilitar Activity Map depende del tipo de implementación:

* **Extensión de Web SDK**: en las opciones de configuración de la extensión, desactive las casillas **[!UICONTROL Recopilar clics en vínculos internos]**, **[!UICONTROL Recopilar clics en vínculos externos]** y **[!UICONTROL Recopilar clics en vínculos de descarga]**.
* **Biblioteca JavaScript de Web SDK**: establezca [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) en `false`.
* **Extensión de Analytics**: en las opciones de configuración de la extensión, anule la selección de la casilla **[!UICONTROL Usar Activity Map]**.
* **AppMeasurement**: elimine o comente el módulo de Activity Map en `AppMeasurement.js`, o sobrescriba la llamada a la función del módulo con un cuerpo vacío:

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

+++

+++¿Cuáles son los requisitos del sistema para utilizar la superposición de Activity Map?

Puede utilizar la versión más reciente de Chrome, Edge o Firefox con la extensión Activity Map.

+++

+++¿Qué debo tener en cuenta al usar Activity Map para información personal?

Considere los siguientes escenarios en los que se pueden recopilar datos de identificación personal mediante Activity Map:

* **Vínculos de correo electrónico**: Si se puede hacer clic en una dirección de correo electrónico para abrir el cliente de correo del usuario, Activity Map puede recopilar la dirección de correo electrónico en la que se hizo clic.
* **Vínculos de ID de usuario**: Una vez que un visitante inicia sesión, Activity Map puede registrar cualquier vínculo que contenga el ID de usuario del visitante.
* **Vínculos de información confidencial**: En el caso de las instituciones financieras, se puede realizar un seguimiento de la información confidencial, como el número de cuenta, si es un vínculo y el visitante hace clic en ella.
* **Vínculos que contienen información personal**: En los sitios web de atención médica, los vínculos pueden contener información personal. Si un visitante hace clic en estos vínculos, Activity Map recopila ese texto del vínculo.

+++

+++¿Qué datos rastrea Activity Map de forma predeterminada?

Activity Map realiza un seguimiento de los siguientes elementos:

* Una etiqueta `<a>` o `<area>` con una propiedad `href`. Los vínculos de etiquetas de anclaje (`#`) no se rastrean de manera predeterminada.
* Un atributo `onclick` que establece una variable `s_objectID`
* Una etiqueta `<input>` o un botón `submit` con un valor o texto secundario
* Una etiqueta `<input>` con el tipo `image` y una propiedad `src`
* Una etiqueta `<button>` sin el atributo `type="button"`. Si desea rastrear `<button>` etiquetas, considere la posibilidad de usar atributos como `role="button"` o `submit="button"` en su lugar.

+++

+++¿Cuáles son algunos ejemplos de vínculos que Activity Map rastrea automáticamente?

A continuación se muestran algunos ejemplos en los que Activity Map tiene toda la información necesaria para rastrear un vínculo.

```html
<a href="home.html">Home</a>

<input type="submit" value="Submit"/>

<input type="image" src="submit-button.png"/>

<p onclick="var s_objectID='Market rates';">
  <span class="title">Current Market Rates</span>
  <span class="subtitle">1.45 USD</span>
</p>

<div onclick="s.tl(true,'o','Chat button')">
  <span class="title">Chat with an agent now</span>
  <span class="subtitle">Current wait: 0 minutes</span>
</div>
```

+++

+++¿Cuáles son algunos ejemplos de vínculos que Activity Map NO rastrea automáticamente?

* La etiqueta de anclaje no tiene un `href` válido
* No están presentes los métodos [`s_objectID`](/help/implement/vars/page-vars/s-objectid.md) o [`tl()`](/help/implement/vars/functions/tl-method.md)
* Falta la propiedad `src` en un elemento de entrada de formulario

Los siguientes son algunos ejemplos en los que Activity Map no realiza un seguimiento de los clics:

```html
<!-- Anchor tag does not have a valid href -->
<a name="innerAnchor">Section header</a>

<!-- Neither s_objectID or tl() method present -->
<p onclick="showPanel('stock price')">
  <span class="title">Current company stock price</span>
  <span class="subtitle">987.65 USD</span>
</p>

<!-- Neither s_objectID or tl() method present -->
<input type="radio" onclick="changeState(this)" name="group1" value="A"/>
<input type="radio" onclick="changeState(this)" name="group1" value="B"/>
<input type="radio" onclick="changeState(this)" name="group1" value="C"/>

<!-- src property missing on a form input element -->
<input type="image"/>
```

+++
