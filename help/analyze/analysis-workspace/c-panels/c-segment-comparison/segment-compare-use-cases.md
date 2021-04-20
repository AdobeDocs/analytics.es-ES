---
title: Casos de uso de comparación de segmentos
description: Descubra casos de uso reales sobre cómo la utilización del panel de comparación de segmentos para obtener información sobre la estrategia de marketing.
keywords: IQ de segmento
feature: Panels
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 99%

---


# Casos de uso de IQ de segmentos

El panel de comparación de segmentos es una función muy utilizada en Analysis Workspace. Los clientes descubren con frecuencia nuevas formas de generar perspectivas. Los siguientes son varios casos de éxito.

## Caso de uso 1: Comparar implementaciones móviles y de escritorio

> *“Comparamos los impactos procedentes de un sitio con los del otro y encontramos enseguida varias inconsistencias de etiquetado. De este modo, evitamos problemas de datos antes del lanzamiento del producto”.*

Un gestor de producto a cargo de un sitio web móvil y un sitio web de escritorio recibió la tarea de comprobar que las etiquetas de ambos fueran coherentes. Para asegurarse de que no se había perdido nada importante, utilizó el panel de comparación de segmentos para comparar las visitas provenientes de su sitio de dispositivos móviles con las visitas provenientes de su sitio de escritorio. Observó que no había eventos de cierre de compra en el sitio web móvil y obtuvo las etiquetas correctas antes de que se lanzara el sitio móvil. Como resultado, el gestor de producto evitó el desastre de datos que hubiera supuesto que el sitio móvil no registrara ninguna conversión.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visita individual en el que Tipo de dispositivo móvil es igual a Teléfono móvil o Tablet | Todos los demás |

## Caso de uso 2: Comparar a los clientes que usan una determinada función con los que no lo hacen

> *“Comprobamos que los clientes que usaban nuestra función de comparación de productos tenían una probabilidad un 10 % mayor de realizar una conversión. Pasamos esta función a la parte superior de la página ¡y los pedidos aumentaron un 4 %!”*

El equipo de optimización de un sitio de venta quería comprender mejor a los usuarios que interactuaban con una función de comparación de productos que habían lanzado recientemente. Utilizaron el panel de comparación de segmentos para comparar a los usuarios que utilizaron la función de comparación de productos con los demás usuarios del sitio. Enseguida pudieron señalar varias diferencias importantes, incluido el hecho de que estos usuarios tenían una probabilidad un 10 % mayor de adquirir un producto. El equipo de optimización del sitio decidió destacar la función de comparación de productos colocándola en la parte superior de la página.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visitante en el que se produce un evento personalizado (herramienta de comparación de precios) | Todos los demás |

## Caso de uso 3: Comparar los visitantes a un sitio de noticias con los de otras secciones

> *“Descubrimos que los visitantes de nuestra sección de noticias veían dos veces más anuncios en vídeo, así que añadimos más opciones de vídeo en esa sección. ¡Experimentamos un aumento del 7 % en el visionado de anuncios en vídeo!”*

Una gran empresa de publicación multimedia buscaba un modo de mejorar la interacción de la audiencia con el contenido en su sección de noticias. Crearon un segmento de visitantes que habían visitado la sección de noticias para comprender mejor a la audiencia. Inmediatamente descubrieron que estos usuarios tenían el doble de probabilidades de ver anuncios en vídeo que los visitantes de cualquier otra sección del sitio. El equipo de vídeo montó una sección de vídeos recomendados en el carril lateral de la sección de noticias y logró un aumento del 7 % en el número de anuncios en vídeo vistos.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visitante donde Sección del sitio es igual a “Noticias” | Todos los demás |

## Caso de uso 4: Comparar los visitantes de búsquedas pagadas con todos los demás

> *“Los visitantes que llegaban a nuestro sitio desde motores de búsqueda tenían tres veces más probabilidades de mejorar una compra que todos los demás. Como resultado, aumentamos el gasto en palabras clave específicas y logramos un aumento del 56 % en la mejora de compras”.*

Una gran empresa de servicios B2B quería entender el tipo de tráfico que llegaba a su sitio a partir de palabras clave de búsqueda pagadas. Las búsquedas de pago no habían resultado en muchas conversiones directas y el responsable de marketing estaba pensando en reducir el presupuesto para ello. El equipo de marketing creó un segmento con los visitantes que llegaban al sitio desde búsquedas pagadas y lo comparó, usando el panel de comparación de segmentos, con el resto de visitantes. Descubrieron que, aunque era menos probable que estos visitantes supusieran una conversión directa, tenían tres veces más probabilidades de mejorar un servicio comprado con anterioridad. De este modo, el equipo de marketing pudo concentrar el presupuesto en palabras clave relacionadas con la mejora de ventas, lo que resultó en un aumento del 56 % en este aspecto.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visitante donde Tipo de referente es igual a Búsqueda de pago | Todos los demás |

## Caso de uso 5: Comparar a los compradores de Fitbit con todos los demás

> *“Descubrimos que las personas que compraban productos Fitbit tenían 6 veces más probabilidad de recibir un mensaje “sin existencias” sobre ellos que todos los demás, por lo que encargamos rápidamente más productos Fitbit para evitar quedarnos sin stock”.*

**Situación:** un importante minorista que vende en línea estaba interesado en saber qué tal se vendía uno de los productos estrella de las fiestas, Fitbit, y en qué se diferenciaban sus compradores de los demás clientes. El equipo de marketing solo tuvo que hacer clic derecho en el elemento “Fitbit” del informe de productos y ejecutar un rápido análisis con IQ de segmento. Lo que descubrieron fue que los usuarios que compraban Fitbits tenían 6 veces más probabilidad de encontrarse el mensaje “sin existencias” que cualquier otro cliente. Tras nuevos análisis, pudieron dirigir a estos visitantes a las tiendas físicas mientras ellos esperaban a que el departamento de compras realizara nuevos pedidos de Fitbits. Como resultado, el minorista evitó nuevos mensajes de falta de existencias y pudo satisfacer mejor la demanda de las fiestas.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenedor de visitante con pedidos realizados y una dimensión personalizada de Marca (FitBit) | Todos los demás |
