---
description: La variable pageName debe rellenarse con un identificador de página fácil de leer e intuitivo.
keywords: Implementación de Analytics
seo-description: La variable pageName debe rellenarse con un identificador de página fácil de leer e intuitivo.
seo-title: Estrategias de nominación de página
solution: Analytics
title: Estrategias de nominación de página
topic: Desarrollador e implementación
uuid: a 829 d 0 c 7-6 ebf -459 a-b 403-5 e 9 c 05161 e 5 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Estrategias de nominación de página

La variable pageName debe rellenarse con un identificador de página fácil de leer e intuitivo.

You can determine the best way of populating the *`pageName`* variable by looking at the structure of your website. The methods listed below outline various ways of populating the *`pageName`* variable.

While the *`pageName`* variable is central to identifying user behavior, Adobe recommends using multiple variables to indicate page information. Las mejores estrategias de asignación de nombres utilizan una variable diferente para cada nivel de jerarquía dentro del sitio, como se muestra a continuación:

* La variable *`channel`* se puede usar para indicar la sección del sitio.
* The *`pageName`* variable can be used to show content type.
* Se puede usar una variable de [!UICONTROL Perspectiva personalizada] (prop1) para ver el contenido detallado.

Los niveles de detalle varían, en función de la propiedad, como se muestra a continuación:

| Variable | Nivel del detalle | Ejemplo |
|---|---|---|
| Canal | Sección general | Electrónica |
| Prop1 | Subsección | Deportes : Deportes locales |
| PageName | Descripción del contenido general | Préstamos : Préstamo hipotecario : Comparación de tipos de interés |
| Prop2 | Descripción del contenido detallado | Electrónica : Notebook PC : Especificaciones detalladas : IBM Thinkpad T20 |

Cuantos más niveles tenga el sitio, más variables deberán utilizarse para identificar el contenido de la página. También puede ser ventajoso para las empresas permitir la superposición de variables. Por ejemplo, una variable detallada puede contener información no solo sobre el producto visualizado, sino también sobre la sección y subsección del sitio. Eso puede resultar especialmente útil cuando un producto o artículo aparece en más de una sección del sitio. 

Las siguientes estrategias de asignación de nombres de página describen de qué manera completar la variable *`pageName`* . Aunque sea tentador elegir la estrategia de asignación de nombres de página más sencilla de implementar, esta estrategia determina en gran medida la optimización de todos los informes de [!UICONTROL rutas] y [!UICONTROL páginas]. Elija cuidadosamente el modo de asignación de nombres de página.

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

Adobe does not recommend leaving the *`pageName`* blank, (which results in using the full URL of the page) even though you may be tempted to do so. The following side-effects are caused by leaving the *`pageName`* variable blank and using the *`pageURL`* as the page identifier.

* Es posible que el dominio y la ruta de una página no siempre se muestren de manera idéntica. Por ejemplo: las cuatro direcciones URL que se muestran a continuación devuelven una sola página:

   * `https://www.mysite.com/index.jsp`
   * `https://www.mysite.com`
   * `https://mysite.com/index.jsp`
   * `https://mysite.com/`
   If the *`pageName`* is left blank, each of these page names would occupy a separate entry in reports.

* Algunas páginas, por ejemplo las de formularios, se publican automáticamente, y de este modo eliminan las distinciones entre el formulario original y el de salida que resulta.
* Cuando se traduce una página a otro idioma mediante los motores de búsqueda u otras herramientas en línea, la dirección URL de la página es la dirección URL del motor de búsqueda (no la dirección URL del sitio).

## HTML (document.title) {#section_B99B8F66B0E2410FA7BFE44E6851EB3F}

If you have invested time into making your HTML titles readable and intuitive, you might consider using the same title as the value in the *`pageName`* variable. Adobe recommends using a server-side variable to populate the *`pageName`* rather than using JavaScript's [!DNL document.title]. Algunos exploradores interpretan el título HTML de forma diferente a otros, lo que podría hacer que [!DNL Analytics] reciba nombres de página diferentes desde exploradores diferentes.

El práctica recomendada para usar el título HTML es copiar los títulos existentes de cada página en una variable independiente o en un elemento de administración de contenido. Si decide realizar cambios en el título HTML para lograr la optimización del motor de búsqueda o por otros motivos, los nombres de páginas de [!DNL Analytics] no se verán afectados. Si el nombre de una página cambia en [!DNL Analytics], esta se convierte en una nueva página y no está conectada con el antiguo nombre, independientemente de la dirección URL asociada.
