---
title: Casos de uso de comparación de segmentos
description: Conozca los casos de uso del mundo real sobre cómo se puede utilizar el panel de comparación de segmentos para obtener información sobre la estrategia de mercadotecnia.
keywords: IQ de segmento
translation-type: tm+mt
source-git-commit: ca9f1ed00295b556250894ae4e7fa377ef8a593d

---


# Casos de uso de IQ de segmentos

El panel de comparación de segmentos es una función muy utilizada en Analysis Workspace. Los clientes descubren con frecuencia nuevas formas de generar perspectivas. Los siguientes son varios casos de uso exitosos.

## Caso de uso 1: comparar implementaciones móviles con implementaciones de escritorio

> *“Comparamos los impactos procedentes de un sitio con los del otro y encontramos enseguida varias inconsistencias de etiquetado. De este modo, evitamos problemas de datos antes del lanzamiento del producto”.*

Un administrador de productos a cargo de un sitio web móvil y un sitio web de escritorio recibió la tarea de asegurarse de que las etiquetas fueran coherentes en todos los dispositivos móviles y de escritorio. Para asegurarse de que no se había perdido nada importante, utilizó el panel de comparación de segmentos para comparar las visitas procedentes de su sitio de dispositivos móviles con las visitas procedentes de su sitio de escritorio. Observó que no había eventos de cierre de compra en el sitio web móvil y obtuvo las etiquetas correctas antes de que se lanzara el sitio móvil. Como resultado, el gestor de producto evitó el desastre de datos que hubiera supuesto que el sitio móvil no registrara ninguna conversión.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visita individual donde Tipo de dispositivo móvil es igual a Teléfono móvil o Tablet | Todos los demás |

## Caso de uso 2: comparar a los clientes que utilizan una determinada función con los que no

> *“Comprobamos que los clientes que usaban nuestra función de comparación de productos tenían una probabilidad un 10 % mayor de realizar una conversión. Pasamos esta función a la parte superior de la página ¡y los pedidos aumentaron un 4 %!”*

Un equipo de optimización de sitios minoristas quería comprender mejor a los usuarios que interactuaban con una función de comparación de productos que habían lanzado recientemente. Utilizaron el panel de comparación de segmentos para comparar a los usuarios que utilizaron la función de comparación de productos con los demás usuarios del sitio. Rápidamente identificaron varias diferencias importantes, incluido el hecho de que estos usuarios tenían un 10% más de probabilidad de comprar un producto. El equipo de optimización del sitio decidió destacar la función de comparación de productos colocándola en la parte superior de la página.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visitante donde existe un evento personalizado (herramienta de comparación de precios) | Todos los demás |

## Caso de uso 3: comparar visitantes del sitio de noticias con otros visitantes de sección del sitio

> *“Descubrimos que los visitantes de nuestra sección de noticias veían dos veces más anuncios en vídeo, así que añadimos más opciones de vídeo en esa sección. ¡Experimentamos un aumento del 7 % en el visionado de anuncios en vídeo!”*

Una importante empresa de publicación de medios estudió las formas de mejorar la participación del público en el contenido en su sección de noticias. Crearon un segmento de visitantes que habían visitado la sección del sitio de noticias para comprender mejor a la audiencia. Inmediatamente encontraron que estos usuarios tenían el doble de probabilidades de ver anuncios en vídeo que los visitantes de cualquier otra sección del sitio. El equipo de video reunió una sección de video recomendada en su carril lateral de noticias y logró un aumento del 7% en los anuncios de video vistos.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visitante donde Sección del sitio es igual a 'Noticias' | Todos los demás |

## Caso de uso 4: comparar visitantes de búsqueda paga con otros

> *“Los visitantes que llegaban a nuestro sitio desde motores de búsqueda tenían tres veces más probabilidades de mejorar una compra que todos los demás. We upped our spend on specific keywords as a result and achieved a 56% increase in up-sells."*

Una gran empresa de servicios B2B quería entender el tipo de tráfico que llegaba a su sitio a partir de palabras clave de búsqueda pagadas. La búsqueda paga no resultó en muchas conversiones directamente, y el ejecutivo de mercadotecnia consideró reducir el presupuesto para ella. El equipo de mercadotecnia creó un segmento de visitantes que ingresaron al sitio mediante una búsqueda paga y lo comparó con todos los demás visitantes mediante el panel de comparación de segmentos. Descubrieron que, aunque estos visitantes no tenían la misma probabilidad de convertirse directamente, tenían tres veces más probabilidades de aumentar sus ventas en un servicio comprado anteriormente. El equipo de mercadotecnia centró su presupuesto solamente en las palabras clave relacionadas con la venta vertical y vio un aumento del 56% en las ventas de servicios.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visitante donde Tipo de referente es igual a búsqueda paga | Todos los demás |

## Caso de uso 5: comparar los compradores de Fitbit con los demás

> *“Descubrimos que las personas que compraban Fitbits tenían 6 veces más probabilidad de recibir un mensaje 'sin existencias' que todos los demás, por lo que encargamos rápidamente más Fitbits para evitar quedarnos sin stock”.*

Un importante minorista en línea estaba interesado en saber cómo uno de los productos de vacaciones más populares, Fitbit, estaba vendiendo y qué hacía que los compradores de Fitbit fueran únicos entre otros clientes. Utilizando la comparación de segmentos, descubrieron que los usuarios que compraban Fitbits tenían 6 veces más probabilidades de recibir un mensaje "sin existencias" que cualquier otro cliente. Después de un análisis más profundo, el equipo de mercadotecnia dirigió a estos visitantes a sus tiendas de ladrillos y morteros mientras esperaban a que su departamento de compras solicitara más Fitbits para enviar. Como resultado, el minorista evitó más mensajes "fuera de existencias" y satisfizo más su demanda navideña.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visitante donde existen pedidos y dimensión personalizada Marca es igual a FitBit | Todos los demás |
