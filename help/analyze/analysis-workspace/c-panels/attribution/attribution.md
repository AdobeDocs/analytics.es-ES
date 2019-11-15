---
description: 'null'
title: Descripción general del panel Atribución
uuid: bb345642-4f45-4fb8-82d0-803248dd52ea
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Descripción general del panel Atribución

>[!IMPORTANT] El panel Atribución está disponible para todos los clientes en los SKU de Adobe Analytics Ultimate, Prime, Select y Foundation.

El panel de atribución es una función IQ [de](../../attribution-iq.md) atribución que permite agregar muchos tipos nuevos de modelos de atribución a tablas improvisadas, visualizaciones y métricas calculadas. Todos los modelos de atribución tienen dos componentes:

* **** Modelo de atribución: El modelo describe la distribución de las conversiones a las visitas individuales de un grupo. Por ejemplo, primer toque o último toque.
* **** Ventana retrospectiva de atribución: La ventana retrospectiva describe qué grupos de visitas se consideran para cada modelo. Por ejemplo: visita o visitante.

## Modelos de atribución

| Icono de IU | Modelo de atribución | Definición | Cuándo usar |
| --- | --- | --- | --- |
| ![Último toque](assets/last_touch1.png) | Último toque | Otorga un 100 % de crédito al punto de contacto que se produce más recientemente antes de la conversión. | El modelo de atribución más básico y común. Se utiliza con frecuencia para conversiones con un breve ciclo de consideración. Último toque lo utilizan comúnmente equipos que gestionan el marketing de búsqueda o que analizan palabras clave de búsqueda interna. |
| ![Primer toque](assets/first_touch.png) | Primer toque | Otorga un 100 % de crédito al punto de contacto que se ve por primera vez en la ventana retrospectiva de atribución. | Otro modelo de atribución común útil para analizar los canales de mercadotecnia con el fin de impulsar la toma de conciencia de la marca o la adquisición de clientes. Se utiliza con frecuencia en equipos de visualización o marketing social, pero también es ideal para evaluar la eficacia de las recomendaciones de productos en el sitio. |
| ![Mismo toque](assets/same_touch.png) | Mismo toque | Otorga un 100 % de crédito a la visita individual donde se produjo la conversión. Si un punto de contacto no se produce en la misma visita que una conversión, se agrupa en "Ninguno". | Un modelo útil para evaluar el contenido o la experiencia del usuario que se presentó inmediatamente en el momento de la conversión. Los equipos de diseño o productos suelen utilizar este modelo para evaluar la eficacia de una página en la que se produce la conversión. |
| ![Lineal](assets/linear.png) | Lineal | Otorga el mismo crédito a cada punto de contacto que se visualice y que conduzca a una conversión. | Útil para conversiones con ciclos de consideración más largos o experiencias de usuario que requieren una participación más frecuente de los clientes. A menudo lo utilizan los equipos que miden la efectividad de las notificaciones de aplicaciones móviles o con productos basados en suscripciones. |
| ![Forma de U](assets/u_shaped.png) | Forma de U | Otorga un 40 % de crédito a la primera interacción, un 40 % de crédito a la última interacción y divide el 20 % restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se proporciona un 100% de crédito. Para las conversiones con dos puntos táctiles, se concede un 50 % de crédito a ambos. | Un gran modelo para aquellos que valoran las interacciones que introdujeron o cerraron una conversión, pero que aún desean reconocer las interacciones de asistencia. La atribución en forma de U suele ser utilizada por equipos que adoptan un enfoque más equilibrado pero desean dar más crédito a los canales que han encontrado o cerrado una conversión. |
| ![Forma de J](assets/j_shaped.png) | Forma de J | Otorga un 60 % de crédito a la última interacción, un 20 % de crédito a la primera interacción y divide el 20 % restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se proporciona un 100% de crédito. Para las conversiones con dos puntos táctiles, se concede un 75% de crédito a la última interacción y un 25% de crédito a la primera. | Este modelo es ideal para aquellos que dan prioridad a los buscadores y cerradores, pero que quieren centrarse en cerrar interacciones. La atribución con forma J suele ser utilizada por equipos que adoptan un enfoque más equilibrado y desean dar más crédito a los canales que cierran una conversión. |
| ![Forma J inversa](assets/inverse_j.png) | J inversa | Otorga un 60 % de crédito al primer toque, un 20 % de crédito al último toque y divide el 20 % restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se proporciona un 100% de crédito. Para las conversiones con dos puntos táctiles, se concede un 75 % de crédito a la primera interacción y un 25 % de crédito a la última. | Este modelo es ideal para aquellos que dan prioridad a los buscadores y cerradores, pero que desean centrarse en encontrar interacciones. La atribución J inversa la utilizan los equipos que adoptan un enfoque más equilibrado y desean dar más crédito a los canales que iniciaron una conversión. |
| ![Personalizado](assets/custom.png) | Personalizado | Permite especificar los pesos que desea dar a los puntos de primer toque, los puntos de último toque y los puntos de contacto intermedios. Los valores especificados se normalizan al 100 % aunque los números personalizados especificados no se agreguen a 100. Para las conversiones con un solo punto de contacto, se proporciona un 100% de crédito. En el caso de interacciones con dos puntos táctiles, se omite el parámetro central. Los puntos de primer y último toque se normalizan al 100 % y el crédito se asigna en consecuencia. | Este modelo es perfecto para aquellos que quieren un control total sobre su modelo de atribución y tienen necesidades específicas que otros modelos de atribución no satisfacen. |
| ![Deterioro de tiempo](assets/time_decay.png) | Tiempo de decadencia | Sigue una decadencia exponencial con un parámetro de semivida personalizado, donde el valor predeterminado es 7 días. El peso de cada canal depende de la cantidad de tiempo que transcurra entre el inicio del punto de contacto y la conversión final. La fórmula utilizada para determinar el crédito es `2`<sup>`(-t/halflife)`</sup>, donde `t` es la cantidad de tiempo entre un punto de contacto y una conversión. A continuación, todos los puntos de contacto se normalizan al 100 %. | Ideal para equipos que periódicamente ejecutan anuncios en vídeo o que comercializan eventos con una fecha predeterminada. Cuanto más larga sea la conversión después de un evento de mercadotecnia, menor será el crédito. |
| ![Participación](assets/participation.png) | Participación | Otorga un 100% de crédito a todos los puntos de contacto únicos. El número total de conversiones está inflado en comparación con otros modelos de atribución. La participación anula la duplicación de los canales que se ven varias veces. | Excelente para comprender quién a menudo los clientes están expuestos a una interacción determinada. Las organizaciones de medios suelen utilizar este modelo para calcular la velocidad de contenido. Las organizaciones minoristas suelen utilizar este modelo para comprender qué partes del sitio son críticas para la conversión. |

## Ventanas de búsqueda

Una ventana retroactiva es la cantidad de tiempo que una conversión debe mirar hacia atrás para incluir puntos táctiles. Los modelos de atribución que dan más crédito a las primeras interacciones ven diferencias mayores al ver diferentes ventanas retroactivas.

* **** Ventana retrospectiva de visita: Revisa hasta el principio de una visita en la que se produjo una conversión. Las ventanas retroactivas de visitas son estrechas, ya que no miran más allá de la visita. Las ventanas retroactivas de visitas respetan la definición de visita modificada en los grupos de informes virtuales.
* **** Ventana retrospectiva del visitante: Busca todas las visitas hasta el primer día del mes del intervalo de fechas actual. Las ventanas retrospectivas de los visitantes son amplias, ya que pueden abarcar muchas visitas. Por ejemplo: si el intervalo de fechas del informe es del 15 de septiembre al 30 de septiembre, el intervalo de fechas retrospectivas del visitante incluye del 1 de septiembre al 30 de septiembre.

## Ejemplo

Consideremos el siguiente ejemplo:

1. El 15 de septiembre, un visitante llega a su sitio a través de un anuncio de búsqueda paga y luego lo abandona.
2. El 18 de setiembre, el visitante regresa a su sitio a través de un vínculo de medios sociales que obtuvo de un amigo. Agregan varios artículos al carro, pero no compran nada.
3. El 24 de septiembre, su equipo de mercadotecnia les enviará un correo electrónico con un cupón para algunos de los artículos del carro de compras. Aplican el cupón, pero visitan otros sitios para ver si hay otros cupones disponibles. Encuentran otro a través de un anuncio, y luego finalmente realizan una compra por $50.

Según la ventana retroactiva y el modelo de atribución, los canales reciben crédito diferente. Los siguientes son algunos ejemplos notables:

* Mediante el **primer toque** y una ventana **retrospectiva de** visita, la atribución solo observa la tercera visita. Entre el correo electrónico y la visualización, el correo electrónico fue el primero, por lo que el correo electrónico recibe un 100% de crédito por la compra de 50 dólares.
* Mediante el **primer toque** y una ventana **retrospectiva de** visitantes, la atribución observa las tres visitas. La búsqueda paga fue la primera, así que recibe un 100% de crédito por la compra de $50.
* Con la ventana **retrospectiva** lineal **y de** visita, el crédito se divide entre correo electrónico y visualización. Cada uno de estos canales recibe un crédito de 25 dólares.
* Con la ventana **retrospectiva** lineal **y de** visitante, el crédito se divide entre búsqueda paga, social, correo electrónico y visualización. Cada canal recibe un crédito de $12.50 por esta compra.
* Mediante la ventana retrospectiva con forma **** J y un **visitante**, el crédito se divide entre búsqueda paga, social, correo electrónico y visualización.
   * Se da crédito del 60% para mostrar, por $30.
   * 20% de crédito se da a la búsqueda paga, por $10.
   * El 20% restante se divide entre social y correo electrónico, lo que da 5 dólares a cada uno.
* Con **Tiempo de decadencia** y una ventana **de retrospectiva de** visitantes, el crédito se divide entre búsqueda paga, social, correo electrónico y visualización. Con la semivida de 7 días predeterminada:
   * Brecha de 0 días entre el punto de contacto de visualización y la conversión. `2`<sup>`(-0/7)`</sup> `= 1`
   * Diferencia de 0 días entre el punto de contacto del correo electrónico y la conversión. `2`<sup>`(-0/7)`</sup> `= 1`
   * Brecha de 6 días entre el punto de contacto social y la conversión. `2`<sup>`(-6/7)`</sup> `= 0.552`
   * Diferencia de 9 días entre el punto de contacto de búsqueda paga y la conversión. `2`<sup>`(-9/7)`</sup> `= 0.41`
   * La normalización de estos valores resulta en lo siguiente:
      * Mostrar: 33,8%, obteniendo $16,88
      * Correo electrónico: 33,8% obteniendo $16,88
      * Social: 18,6%, obteniendo $9,32
      * Búsqueda paga: 13,8%, obteniendo $6,92

> [!TIP] Otros eventos de conversión, como pedidos o eventos personalizados, también se dividen si el crédito pertenece a más de un canal. Por ejemplo, si dos canales contribuyen a un evento personalizado mediante un modelo de atribución lineal, ambos canales obtienen 0,5 del evento personalizado. Estas fracciones de evento se suman en todas las visitas y luego se redondean al entero más cercano para los informes.

## Uso de la atribución con canales de mercadotecnia

Cuando se introdujeron los canales de marketing por primera vez, solo incluyeron dimensiones de primer y último toque. Con estos modelos de atribución adicionales, ya no se necesitan dimensiones explícitas de primer/último toque. Adobe proporciona dimensiones genéricas del canal **de** mercadotecnia para que se puedan utilizar con el modelo de atribución que elija. Estas dimensiones genéricas de los canales de mercadotecnia se comportan de forma idéntica a las dimensiones del canal de último toque, pero tienen una etiqueta diferente para evitar confusiones al usar canales de mercadotecnia con un modelo de atribución diferente.

Dado que las dimensiones del canal de mercadotecnia dependen de una definición de visita tradicional (según lo definen sus reglas de procesamiento), su definición de visita no se puede cambiar mediante grupos de informes virtuales.

## Uso de la atribución con variables de varios valores

Algunas dimensiones en Analytics pueden contener varios valores en una sola visita. Algunos ejemplos comunes son las variables de lista y la variable products.

Cuando la atribución se aplica a visitas con varios valores, todos los valores de la misma visita obtienen el mismo crédito. Dado que muchos valores pueden recibir este crédito, el total del informe puede ser diferente a si se suma cada elemento de línea individual. El total del informe se anula la duplicación, mientras que cada valor de dimensión individual obtiene el crédito adecuado.

## Uso de la atribución con segmentación

La atribución siempre se ejecuta antes de la segmentación y ésta se ejecuta antes de que se apliquen los filtros de informe. Este concepto también se aplica a los grupos de informes virtuales que utilizan segmentos.

Por ejemplo, si crea un VRS con un segmento "Display Hits" aplicado, puede ver otros canales en una tabla utilizando algunos modelos de atribución.

![Grupo de informes virtuales de solo visualización](assets/vrs-aiq-example.png)
