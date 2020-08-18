---
description: Los segmentos le permiten identificar subconjuntos de visitantes basándose en sus características o en las interacciones con el sitio web. Los segmentos están diseñados como análisis de audiencia codificados que puede crear para sus necesidades específicas, y luego verificar, editar y compartir con otros integrantes del equipo, o bien utilizar en otros productos de Adobe y capacidades de Analytics.
title: Acerca de los segmentos y los contenedores
topic: Segments
uuid: e8b1edd1-5d6c-4213-994b-fed789ad30a4
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '3709'
ht-degree: 100%

---


# Acerca de los segmentos y los contenedores

Los segmentos le permiten identificar subconjuntos de visitantes basándose en sus características o en las interacciones con el sitio web. Los segmentos están diseñados como análisis de audiencia codificados que puede crear para sus necesidades específicas, y luego verificar, editar y compartir con otros integrantes del equipo, o bien utilizar en otros productos de Adobe y capacidades de Analytics.

Los segmentos se basan en una jerarquía de niveles de [!UICONTROL visitante], [!UICONTROL visita] y [!UICONTROL visita individual] usando un modelo de contenedor anidado. Los contenedores anidados le permiten definir los atributos y las acciones del visitante basándose en las reglas entre los contenedores y dentro de ellos. Los segmentos de Analytics pueden generarse, aprobarse, compartirse, guardarse y ejecutarse en varios productos y capacidades en [!DNL Adobe Experience Cloud]. Los segmentos pueden generarse a partir de un informe, integrarse en un informe de panel o marcarse como favoritos para acceder rápidamente a ellos.

Puede crear y guardar segmentos en el Generador de segmentos, o bien crearlos a partir de un informe de abandonos (en un [!DNL ad hoc analysis]). También puede utilizar y ampliar segmentos pregenerados basados en reglas específicas entre contenedores anidados, lo que le permite filtrar los resultados y aplicarlos a informes. Además, los segmentos pueden utilizarse juntos como [segmentos apilados](/help/components/segmentation/segmentation-workflow/seg-workflow.md).

## Segmentos {#section_CC4EBA2A6CCB4F8BBB8437052A880657}

Los segmentos identifican quiénes son sus visitantes (país, sexo, cafetería), qué dispositivos y servicios utilizan (explorador, motor de búsqueda, dispositivo móvil), desde dónde navegan (motor de búsqueda, página de salida anterior, búsqueda natural) y mucho más.

![](assets/seg.png)

Los segmentos pueden basarse en los siguientes valores:

* Visitantes en función de sus atributos: tipo de navegador, dispositivo, número de visitas, país, género.
* Visitantes en función de interacciones: campañas, búsqueda de palabras clave o motor de búsqueda.
* Visitantes en función de salidas y entradas: visitantes de Facebook, una página de aterrizaje definida o un dominio de referencia.
* Visitantes en función de variables personalizadas: campo de formulario, categorías definidas o ID de cliente.

Cuando genera segmentos de audiencia en el Generador de segmentos, define condiciones utilizando los operadores [!UICONTROL AND] y [!UICONTROL OR] entre los contenedores.

![](assets/standard_segment_containers.png)

Este tipo de segmentos filtra conjuntos de datos en función de características unidas con los operadores [!UICONTROL AND] y [!UICONTROL OR].

## Segmentos secuenciales {#section_EE5B14287FC44E0B96E77679A2438948}

Los segmentos secuenciales le permiten identificar a los visitantes en función de la navegación y las vistas de página en su sitio, lo que proporciona un segmento de acciones e interacciones definidas. Los segmentos secuenciales le ayudan a identificar qué le gusta a un visitante, así como lo que evita. Cuando se generan segmentos secuenciales, se utiliza el operador [!UICONTROL THEN] para definir y ordenar la navegación del visitante.

![](assets/sequential_seg.png)

| Visita uno | Visita dos | Visita tres |
|---|---|---|
| En la primera visita, el visitante accedió a la página de aterrizaje principal (A), excluyó la página de campaña (B) y después vio la página del producto (C). | En la segunda visita, el visitante volvió a acceder a la página de aterrizaje principal (A), excluyó la página de campaña (B) y vio de nuevo la página del producto (C), para acceder a continuación a una nueva página (D). | En la tercera visita, el visitante accedió y siguió la misma ruta que en la primera y la segunda visita, y después excluyó la página F para ir directamente a una página de producto dirigida. |

Los segmentos secuenciales pueden basarse en los siguientes valores de visitas individuales:

* Visitantes en función de una secuencia de visitas individuales de páginas: vistas de página en una sola visita, vistas de página en visitas separadas o visitas que excluyeron vistas de página.
* Visitantes en función del tiempo después y entre las vistas de página: después de un límite de tiempo, entre visitas individuales o después de un evento.

![](assets/sequential_segmentation_containers_view.png)

Un segmento secuencial filtra conjuntos de datos en función de las acciones del usuario usando el operador [!UICONTROL THEN].

## Vídeo explicativo {#section_89D6184890AF4086A8056BFBB0B68C29}

En este vídeo de YouTube se proporciona una breve descripción sobre qué son los contenedores de segmento y cómo se utilizan.

| Nombre del vídeo | Vínculo de vídeo |
|---|---|
| Contenedores de segmento | [Contenedores de segmento en Adobe Analytics](https://www.youtube.com/watch?v=A513j-ej0oc&amp;index=2&amp;list=PL2tCx83mn7GtHqZicFTa--aE6d02BvvTd) |

## Acerca de los contenedores {#section_AF2A28BE92474DB386AE85743C71B2D6}

Un segmento establece las condiciones necesarias para filtrar a un visitante en función de sus atributos o de las interacciones con su sitio. Para establecer las condiciones en un segmento, debe fijar las reglas que filtran a los visitantes según sus características de visitante y/o rasgos de navegación. Si desea desglosar todavía más los datos de los visitantes, puede filtrar basándose en las visitas específicas y/o las visitas individuales de cada visitante para ver una página. El Generador de segmentos proporciona una sencilla arquitectura para crear estos subconjuntos y aplicar reglas como contenedores anidados y jerárquicos de visitante, visita y visita individual.

La arquitectura de contenedor empleada en el Generador de segmentos define el **[!UICONTROL visitante]** como el contenedor exterior, que incluye datos globales específicos del visitante en las visitas y vistas de páginas. Un contenedor de **[!UICONTROL visita]** anidado le permite establecer reglas para desglosar los datos del visitante en función de las visitas, y un contenedor de **[!UICONTROL visita individual]** anidado le permite desglosar la información del visitante según las vistas de página individuales. Cada contenedor le permite realizar informes basados en el historial del visitante o en las interacciones detalladas por visitas, o bien desglosar las visitas individuales.

![](assets/sequential_segmentation_container_hierarchy.png)

**Contenedor de visitante**

El contenedor de visitante incluye todas las visitas y vistas de página de los visitantes en un período de tiempo específico. Un segmento en el nivel de visitante devuelve la página que cumple la condición, además de todas las demás páginas visitadas por el visitante (restringidas únicamente por los intervalos de fechas definidos). Al ser el contenedor definido con mayor amplitud, los informes generados en el nivel del contenedor de visitante devuelven vistas de página de todas las visitas, lo que le permite generar análisis multivisitas. Por tanto, el contenedor de visitante es el más susceptible de cambiar en función de intervalos de fechas definidos.

Los contenedores de visitante pueden incluir valores basados en el historial general de un visitante:

* Días antes de la primera compra
* Página de entrada original
* Dominios de referencia originales

**Contenedor de visita**

El contenedor de visita le permite identificar interacciones de páginas, campañas o conversiones para una sesión web específica. El contenedor de visita es el contenedor más utilizado, ya que captura los comportamientos de la sesión de visita al completo cuando se cumple la regla y le permite definir qué visitas desea incluir o excluir al generar y aplicar un segmento. Asimismo, le ayuda a encontrar una respuesta a una pregunta como: ¿Cuántos visitantes vieron la sección de noticias y deportes en la misma visita? O: ¿Qué páginas se atribuyeron a una conversión satisfactoria en una venta?

Los contenedores de visita incluyen valores basados en la incidencia por visita:

* Número de visita
* Página de entrada
* Frecuencia de retorno
* Métricas de participación
* Métricas asignadas linealmente

**Contenedor de visita individual**

El contenedor de visita individual define qué visitas individuales de página desea incluir o excluir de un segmento. Es el contenedor más limitado del que dispone para identificar clics específicos y vistas de página cuando una condición sea verdadera, lo que le permite ver un código de seguimiento único, o aislar un comportamiento en una sección en concreto de su sitio. También podría interesarle localizar un valor específico cuando se produzca una acción, como el canal de marketing cuando se realice un pedido.

Los contenedores de visitas individuales incluyen valores basados en el desglose de una sola página:

* Productos
* props de lista
* eVars de lista
* eVars de comercialización (en el contexto de eventos)

   >[!NOTE]
   >
   >Si utiliza este contenedor en un valor que persiste, como una eVar, extraerá todas las visitas individuales en las que dicho valor persista. En el caso de un código de seguimiento que expire tras una semana, ese valor podría persistir en varias visitas.

**Contenedor de grupo lógico**

El contenedor de grupo lógico le permite proporcionar un contenedor separado dentro de las reglas de segmento para filtrar entidades no basadas en jerarquía. Por ejemplo, es posible que necesite proporcionar un contenedor anidado dentro del segmento que filtra en función del visitante. Este tipo de lógica requiere interrumpir la jerarquía (puesto que usted ya tiene un contenedor de visitante de nivel superior) para filtrar únicamente para visitantes seleccionados. Puede hacerse con el contenedor de grupo lógico. Consulte [Ejemplos de grupos lógicos](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md) para obtener más información.

## Anidado de contenedores {#section_7FDF47B3C6A94C38AE40D3559AFFAF70}

Al crear contenedores de segmentos dentro de otros contenedores, básicamente está creando un segmento dentro de otro segmento. La siguiente lógica se utiliza con los contenedores anidados:

1. Determinar qué datos se incluyen utilizando el contenedor exterior. Los datos que no coincidan con esta regla exterior se descartarán en el informe segmentado.
1. Aplicar la regla anidada a los demás datos. La regla anidada no se aplica a ninguna visita individual que la primera regla haya rechazado.
1. Repetir hasta que se hayan calculado todas las reglas de los contenedores anidados. Los datos restantes se incluyen entonces en el informe resultante.

Puede utilizar el anidado entre contenedores, así como entre las reglas dentro de un contenedor. A continuación se indica lo que puede anidar en cada contenedor:

| Nombre de contenedor | Qué puede anidar dentro |
|---|---|
| Visita individual | Solo eventos |
| Visita | Contenedor de visita individual, eventos |
| Visitante | Contenedor de visita, contenedor de visita individual, eventos |
| grupo lógico | Contenedor de visitante, contenedor de visita, contenedor de visita individual |

**Incluir varios contenedores dentro de una sola definición**

Si incluye varios segmentos en un nuevo segmento compuesto puede refinar los datos todavía más. El hecho de arrastrar juntos dos segmentos existentes funciona como una instrucción “OR” al filtrar los visitantes. Todos los contenedores del lienzo se revisan comparándolos con todos los datos, y todos los datos que coincidan con alguno de los contenedores se incluirán en el informe.

Por ejemplo, si arrastra un contenedor de visita donde País = Estados Unidos con un contenedor de visita donde Pedido = Verdadero

```
Country = United States + Order = True
```

generará un segmento que se comportará siguiendo este orden:

1. El segmento buscará primero entre todos los datos e identificará a los visitantes de Estados Unidos.
1. A continuación, el segmento volverá a buscar entre todos los datos para comprobar si algún visitante realizó un pedido.
1. Ambos conjuntos de datos se aplicarán entonces al informe.

## Contenedores para segmentos secuenciales {#section_324AF503F51A4A62806151FE440F3B2E}

La segmentación secuencial emplea los mismos contenedores básicos, incluidos el de [!UICONTROL visitantes], [!UICONTROL visitas] y [!UICONTROL visitas individuales] (así como las vistas de página u otras dimensiones) anidados jerárquicamente.

![](assets/nesting_container.png)

[!UICONTROL Visitantes] constituye el contenedor de orden superior en la segmentación secuencial, con [!UICONTROL visitas] contenidas dentro del contenedor de [!UICONTROL visitantes] y [!UICONTROL visitas individuales] contenidas dentro de los contenedores de [!UICONTROL visitantes] o [!UICONTROL visitas]. Esta [jerarquía de contenedores](/help/components/segmentation/seg-overview.md#section_7FDF47B3C6A94C38AE40D3559AFFAF70) debe mantenerse para generar segmentos secuenciales bien ordenados.

**Para generar segmentos secuenciales**, se anidan los contenedores y se une la lógica secuencial usando el operador [!UICONTROL THEN], que requiere que cada contenedor sea verdadero en función de la secuencia del visitante.

![](assets/sequential_segmentation_nesting_3.png)

La única excepción a esta jerarquía de contenedores es al usar el [contenedor de grupo lógico](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md). El contenedor de [!UICONTROL grupo lógico] le permite anidar una visita individual dentro de un contenedor sin orden para capturar eventos y dimensiones pero fuera de un orden secuencial.

![](assets/logic_group_hierarchy.png)

## Informes basados en datos de contenedores {#concept_BE822C12F87C4F07B7147D80BEFBAB87}

Los contenedores le permiten filtrar datos diferentes basados en valores de informes al desglosar los segmentos y aplicarlos a los informes.

Los datos capturados en cada nivel de la jerarquía de contenedores visitante > visita > visita individual afectan a cómo genera sus segmentos. Si toma el mismo segmento aplicado al mismo informe utilizando el mismo conjunto de datos, obtendrá valores diferentes en función del contenedor a partir del cual genere el informe. Los factores como el nivel al que se realiza el informe del contenedor y la persistencia de los valores en las visitas individuales pueden suponer grandes cambios en la precisión de sus informes.

## Principios básicos de los datos de contenedor {#section_9576D970F912450191AFB5B83F7F1656}

Por ejemplo, el visitante que se muestra a continuación visitó un sitio en la primera visita, aterrizó en la página de inicio y, a continuación, visitó otras tres páginas y convirtió la visita en una venta. En una visita aparte, el visitante llegó esta vez a través de la página del producto, se dirigió a la página de inicio, volvió atrás a la página del producto y, por último, cerró la sesión tras echar un vistazo a los gorros de invierno. En función de los datos capturados para cada contenedor del segmento, se mostrarán en el informe valores diferentes.

El segmento *Página es igual a Abrigo de invierno* que se muestra a continuación se aplica al **informe de páginas**.

![](assets/page_winter_coat.png)

En función del contenedor seleccionado, el informe muestra resultados diferentes.

![](assets/container_overview.png)

**Informes desde el contenedor de visita individual**

Cuando esta condición se encuentre dentro de un contenedor de visita individual, el informe solo enumerará páginas donde *Página = Abrigos de invierno* sea un valor verdadero. Dado que una sola página coincide con esta condición en un contenedor de una sola página, únicamente se muestra la página Abrigos de invierno.

![](assets/container_overview_PV.png)

Al realizar informes desde el contenedor de visita individual, podrá comprobar cómo la realización de informes desde diferentes contenedores afecta a los valores generales de los informes. Cuando visualice el informe del segmento, fíjese en que las vistas de página equivalen aproximadamente a las visitas (cerca de 2.000 visitantes vieron páginas duplicadas en una visita, lo que se suma al número total de vistas de página), y los visitantes únicos equivalen aproximadamente al número de visitas (cerca de 2.000 visitantes únicos realizaron una visita más de una vez).

![](assets/container_report_PV.png)

>[!IMPORTANT]
>
>Independientemente de cómo visualice los datos (desde el contenedor de visita individual, visita o visitante), todos tienen el mismo número de visitantes, 63 541 en este ejemplo. Independientemente de cómo genere el informe, la condición de visitante inicial —los visitantes que vieron la página Abrigos de invierno— permanece intacta. Es el subconjunto de datos desde el que realiza el informe en los diferentes niveles.

**Informes desde el contenedor de visita**

Si esta misma condición se encuentra dentro de un contenedor de visita, entonces el informe enumera todas las páginas de la visita donde *Página es igual a Abrigos de invierno* sea un valor verdadero. Filtra la página Abrigos de invierno, pero también captura las demás páginas de la visita donde la condición sea verdadera. Dado que el visitante también visitó las páginas de inicio, del producto y de compra en la visita en la que se cumplió la condición, estas páginas adicionales se enumeran en el informe cuando este se realiza utilizando los datos del contenedor de visitante.

![](assets/container_overview_visit.png)

Si muestra valores de segmento desde el contenedor de visita, comprobará que el número de vistas de página ha aumentado considerablemente. Esto se debe a que al realizar informes desde el contenedor de visita se identifican todas las páginas que cumplieron las condiciones, además de todas las demás páginas visualizadas en la visita (con todas las vistas de página capturadas en cada contenedor de visita).

![](assets/container_report_Visit.png)

**Informes desde el contenedor de visitante**

Si esta misma condición se encuentra dentro de un contenedor de visitante, entonces el informe enumera todas las páginas visualizadas por el visitante donde *Página es igual a Abrigos de invierno* sea un valor verdadero. Eso significa que si un visitante vio la página Abrigos de invierno, se enumerarán todas las páginas del contenedor de visitante, incluidas las vistas de página de otras visitas. Por consiguiente, también se enumerarán en el informe otras páginas que no cumplen la condición, puesto que el visitante las vio previamente. En el informe se enumerarán todas las páginas del contenedor de visitante, incluso si son anteriores y no cumplen estrictamente las condiciones.

![](assets/container_overview_visitors.png)

Si muestra los segmentos desde el contenedor de visitante, verá que las vistas de página y las visitas han aumentado. Esto se debe a que a nivel de visitante, si este visitó la página Abrigos de invierno solo una vez (con lo que la condición es verdadera), se capturan todas las demás vistas de página y visitas de dicho visitante.

![](assets/container_report_Visitor.png)

Resumiendo: es fundamental entender cómo funciona la segmentación en diferentes desgloses de datos para interpretar los datos que devuelve.

## Informes basados en el contenedor {#section_D0604748F2794327B8C668617A31EC18}

Todos los desgloses de datos de segmentos tienen un alcance determinado al que estos se aplican. La mayoría de los desgloses de informes se basan en *vistas de página*. Sin embargo, muchos segmentos valiosos se basan en el contenedor de *visita* y, en menor medida, en el contenedor de *visitante*. Es importante entender los informes en función del alcance del contenedor.

Partiendo del ejemplo del segmento *Página = Abrigos de invierno* utilizado anteriormente, las cuestiones enumeradas a continuación definen otros aspectos del segmento en función de cómo se aplican los datos del contenedor y de cómo debería coincidir el alcance de los datos con el tipo de segmento.

**Contenedor de segmento basado en regla de segmento coincidente**

Si se aplica el contenedor de segmento según el alcance natural de los datos, se generan los resultados esperados cuando los elementos de línea coinciden con la regla del segmento.

* **Contenedor de visita individual donde Página es igual a &quot;Abrigo de invierno&quot;**: al visualizar un informe de *página* con este segmento, se devuelven solo los valores iguales a &quot;Abrigo de invierno&quot;. Todas las demás páginas se excluyen del informe.
* **Contenedor de visita donde Página de entrada es igual a &quot;Ropa de invierno&quot;**: al visualizar un *informe de página* de entrada con este segmento, se devuelve solo la segunda visita, ya que su página de entrada coincide con la regla del segmento.
* **Contenedor de visita, donde el número de visitas es igual a 1**: al visualizar una visita, todas las vistas de página desde la primera visita se incluyen en el informe, ya que coincide con la regla del segmento.

**Vistas de página a nivel de contenedor de visita**

Muchas reglas de segmentos identifican las vistas de página por visita. Cuando esto sucede, se aplica todo el contenedor de visitante si una sola visita individual coincide con la regla. Este informe de segmento resulta especialmente valioso, ya que las vistas de página en función de las visitas proporcionan información basada en las vistas de página por visita.

* **Contenedor de visita donde Página es igual a página &quot;Abrigo de invierno&quot;**: en un informe de página a nivel de contenedor de visitante se muestran todas las vistas de página de las visitas que incluyen una vista de la página &quot;Ropa de invierno&quot;. Si la página coincide con la regla del segmento, todas las vistas de página asociadas con esa visita se incluyen en el informe.
* **Contenedor de visita donde Página es igual a página de &quot;Inicio&quot;**: en un informe de página con este segmento solo se muestran los datos de la primera visita. Esto se debe a que en la segunda visita el visitante no vio una página de &quot;Inicio&quot;.
* **Contenedor de visitante donde Página es igual a &quot;Ropa de invierno&quot;**: en un informe de página, este segmento recupera todos los datos de las dos visitas, ya que en ambas el visitante vio la página &quot;Ropa de invierno&quot;.

**Contenedor de segmento que identifica Visitas individuales menores que vistas de página**

El uso de un segmento con un contenedor menor que el alcance del desglose devuelve datos inesperados. El uso de un desglose menor sigue extrayendo todas las visitas individuales de ese alcance de datos.

* **Contenedor de visita individual donde Página de entrada es igual a página de producto**: todas las páginas se asocian con la página de entrada de la visita, lo que acaba convirtiéndose en un desglose basado en la visita. El uso de este segmento no solo extrae la página de entrada &quot;Página de producto&quot;, sino también todas las visitas individuales de dicha visita.
* **Contenedor de visita individual donde Var de lista 1 contiene ValorA**: si varios valores se definieron en la misma visita individual como variables de lista, todos los valores de las variables se incluyen en el segmento. No hay forma de separar los valores que se producen en la misma vista de página, ya que el contenedor de visita individual es el contenedor de segmento más pequeño para desglosar las visitas individuales.
* **Contenedor de visita individual donde Página es igual a &quot;Compra&quot;**: si se usan las vistas de página como métrica, solo se mostrará la página de compra (tal y como cabría esperar). Si se usa un informe de participación en ingresos, todas las páginas de la primera visita recibirán 100 dólares, dado que la métrica de participación se basa en la visita.
* **Contenedor de visita individual donde Página es igual a &quot;Abrigo de invierno&quot;**: si se usan las vistas de página como métrica, solo se mostrará la página de abrigo de invierno (tal y como cabría esperar). Si se usa un informe de participación en ingresos, ninguna página recibirá saldo, ya que esta dimensión requiere una dimensión persistente. La vista de página que realizó la compra (la página de compra) no se incluye en el contenedor de visita individual, por lo que ningún elemento recibe participación en los ingresos. Sin embargo, si se ejecuta un informe desde el contenedor de visita, se incluirán todas las vistas de página de esa visita y se distribuirá la participación en los ingresos (100 dólares) entre todas las páginas vistas en la sesión.

## Persistencia a través de los contenedores {#concept_E579D72B1C644AE9A4C4EAF6B47A4DCB}

El hecho de filtrar por las dimensiones que persisten en una serie de páginas, como una eVar de campaña o una dimensión de referencia, afecta a los datos recopilados a nivel de contenedor, y debe entenderse bien para garantizar la precisión de los informes.

Los datos de los segmentos pueden variar en función de la persistencia de una dimensión o de una variable aplicada en las páginas seleccionadas. Algunas dimensiones, como la de página, proporcionan valores únicos a nivel de página y se filtran basándose en los datos del contenedor de visita individual. (Consulte el [ejemplo de Informes basados en datos de contenedores](/help/components/segmentation/seg-overview.md)). Otras dimensiones, como la de dominio de referencia, persisten en varias páginas de una visita. Algunas dimensiones o variables aplicadas, como la duración de la visita, permanecen en todo el historial del visitante.

![](assets/RefDomain_aol.png)

A diferencia de la dimensión de página, el valor del dominio de referencia se incluye en cada página de esta visita. Por ejemplo, el visitante mostrado más adelante llega a la página de inicio desde un sitio de referencia. Por consiguiente, todas las páginas de esa visita se asignan al mismo valor del dominio de referencia.

El segmento *Dominio de referencia es igual a aol.com* indicado a continuación se aplica al **informe de páginas**.

![](assets/container_overview_persist.png)

En una visita nueva, el visitante es remitido desde otro sitio. Por consiguiente, a todas las páginas de la nueva visita se les asigna el nuevo valor del dominio de referencia para cada vista de página.

**Informes desde el contenedor de visita individual**

Dado que a todas las vistas de página dentro de la misma visita se les asigna el mismo valor del dominio de referencia, los informes realizados a nivel del contenedor de visita individual donde *Dominio de referencia = &quot;aol.com&quot;* devuelven todas las páginas enumeradas en la siguiente tabla.

![](assets/container_overview_persist_Visit.png)

Según los datos del contenedor de visita individual, se realizaron 92.000 vistas de página en más de 33.000 visitas de más de 32.000 visitantes. De media, cada visita realizó tres vistas de página, y casi todas las visitas fueron de visitantes únicos.

![](assets/container_report_persist_PV.png)

**Informes desde el contenedor de visita**

Si esta misma condición se filtra en el contenedor de visita para un informe de páginas, entonces todas las páginas de la visita donde *Dominio de referencia = &quot;aol.com&quot;* tienen un valor verdadero. Dado que el valor del dominio de referencia se establece a nivel de visita, los informes realizados a nivel de vista de página y de visita son iguales.

![](assets/container_overview_persist_Visit.png)

En este ejemplo, como todas las páginas tienen el mismo valor de dominio de referencia basado en la visita, el informe a nivel de contenedor de visita es (casi) igual al informe del contenedor de vista de página (con una ligera desviación —de 98.234 a 98.248— debido a anomalías de los datos).

![](assets/container_report_persist_Visit.png)

**Informes desde el contenedor de visitante**

Desde el contenedor de visitante, el informe de página enumera todas las páginas vistas por cualquier visitante donde *Dominio de referencia es igual a &quot;aol.com&quot;* tenga un valor verdadero. Por consiguiente, si un visitante ha tenido *&quot;aol.com&quot;* como dominio de referencia en algún momento en el historial (dentro del período de tiempo definido), entonces se enumerarán todas las páginas del contenedor de visitante, incluidas las vistas de página de otras visitas. También se enumerarán en el informe las páginas que no cumplen la condición principal, ya que están incluidas en el contenedor de visitante. En el informe se enumerarán todas las páginas del contenedor de visitante, incluso si son anteriores y no cumplen estrictamente las condiciones.

En un informe de Dominio de referencia, *Dominio de referencia = &quot;aol.com&quot;* es verdadero en cuatro vistas de página, pero *Dominio de referencia = &quot;weather.com&quot;* es verdadero en las demás páginas que visitó el visitante. Desde el contenedor de visitante, obtendrá una lista de visitantes donde &quot;aol.com&quot; es verdadero, pero también le proporcionará las páginas donde el dominio de referencia es &quot;weather.com&quot;, que no es un valor que coincida con su solicitud inicial en el segmento.

![](assets/container_overview_persist_Visitor.png)

Cuando vea datos desde el contenedor de visitante, fíjese en que las vistas de página han aumentado considerablemente (de 98.248 a 112.925). Esto se debe a que se han enumerado todas las vistas de página del visitante, incluidas aquellas que tienen otros valores de dominio de referencia guardados a nivel de contenedor de visitante (así como las visitas adicionales de dicho visitante, lo que aumenta las visitas de 33.203 a 43.448).

![](assets/container_report_persist_Visitor.png)

Resumiendo:

* El contenedor de visita devuelve todas las páginas vistas en una visita donde al menos una página cumple los criterios. Así pues, si una página se ve solo en la visita 1 del día 1, entonces se incluyen en los datos todas las páginas vistas en toda la visita.
* Tenga cuidado cuando la condición con la que está segmentando se encuentra en una eVar o en otro tipo de variable persistente. Por ejemplo, podría utilizar la condición “donde Campaign contenga un correo electrónico”, que expira tras 7 días. Si la campaña se establece en la primera visita, persistirá durante 7 días más. De este modo se incluirá cada visita, incluso si la campaña solo estaba establecida en la primera visita. Las demás visitas también se incluirán (siempre y cuando se encuentren dentro del intervalo de fechas del informe). Si desea que los valores persistentes dejen de incluirse, utilice el evento “instancia de” o una variable Prop equivalente, si está disponible.

