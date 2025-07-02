---
title: Casos de uso de comparación de segmentos
description: Descubra casos de uso reales sobre cómo la utilización del panel de comparación de segmentos para obtener información sobre la estrategia de marketing.
keywords: IQ de segmento
feature: Segmentation
role: User, Admin
exl-id: d7c02e5c-5313-4e12-86cb-d483644ccbc7
source-git-commit: 24dd47e995523aedba1385ee8882af5e11c7b128
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 18%

---

# Casos de uso de comparación de segmentos

El panel de comparación de segmentos es una función muy utilizada en Analysis Workspace. Los clientes descubren con frecuencia nuevas formas de generar perspectivas. Los siguientes son varios casos de éxito.

## Caso de uso 1: Comparar implementaciones móviles y de escritorio

> *&quot;Ha comparado las visitas de un sitio a otro y ha encontrado rápidamente varias incoherencias en el etiquetado. De este modo, evitó problemas de datos antes del lanzamiento del producto.&quot;*

Usted está a cargo de un sitio web móvil y un sitio web de escritorio, y tiene la tarea de asegurarse de que las etiquetas sean coherentes en todos los dispositivos móviles y de escritorio. Para asegurarse de que no se pierde nada importante, utilice el panel de comparación de segmentos para comparar las visitas provenientes de su sitio móvil con las visitas provenientes de su sitio de escritorio. Observe que no hay eventos de cierre de compra en el sitio web móvil y obtenga las etiquetas correctas antes de que se publique el sitio móvil. Como resultado, se evita un desastre de datos debido a que el sitio móvil no registra ninguna conversión.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visita individual en el que Tipo de dispositivo móvil es igual a Teléfono móvil o Tablet | Todos los demás |

## Caso de uso 2: Comparar a los clientes que usan una determinada función con los clientes que no lo hacen

> *&quot;Descubrió que los clientes que usaron su característica de comparación de productos tenían una probabilidad un 10% mayor de realizar una conversión. ¡Ha movido la comparación de productos al principio de la página y ha aumentado los pedidos en un 4%!&quot;*

El equipo de optimización de un sitio de venta minorista desea comprender mejor a los usuarios que interactúan con una función de comparación de productos que lanzaron recientemente. Utilizan el panel de comparación de segmentos para comparar a los usuarios que utilizan la función de comparación de productos con los demás usuarios del sitio. Identifican rápidamente varias diferencias importantes, incluido el hecho de que estos usuarios tienen una probabilidad un 10 % mayor de comprar un producto. El equipo de optimización del sitio decide destacar la función de comparación de productos colocándola en la parte superior de la página.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visitante en el que se produce un evento personalizado (herramienta de comparación de precios) | Todos los demás |

## Caso de uso 3: Comparar los visitantes a un sitio de noticias con los de otras secciones

> *&quot;Descubrió que los visitantes de su sección de noticias duplicaban la probabilidad de ver anuncios de vídeo, por lo que agregó más opciones de vídeo a esa sección. ¡Ha experimentado un aumento del 7 % en los anuncios de vídeo vistos!&quot;*

Una gran empresa de publicación multimedia busca formas de mejorar la participación del contenido para las audiencias en su sección de noticias. Crean un segmento de visitantes que visitan la sección del sitio de noticias para comprender mejor a la audiencia. Inmediatamente descubren que estos usuarios tienen el doble de probabilidades de ver anuncios en vídeo que los visitantes de cualquier otra sección del sitio. El equipo de vídeo montó una sección de vídeos recomendados en el carril lateral de la sección de noticias y logró un aumento del 7 % en el número de anuncios en vídeo vistos.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visitante donde Sección del sitio es igual a “Noticias” | Todos los demás |

## Caso de uso 4: Comparar los visitantes de búsquedas pagadas con todos los demás

> *&quot;Los visitantes que llegaban a su sitio desde motores de búsqueda tenían tres veces más probabilidades de mejorar una compra que todos los demás. Como resultado, aumentaste el gasto en palabras clave específicas y lograste un aumento del 56 % en la mejora de ventas.&quot;*

Una gran empresa de servicios B2B quiere comprender el tipo de tráfico que generan las palabras clave de búsqueda pagadas en su sitio. La búsqueda de pago no ha resultado en numerosas conversiones directas y el ejecutivo de marketing considera la posibilidad de reducir el presupuesto para ello. El equipo de marketing crea un segmento con los visitantes que acceden al sitio mediante búsquedas pagadas y lo compara con el resto de visitantes mediante el panel de comparación de segmentos. Descubren que, aunque es menos probable que estos visitantes suban sus ventas directamente, tienen tres veces más probabilidades de mejorar un servicio comprado con anterioridad. El equipo de marketing centra su presupuesto únicamente en las palabras clave relacionadas con la mejora de ventas y observa un aumento del 56 % en estas últimas.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visitante donde Tipo de referente es igual a Búsqueda de pago | Todos los demás |

## Caso de uso 5: Comparar a los compradores de Fitbit con todos los demás

> *&quot;Comprobó que las personas que compraban productos Fitbit tenían 6 veces más probabilidad de recibir un mensaje &quot;sin existencias&quot; que todos los demás. Por lo tanto, ¡encargó rápidamente más Fitbits y evitó quedarse sin stock!&quot;*

**Escenario:** Un importante retailer en línea está interesado en saber qué tal se vende uno de los productos estrella de las fiestas, Fitbit, y en qué se diferencian sus compradores de los demás clientes. El equipo de marketing puede seleccionar el elemento de línea Fitbit en su informe de productos y ejecutar rápidamente un análisis de comparación de segmentos desde el menú contextual. Lo que descubren es que los usuarios que compran productos Fitbit tienen 6 veces más probabilidad de encontrarse el mensaje &quot;sin existencias&quot; que cualquier otro cliente. Tras nuevos análisis, el equipo de marketing puede dirigir a estos visitantes a sus tiendas físicas mientras esperan a que su departamento de compras realice nuevos pedidos de productos Fitbit. Como resultado, retailer evita más mensajes de falta de existencias y puede satisfacer una mayor demanda de días festivos.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visitante con pedidos realizados y una dimensión personalizada de Marca (FitBit) | Todos los demás |
