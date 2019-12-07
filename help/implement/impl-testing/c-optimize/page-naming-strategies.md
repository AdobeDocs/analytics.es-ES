---
description: La variable pageName debe rellenarse con un identificador de página fácil de leer e intuitivo.
keywords: Analytics Implementation
title: Estrategias de asignación de nombres de página
topic: Developer and implementation
uuid: a829d0c7-6ebf-459a-b403-5e9c05161e5c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Estrategias de asignación de nombres de página

La variable pageName debe rellenarse con un identificador de página fácil de leer e intuitivo.

Puede determinar la forma más adecuada para rellenar la variable *`pageName`* desde la estructura de su sitio web. Los métodos enumerados más adelante resumen varias maneras de rellenar la variable *`pageName`*.

Aunque la variable *`pageName`* es fundamental para identificar la conducta del usuario, Adobe recomienda utilizar varias variables para indicar la información de la página. Las mejores estrategias de asignación de nombres utilizan una variable diferente para cada nivel de jerarquía dentro del sitio, como se muestra a continuación:

* La variable *`channel`* se puede usar para indicar la sección del sitio.
* La variable *`pageName`* se puede usar para mostrar el tipo de contenido.
* Se puede usar una variable de [!UICONTROL Perspectiva personalizada] (prop1) para ver el contenido detallado.

Los niveles de detalle varían, en función de la propiedad, como se muestra a continuación:

| Variable | Nivel del detalle | Ejemplo |
|---|---|---|
| Canal | Sección general | Electrónica |
| Prop1 | Subsección | Deportes : Deportes locales |
| PageName | Descripción del contenido general | Préstamos : Préstamo hipotecario : Comparación de tipos de interés |
| Prop2 | Descripción del contenido detallado | Electrónica : Notebook PC : Especificaciones detalladas : IBM Thinkpad T20 |

Cuantos más niveles tenga el sitio, más variables deberán utilizarse para identificar el contenido de la página. También puede ser ventajoso para las empresas permitir la superposición de variables. Por ejemplo, una variable detallada puede contener información no solo sobre el producto visualizado, sino también sobre la sección y subsección del sitio. Eso puede resultar especialmente útil cuando un producto o artículo aparece en más de una sección del sitio.

Las siguientes estrategias de asignación de nombres de página describen de qué manera completar la variable *`pageName`* campaign. Aunque sea tentador elegir la estrategia de asignación de nombres de página más sencilla de implementar, esta estrategia determina en gran medida la optimización de todos los informes de [!UICONTROL rutas] y [!UICONTROL páginas]. Elija cuidadosamente el modo de asignación de nombres de página.

## Nombre único para cada página {#section_24704CA39E2F4C00ACEAFF39CA0A921B}

El método más valioso de asignación de nombres de página es dar a cada una un identificador único que sea fácil de entender por todos los usuarios de [!DNL Analytics] de la organización. Algunos ejemplos de nombres de página son Página de inicio, Departamento de electrónica y Deportes : Deportes locales : Ligas escolares.

La mayoría de los usuarios de [!DNL Analytics] encuentra que los nombres de páginas jerárquicos son útiles para identificar dónde se encuentra la página en el sitio y el propósito de la misma. La siguiente tabla muestra algunos nombres de páginas de muestra para diferentes sectores:

| Conversión | Medios | Finanzas |
|---|---|---|
| Página principal | Página principal | Página principal |
| Electrónica | Tecnología | Préstamos hipotecarios |
| Electrónica : Notebook PC | Tecnología : Nuevos dispositivos | Préstamos hipotecarios : Comparación de tipos de interés |
| Electrónica : Notebook PC : Página de productos | Tecnología : Nuevos dispositivos : Página de artículos | Préstamos hipotecarios : Comparación de tipos de interés : Fijo a 10 años |

## Ruta del archivo (no la dirección URL completa) {#section_37FDCDA00DA84B3D9B8AB4290555FF34}

Para algunos sitios, la ruta del archivo es clara y fácil de leer. Cualquier usuario comercial puede leer una dirección URL y determinar la página a la que se refiere la ruta del archivo. Si este es el caso del sitio, puede utilizar una variable del lado del servidor para rellenar la ruta hacia el archivo en la variable *`pageName`*, tal como se muestra abajo:

```js
s.pageName="<%= file_path %>"
```

No se recomienda dejar el espacio de *`pageName`* en blanco (lo que haría que se utilizara la dirección URL completa de la página) aunque esté tentado de hacerlo. Si se deja en blanco el espacio de la variable *`pageName`* y se usa la *`pageURL`* como identificador de página, podría ocurrir lo siguiente:

* Es posible que el dominio y la ruta de una página no siempre se muestren de manera idéntica. Por ejemplo: las cuatro direcciones URL que se muestran a continuación devuelven una sola página:

   * `https://www.mysite.com/index.jsp`
   * `https://www.mysite.com`
   * `https://mysite.com/index.jsp`
   * `https://mysite.com/`
   Si el espacio de *`pageName`* se deja en blanco, cada uno de estos nombres de página ocuparía una entrada diferente en los informes.

* Algunas páginas, por ejemplo las de formularios, se publican automáticamente, y de este modo eliminan las distinciones entre el formulario original y el de salida que resulta.
* Cuando se traduce una página a otro idioma mediante los motores de búsqueda u otras herramientas en línea, la dirección URL de la página es la dirección URL del motor de búsqueda (no la dirección URL del sitio).

## HTML (document.title) {#section_B99B8F66B0E2410FA7BFE44E6851EB3F}

Si ha invertido tiempo en hacer que los títulos HTML sean más legibles e intuitivos, puede considerar la opción de usar el mismo título como valor en la variable *`pageName`*. Se recomienda usar una variable del lado del servidor para rellenar el espacio de *`pageName`* en lugar de usar el [!DNL document.title] de JavaScript. Algunos exploradores interpretan el título HTML de forma diferente a otros, lo que podría hacer que [!DNL Analytics] reciba nombres de página diferentes desde exploradores diferentes.

El práctica recomendada para usar el título HTML es copiar los títulos existentes de cada página en una variable independiente o en un elemento de administración de contenido. Si decide realizar cambios en el título HTML para lograr la optimización del motor de búsqueda o por otros motivos, los nombres de páginas de [!DNL Analytics] no se verán afectados. Si el nombre de una página cambia en [!DNL Analytics], esta se convierte en una nueva página y no está conectada con el antiguo nombre, independientemente de la dirección URL asociada.
