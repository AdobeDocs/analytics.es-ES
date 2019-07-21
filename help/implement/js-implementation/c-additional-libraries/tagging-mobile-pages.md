---
description: El código de seguimiento móvil se coloca en la página en forma de etiqueta de imagen generada por el servidor.
keywords: Implementación de Analytics; seguimiento móvil; protocolos móviles; evitar caché; alt tag; tipo de imagen predeterminado
seo-description: El código de seguimiento móvil se coloca en la página en forma de etiqueta de imagen generada por el servidor.
seo-title: Etiquetado de páginas para protocolos móviles
solution: Analytics
title: Etiquetado de páginas para protocolos móviles
topic: Desarrollador e implementación
uuid: 5788 beaf-f 309-4918-a 99 c-a 3 e 591668205
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Etiquetado de páginas para protocolos móviles

El código de seguimiento móvil se coloca en la página en forma de etiqueta de imagen generada por el servidor.

El código de seguimiento móvil se coloca en la página en forma de etiqueta de imagen generada por el servidor. Los dispositivos móviles no suelen admitir los lenguajes de scripting como JavaScript y WMLScript, por lo que la señalización de seguimiento no puede generarse de forma dinámica a través de estos lenguajes.

Si la imagen de señalización móvil es en realidad de 2 x 2 píxeles, establezca las propiedades de altura y ancho en 5 para garantizar que se admitirá en todos los dispositivos móviles. Por ejemplo:

```
<img sr c="https://metric.mydomain.com/b/ss/<Report_Suite_Name>/5/<random_number>?pageName=" alt="" width="5" height="5"/>
```

## Uso de un número aleatorio para evitar el almacenamiento en caché {#section_BF5C344A16034C439C8704632CF673A7}

Aunque los servidores de Adobe indican a los exploradores que no almacenen en caché la señalización de seguimiento, no es seguro que todos los exploradores sigan estas instrucciones. Para tratar de evitar aún más el almacenamiento en caché de la señalización, es recomendable que el servidor web genere dinámicamente un número aleatorio en la ruta URL de la imagen. Al hacerlo se asegura una mayor precisión de los informes. El número aleatorio debe estar en la última sección de la ruta, como se indica aquí:

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" />.
```

## Inclusión de una etiqueta ALT {#section_FBD8B2FD1EA0429580C2B933DA300B07}

Algunos exploradores móviles requieren que todas las imágenes contengan texto alternativo en la etiqueta de imagen. A continuación se muestra cómo debe aparecer el atributo ALT en la etiqueta de imagen:

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" alt=""/>.
```

Es importante que /5/ aparezca siempre correctamente en la ruta. Los servidores de Adobe lo utilizan para identificar los dispositivos móviles. Si se usa el /1/ estándar, los servidores de Adobe intentan configurar una cookie en el dispositivo móvil.

## Cambio del tipo de imagen predeterminado {#section_2F969909010D4A64BF6E092A32ABADB7}

Si el tipo de imagen predeterminado no se admite en un dispositivo particular, no se devuelve ningún dato. Para evitarlo, puede forzar el servidor de recopilación de datos de Adobe para que devuelva un tipo de gráfico particular que el dispositivo móvil sí admita. El código que sigue al nombre del grupo de informes especifica el tipo de imagen:

* `/5/` devuelve el tipo de imagen predeterminado.
* `/5.1/` o `/1/` siempre devuelve una imagen GIF.

* `/5.5/` siempre devuelve una imagen WBMP.

See [Identifying Visitors using Mobile Protocols](../../../implement/js-implementation/c-unique-visitors/visid-mobile.md#concept_8C5557634014440AA3588FBB0CF6BB49).
