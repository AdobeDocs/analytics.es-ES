---
description: IQ de segmento (comparación de segmentos) es una de las características más utilizadas de Analysis Workspace y los clientes no dejan de encontrar formas innovadoras de obtener nuevas perspectivas con ella. Estos son solo algunos de los muchos casos de uso con éxito.
keywords: IQ de segmento
seo-description: IQ de segmento (comparación de segmentos) es una de las características más utilizadas de Analysis Workspace y los clientes no dejan de encontrar formas innovadoras de obtener nuevas perspectivas con ella. Estos son solo algunos de los muchos casos de uso con éxito.
seo-title: Casos de uso de IQ de segmento
title: Casos de uso de IQ de segmento
uuid: 2 a 98 b 96 b -5529-4 c 7 f-a 787-27920603 d 5 b 0 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Casos de uso de IQ de segmento

IQ de segmento (comparación de segmentos) es una de las características más utilizadas de Analysis Workspace y los clientes no dejan de encontrar formas innovadoras de obtener nuevas perspectivas con ella. Estos son solo algunos de los muchos casos de uso con éxito.

## Use case 1: compare mobile vs desktop implementations {#section_B3A5983E58D0470895C030EA527C4966}

**“Comparamos los impactos procedentes de un sitio con los del otro y encontramos enseguida varias inconsistencias de etiquetado. De este modo, evitamos problemas de datos antes del lanzamiento del producto”.**

**Situación**: un gestor de producto a cargo de un sitio web móvil y un sitio web de escritorio recibió la tarea de comprobar que las etiquetas de ambos fueran coherentes. Para asegurarse de que no había pasado por alto algo importante, empleó IQ de segmento para comparar los impactos procedentes del sitio móvil con los recibidos del sitio de escritorio. Notó que había olvidado etiquetar el evento de finalización de compra en el sitio web móvil y pudo arreglarlo antes del lanzamiento del sitio web móvil. Como resultado, el gestor de producto evitó el desastre de datos que hubiera supuesto que el sitio móvil no registrara ninguna conversión.

**Cómo configurar esta comparación:**

<table id="table_B5FA23CB34DE4331A8BD65ED4B351038"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segmento 1 </th> 
   <th colname="col3" class="entry"> Segmento 2 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Utilice/Cree un segmento en el nivel de impacto en el que </p> <p> </p> <p> 
     <ul id="ul_1F5D5136620E449D93A771CD2576A18A"> 
      <li id="li_CB32DD1033DA4E5CA3B9AD41030800E6">Tipo de dispositivo móvil es igual a Teléfono móvil o Tableta </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Utilice/Cree un segmento en el nivel de impacto en el que </p> <p> </p> <p> 
     <ul id="ul_79CC51C4C9494275B3F37B6D2AB0505E"> 
      <li id="li_83BE21AD1FB34195BAFF3F15421DBB3D">Tipo de dispositivo móvil no es igual a Teléfono móvil o Tableta </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Use case 2: compare customers who use a certain feature to those who don't {#section_878B08FDD70A45E186C1F28EBA296636}

**“Comprobamos que los clientes que usaban nuestra función de comparación de productos tenían una probabilidad un 10 % mayor de realizar una conversión. Pasamos esta función a la parte superior de la página ¡y los pedidos aumentaron un 4 %!”**

**Situación:** el equipo de optimización de un sitio de venta quería comprender mejor a los usuarios que interactuaban con una función de comparación de productos que habían lanzado recientemente. Creando un segmento con los visitantes que habían interactuado con la función, pudieron utilizar IQ de segmento para comparar a estos usuarios con los demás visitantes. IQ de segmento identificó enseguida varias diferencias importantes, incluido el hecho de que estos usuarios tenían una probabilidad un 10 % mayor de adquirir un producto. El equipo de optimización del sitio decidió destacar la función de comparación de productos colocándola en la parte superior de la página.

**Cómo configurar esta comparación:**

| Segmento 1 | Segmento 2 |
|--- |--- |
| Utilice/cree un segmento en el nivel de visitante para los visitantes que han interactuado con la herramienta de comparación de precios. | Utilice el segmento Todos los demás que se genera automáticamente y que abarca a todos aquellos no incluidos en el segmento 1. |

## Use case 3: compare news site visitors to other site section visitors {#section_0EAFC90C450244058B161200AC9901B8}

**“Descubrimos que los visitantes de nuestra sección de noticias veían dos veces más anuncios en vídeo, así que añadimos más opciones de vídeo en esa sección. ¡Experimentamos un aumento del 7 % en el visionado de anuncios en vídeo!”**

**Situación:** una gran empresa de publicación multimedia buscaba un modo de mejorar la interacción de la audiencia con el contenido en su sección de noticias. Para comprender mejor a la audiencia de noticias, crearon un segmento con los visitantes de dicha sección. IQ de segmento escaneó todas las métricas y dimensiones, y determinó inmediatamente que estos usuarios tenían el doble de probabilidades de ver anuncios en vídeo que los de cualquier otra sección del sitio. El equipo de vídeo montó una sección de vídeos recomendados en el carril lateral de la sección de noticias y logró un aumento del 7 % en el número de anuncios en vídeo vistos. Podían haber dedicado su tiempo y esfuerzo a muchas otras cosas, pero IQ de segmento les mostró un camino evidente que produjo resultados rápidos y mensurables.

**Cómo configurar esta comparación:**

| Segmento 1 | Segmento 2 |
|--- |--- |
| Utilice/cree un segmento en el nivel del visitante para los visitantes de la sección Noticias. | Utilice el segmento Todos los demás que se genera automáticamente y que abarca a todos aquellos no incluidos en el segmento 1. |

## Use case 4: compare visitors from paid search to everyone else {#section_73912670409349CAB131FE9D8B4FB11C}

**“Los visitantes que llegaban a nuestro sitio desde motores de búsqueda tenían tres veces más probabilidades de mejorar una compra que todos los demás. Como resultado, aumentamos el gasto en palabras clave específicas y logramos un aumento del 56 % en la mejora de compras”.**

**Situación:** una gran empresa de servicios B2B quería entender el tipo de tráfico que llegaba a su sitio a partir de palabras clave de búsqueda pagadas. Las búsquedas pagadas no habían resultado en muchas conversiones directas y el responsable de marketing estaba pensando en reducir el presupuesto para ello. El equipo de marketing creó un segmento con los visitantes que llegaban al sitio desde búsquedas pagadas y lo comparó mediante IQ de segmento con todos los demás visitantes. Descubrieron que, aunque era menos probable que estos visitantes supusieran una conversión directa, tenían tres veces más probabilidades de mejorar un servicio comprado con anterioridad. De este modo, el equipo de marketing pudo concentrar el presupuesto en palabras clave relacionadas con la mejora de ventas, lo que resultó en un aumento del 56 % en este aspecto.

**Cómo configurar esta comparación:**

| Segmento 1 | Segmento 2 |
|--- |--- |
| Utilice/cree un segmento en el nivel de visitante para los visitantes referidos por una búsqueda natural y los procedentes de una campaña SEM. | Utilice el segmento Todos los demás que se genera automáticamente y que abarca a todos aquellos no incluidos en el segmento 1. |

## Use case 5: compare Fitbit purchasers to everyone else {#section_9142B8A270764545B0A516AA309F1785}

**“Descubrimos que las personas que compraban Fitbits tenían 6 veces más probabilidad de recibir un mensaje 'sin existencias' que todos los demás, por lo que encargamos rápidamente más Fitbits para evitar quedarnos sin stock”.**

**Escenario:** Un importante minorista en línea estaba interesado en saber cómo se vendía uno de los productos estrella de las fiestas (Fitbit) y en qué se diferenciaban los compradores de Fitbit de otros clientes. El equipo de marketing solo tuvo que hacer clic derecho en el elemento “Fitbit” del informe de productos y ejecutar un rápido análisis con IQ de segmento. Lo que descubrieron fue que los usuarios que compraban Fitbits tenían 6 veces más probabilidad de encontrarse el mensaje “sin existencias” que cualquier otro cliente. Tras nuevos análisis, pudieron dirigir a estos visitantes a las tiendas físicas mientras ellos esperaban a que el departamento de compras realizara nuevos pedidos de Fitbits. Como resultado, el minorista evitó nuevos mensajes de falta de existencias y pudo satisfacer mejor la demanda de las fiestas.

**Cómo configurar esta comparación:**

<table id="table_9018BEB4C2DE429FA773B250CB5C3E58"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segmento 1 </th> 
   <th colname="col3" class="entry"> Segmento 2 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Utilice/Cree un segmento en el nivel de visitante en el que </p> <p> 
     <ul id="ul_52E8ED6F4F7241D5ABE4EE7EA1E556D8"> 
      <li id="li_33750601AB2A43728834B29AF86D5CCF">Pedidos es mayor que o igual a 1 Y </li> 
      <li id="li_4E09D1286DAE4BABA49E4834E73BDC28">Marca es igual a Fitbit </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Utilice el segmento <span class="wintitle">Todos los demás</span> que se genera automáticamente y que abarca a todos aquellos no incluidos en el segmento 1. </p> </td> 
  </tr> 
 </tbody> 
</table>

