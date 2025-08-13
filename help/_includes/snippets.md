---
source-git-commit: 4eea524bf95c9b6bc9ddc878c8c433bc1e60daee
workflow-type: tm+mt
source-wordcount: '2964'
ht-degree: 88%

---
# Fragmentos

## Report Builder heredado {#legacy-arb}

>[!IMPORTANT]
>
>[Report Builder](https://experienceleague.adobe.com/es/docs/analytics/analyze/report-builder/rb-overview) nuevo y optimizado se publicó el 16 de octubre de 2024. Es compatible con Mac, Windows y navegadores web.
>&#x200B;>Esta versión de complemento heredado de Report Builder sigue funcionando. Puede [convertir sus libros heredados](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks) al nuevo Report Builder.

## Anuncio del final de la vida útil de Reports & Analytics {#ra-eol}

>[!IMPORTANT]
>
>A partir del **17 de enero de 2024**, Adobe dejará de usar Reports &amp; Analytics y los informes y funciones que los acompañan. En ese momento, Reports &amp; Analytics y todos sus informes y programaciones dejaron de funcionar. Los informes, las visualizaciones y la tecnología subyacente que alimentan Reports &amp; Analytics ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de Reports &amp; Analytics están disponibles en Analysis Workspace. Para obtener más información, consulte [Usar plantillas](/help/analyze/analysis-workspace/templates/use-templates.md).
> 
>Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de Reports &amp; Analytics se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. Este aviso explica el proceso de finalización de la vida útil.
>
>Más información acerca del [Anuncio del final de la vida útil](https://www.adobe.com/go/analytics_rnaeol_es) de Reports &amp; Analytics.

## Opciones de ordenación de componentes {#components-sort-options}

| Opción | Función |
|---------|----------|
| [!UICONTROL **Recomendado**] | Ordena los componentes con los recomendados en la parte superior de la lista. Los componentes que usted u otras personas de su organización utilizan con más frecuencia y más recientemente aparecen en la parte superior de la lista. |
| [!UICONTROL **Alfabético**] | Ordena los componentes alfabéticamente. |
| [!UICONTROL **Categórica**] | Ordena los componentes según su tipo (dimensión, métrica, segmento, intervalo de fecha). |

{style="table-layout:auto"}

## Prueba limitada de fase de lanzamiento {#release-limited-testing}

>[!AVAILABILITY]
>
>La funcionalidad descrita en este artículo se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de lanzamiento de Analytics, consulte [Lanzamientos de funciones de Adobe Analytics](/help/release-notes/releases.md).

## Sección de prueba limitada de fase de lanzamiento {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funcionalidad descrita en esta sección se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de lanzamiento de Analytics, consulte [Lanzamientos de funciones de Adobe Analytics](/help/release-notes/releases.md).


## Aviso sobre complementos {#plug-in}

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el equipo de cuentas de Adobe de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.


## Solo disponible para clientes existentes {#available-existing-customers}

>[!AVAILABILITY]
>
>La funcionalidad descrita en esta sección solo está disponible para los clientes existentes que ya tienen una licencia para la funcionalidad. La funcionalidad ya no se ofrece como complemento adicional a los clientes existentes o nuevos.
>



## Modelos de atribución {#attribution-models-details}

Un modelo de atribución determina qué elementos de dimensión obtienen crédito por una métrica cuando se ven varios valores dentro de la ventana de retrospección de una métrica. Los modelos de atribución solo se aplican cuando hay varios elementos de dimensión establecidos dentro de la ventana de retrospección. Si solo se establece un elemento de dimensión, ese elemento de dimensión obtiene un 100 % de crédito, independientemente del modelo de atribución utilizado.

| Icono | Modelo de atribución | Definición |
| :---: | :--- | --- |
| ![Último contacto](/help/assets/icons/AttributeLastTouch.svg) | Último contacto | Otorga un 100 % de crédito al punto de contacto que se produce más recientemente antes de la conversión. Este modelo de atribución suele ser el valor predeterminado para cualquier métrica en la que no se especifique lo contrario en un modelo de atribución. Las organizaciones suelen utilizar este modelo en el que el tiempo de conversión es relativamente corto, como en el caso del análisis de palabras clave de búsqueda interna. |
| ![Primer contacto](/help/assets/icons/AttributeFirstTouch.svg) | Primer contacto | Otorga un 100 % de crédito al punto de contacto que se ve por primera vez en la ventana de retrospección de la atribución. Las organizaciones suelen utilizar este modelo para comprender la imagen de marca o la adquisición de clientes. |
| ![Lineal](/help/assets/icons/AttributeLinear.svg) | Lineal | Otorga el mismo crédito a cada uno de los puntos de contacto que se ven hasta llegar a una conversión. Resulta útil cuando los ciclos de conversión son más largos o requieren una participación del cliente más frecuente. Las organizaciones suelen utilizar este modelo de atribución para medir la efectividad de las notificaciones en aplicaciones móviles o con productos por suscripción. |
| ![Participación](/help/assets/icons/AttributeParticipation.svg) | Participación | Otorga un 100% de crédito a todos los puntos de contacto únicos. Dado que cada punto de contacto recibe un 100 % de crédito, los datos de métricas suelen sumar más del 100 %. Si un elemento de dimensión aparece varias veces por separado hasta llegar a una conversión, los valores se deduplican al 100 %. Este modelo de atribución es ideal en situaciones en las que desea comprender a qué puntos de contacto están más expuestos los clientes. Las organizaciones de medios suelen utilizar este modelo para calcular la velocidad de contenido. Los organizaciones minoristas suelen utilizar este modelo para comprender qué partes de sus sitios son esenciales para la conversión. |
| ![Mismo contacto](/help/assets/icons/AttributeSameTouch.svg) | Mismo contacto | Otorga un 100 % de crédito al mismo evento donde se realizó la conversión. Si un punto de contacto no sucede en el mismo evento que una conversión, se agrupa bajo “Ninguno”. Este modelo de atribución a veces se equipara a no tener ningún modelo de atribución. Resulta útil en situaciones en las que no desea valores de otros eventos que afecten a cómo una métrica da crédito a los elementos de dimensión. Los equipos de producto o diseño a menudo pueden utilizar este modelo para tener acceso a la efectividad de una página en la que tiene lugar la conversión. |
| ![Forma de U](/help/assets/icons/AttributeUShaped.svg) | Forma de U | Otorga un 40% de crédito a la primera interacción, un 40% de crédito a la última interacción y divide el 20% restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. Para las conversiones con dos puntos de contacto, se otorga un 50 % de crédito a ambos. Este modelo de atribución se utiliza mejor en situaciones en las que se valora más la primera y la última interacción, pero no se desea descartar por completo las interacciones adicionales intermedias. |
| ![Curva J](/help/assets/icons/AttributeJCurve.svg) | Curva J | Otorga un 60% de crédito a la última interacción, un 20% de crédito a la primera interacción y divide el 20% restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. Para las conversiones con dos puntos de contacto, se otorga un 75 % de crédito a la última interacción y un 25 % de crédito a la primera. Este modelo de atribución, que es similar a la Forma U, favorece la primera y la última interacción, pero favorece más intensamente la última interacción. |
| ![J inversa](/help/assets/icons/AttributeInverseJ.svg) | J inversa | Otorga un 60% de crédito al primer contacto, un 20% al último contacto y divide el 20% restante en cualquier punto de contacto intermedio. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. Para las conversiones con dos puntos de contacto, se otorga un 75 % de crédito a la primera interacción y un 25 % de crédito a la última. Este modelo de atribución, que es similar a la Forma J, favorece la primera y la última interacción, pero favorece más intensamente la primera interacción. |
| ![Deterioro de tiempo](/help/assets/icons/AttributeTimeDecay.svg) | Declive temporal | Sigue un declive exponencial con un parámetro de semivida personalizado, con un valor predeterminado de 7 días. El valor de cada canal depende de la cantidad de tiempo que transcurra entre el inicio del punto de contacto y la conversión final. La fórmula utilizada para determinar el crédito es `2^(-t/halflife)`, donde `t` es la cantidad de tiempo entre un punto de contacto y una conversión. A continuación, todos los puntos de contacto se normalizan al 100 %. Es ideal en las situaciones en las que desea medir la atribución con respecto a un evento específico e importante. Cuanto más tiempo tarde en suceder una conversión después de este evento, menos crédito se le atribuirá. |
| ![Personalizado](/help/assets/icons/AttributeCustom.svg) | Personalizado | Le permite especificar los valores que desea asignar al primer punto de contacto, al último punto de contacto y a cualquier punto de contacto intermedio. Los valores especificados se normalizan al 100% incluso si los números introducidos no suman 100. Para las conversiones con un solo punto de contacto, se otorga un 100% de crédito. En el caso de interacciones con dos puntos de contacto, se omite el parámetro central. A continuación, los primeros y últimos puntos de contacto se normalizan al 100 % y se asigna el crédito correspondiente. Este modelo es perfecto para los analistas que quieren tener un control total sobre su modelo de atribución y tienen necesidades específicas que otros modelos de atribución no satisfacen. |
| ![Algorítmico](/help/assets/icons/AttributeAlgorithmic.svg) | Algorítmico | Utiliza técnicas estadísticas para determinar de manera dinámica la asignación óptima de crédito para la métrica seleccionada. El algoritmo utilizado para la atribución se basa en el dividendo de Harsanyi de la teoría de juegos cooperativa. El dividendo de Harsanyi es una generalización de la solución del valor de Shapley (llamada así por Lloyd Shapley, economista ganador del Premio Nobel) para distribuir crédito entre los jugadores en un juego con contribuciones desiguales al resultado.<br>En un nivel superior, la atribución se calcula como una coalición de actores a los que debe distribuirse equitativamente un excedente. La distribución del superávit de cada coalición se determina de acuerdo con el superávit creado previamente por cada subcoalición (o los elementos de dimensión que participaban antes) de manera recursiva. Para obtener más información, consulte los artículos originales de John Harsanyi y Lloyd Shapley: <br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). Un modelo de negociación simplificado para un juego cooperativo de n personas. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Contenedor de atribución {#attribution-container}

Un contenedor de atribución define el ámbito deseado para la atribución. Las opciones posibles son las siguientes:

* **Visita**: busca conversiones desde el ámbito del contenedor de visita.
* **Visitante**: busca conversiones desde el ámbito del contenedor de visitante.

## Ventana de retrospección de atribución {#attribution-lookback-window}

Una ventana retrospectiva es la cantidad de tiempo que una conversión debe devolverse en el tiempo para incluir los puntos de contacto. Si un elemento de dimensión se establece fuera de la ventana de retrospección, el valor no se incluye en ningún cálculo de atribución.

* **14 días**: se remonta hasta 14 días desde que se realizó la conversión.
* **30 días**: se remonta hasta 30 días desde que se realizó la conversión.
* **60 días**: se remonta hasta 60 días desde que se realizó la conversión.
* **90 días**: se remonta hasta 90 días desde que se realizó la conversión.
* **Tiempo personalizado:** permite establecer una ventana de retrospección personalizada desde el momento en que se realizó una conversión. Puede especificar el número de minutos, horas, días, semanas, meses o trimestres. Por ejemplo, si se realizó una conversión el 20 de febrero, una ventana de retrospección de cinco días evaluaría todos los puntos de contacto de la dimensión del 15 al 20 de febrero en el modelo de atribución.

## Ejemplo de atribución {#attribution-example}

Consideremos el siguiente ejemplo:

1. El 15 de septiembre, un visitante llega a su sitio a través de un anuncio de búsqueda de pago y luego lo abandona.
1. El 18 de setiembre, el visitante regresa a su sitio a través de un vínculo de medios sociales que obtuvo de un amigo. Agregan varios artículos al carro, pero no compran nada.
1. El 24 de septiembre, su equipo de marketing les enviará un correo electrónico con un cupón para algunos de los artículos del carrito. Aplican el cupón, pero visitan otros sitios para ver si hay otros cupones disponibles. Encontraron otro a través de un anuncio y finalmente hicieron una compra por valor de 50 dólares.

Según el modelo de atribución, el contenedor y los canales reciben un crédito diferente. Consulte la siguiente tabla para ver ejemplos:

| Modelo | Contenedor | Período de retroactividad | Explicación |
|---|---|---|---|
| Primer contacto | Visita | 30 días | La atribución solo examina la tercera visita. Entre el correo electrónico y la visualización, el correo electrónico fue lo primero, por lo que este recibe el 100 % del crédito por la compra de 50 USD. |
| Primer contacto | Visitante | 30 días | La atribución examina las tres visitas. La búsqueda de pago fue la primera, así que recibe el 100 % del crédito por la compra de 50 USD. |
| Lineal | Visita | 30 días | El crédito se divide entre el correo electrónico y la visualización. Cada uno de estos canales recibe un crédito de 25 USD. |
| Lineal | Visitante | 30 días | El crédito se divide entre la búsqueda de pago, el medio social, el correo electrónico y la visualización. Cada canal recibe un crédito de 12,50 USD por esta compra. |
| Con forma de J | Visitante | 30 días | El crédito se divide entre la búsqueda de pago, el medio social, el correo electrónico y la visualización.<ul><li>Se otorga un crédito del 60 % a la visualización, es decir, 30 dólares.</li><li>El 20 % de crédito se asigna a la búsqueda de pago, 10 dólares en este caso.</li><li>El 20% restante se divide entre el medio social y el correo electrónico, lo que otorga 5 dólares a cada uno.</li></ul> |
| Declive temporal | Visitante | 30 días | <ul><li>Diferencia de 0 días entre el punto de contacto de visualización y la conversión. `2^(-0/7) = 1`</li><li>Diferencia de 0 días entre el punto de contacto del correo electrónico y la conversión. `2^(-0/7) = 1`</li><li>Diferencia de 6 días entre el punto de contacto social y la conversión. `2^(-6/7) = 0.552`</li><li>Diferencia de 9 días entre el punto de contacto de búsqueda de pago y la conversión. `2^(-9/7) = 0.41`</li>La normalización de estos valores resulta en lo siguiente:<ul><li>Visualización: 33,8 %, 16,88 dólares</li><li>Correo electrónico: 33,8 % 16,88 dólares</li><li>Medio social: 18,6 %, 9,32 dólares</li><li>Búsqueda de pago: 13,8 %, 6,92 dólares</li></ul></li></ul> |

Los eventos de conversión que generalmente tienen números enteros se dividen si el crédito pertenece a más de un canal. Por ejemplo, si dos canales contribuyen a un pedido mediante un modelo de atribución lineal, ambos canales obtienen 0,5 de dicho pedido. Estas métricas parciales se suman entre todas las visitas y luego se redondean al entero más cercano para los informes.

## Comparaciones de visualizaciones de recorridos {#journey-visualization-comparisons}

Se han diseñado varias visualizaciones en Customer Journey Analytics para analizar los recorridos que proporcione a sus clientes.

Utilice la siguiente información para elegir la visualización que mejor se adapte a sus necesidades.

| Función | Lienzo de recorrido | Visita en orden previsto | Flujo |
|---------|----------|---------|---------|
| **Secuencia predefinida de páginas** | Sí</br>Combina análisis predefinidos y exploratorios. La ruta final se utiliza cuando se utilizan nodos predefinidos en la ruta (los visitantes se cuentan siempre y cuando se desplacen finalmente de un nodo predefinido al otro). También se pueden mostrar los siguientes nodos inmediatos (no posibles). | Sí</br>La ruta puede ser una ruta final o puede restringirse al siguiente punto de contacto | No |
| **Secuencia exploratoria de páginas (análisis ad hoc)** | Sí</br>Combina análisis predefinidos y exploratorios. La ruta final se utiliza cuando se utilizan nodos predefinidos en la ruta (los visitantes se cuentan siempre y cuando se desplacen finalmente de un nodo predefinido al otro). También se pueden mostrar los siguientes nodos inmediatos (no posibles). | Limitado</br>Permite hacer clic con el botón derecho del ratón y ver las visitas en el orden previsto en una tabla de forma libre. | Sí</br>Solo análisis exploratorio. Siempre dentro de una instancia de dimensión entre nodos. Esto significa que cada nodo muestra el siguiente punto de contacto inmediato (no final) a lo largo de la ruta. |
| **Muestra dónde se retiraron las personas (abandonaron) y continuaron (fracasaron)** | Sí</br>Muestra recorridos predefinidos y exploratorios | Sí</br>Muestra los recorridos predefinidos | Sí</br>Muestra los recorridos exploratorios |
| **Recorridos lineales** | Sí | Sí | No |
| **Recorridos no lineales con varios puntos de entrada y rutas** | Sí | No | Sí |
| **Métrica principal** | Cualquier métrica, incluidas las métricas calculadas | Solo sesión o persona | Solo ocurrencias (vistas de ruta) |
| **Métrica secundaria** | Sí<p>Cualquier métrica, incluidas las métricas calculadas</p> | No | No |
| **Compatibilidad con los componentes en nodos o puntos de contacto** | Métricas, elementos de dimensión, filtros e intervalos de fechas. | Métricas, elementos de dimensión, filtros e intervalos de fechas. | Solo elementos de dimensión (excepto el punto de contacto inicial y final) |
| **Comparar filtros** | No | Sí<p>Realice comparaciones paralelas de dos filtros distintos en el mismo informe</p> | No |
| **Interacción de los componentes mediante arrastrar y soltar** | Sí | Sí | No |
| **Recorridos de Adobe Journey Optimizer** | Sí</br>Abrir recorridos de Journey Optimizer para un análisis y una personalización más profundos | No | No |

{style="table-layout:auto"}



## Sección de filtro Etiqueta {#tagfiltersection}

| Etiquetas | Descripción |
|---|---|
| ![Etiquetas](/help/assets/filter-tag.png){width="300"} | La sección **[!UICONTROL Etiquetas]** le permite filtrar las etiquetas. <ul><li>Puede ![Búsqueda](/help/assets/icons/Search.svg) *Buscar etiquetas* para buscar las etiquetas que puede utilizar para filtrar.</li><li>Puede seleccionar más de una etiqueta. Las etiquetas disponibles dependen de las selecciones realizadas en otras secciones del panel de filtro.</li><li>Los números indican lo siguiente:<ul><li>**(1)**: el número de etiquetas seleccionadas (si se seleccionan una o más).</li><li>**2︎⃣**: el número de etiquetas disponibles para los elementos resultantes del filtro actual.</li><li>7︎⃣: el número de elementos asociados a la etiqueta específica.</li></ul></li></ul> |


## Sección de filtro del grupo de informes {#reportsuitefiltersection}

| Grupo de informes | Descripción |
|---|---|
| ![Grupo de publicaciones](/help/assets/filter-reportsuite.png){width="300"} | La sección **[!UICONTROL Grupo de informes]** le permite filtrar los grupos de informes. <ul><li>Puede ![Buscar](/help/assets/icons/Search.svg) *Buscar grupos de informes* para buscar grupos de informes que pueda usar para filtrar.</li><li>Puede seleccionar más de un grupo de informes. Los grupos de informes disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican lo siguiente:<ul><li>**(2)**: El número de grupos de informes seleccionados (si se seleccionan uno o más grupos de informes).</li><li>**3︎⃣**: El número de grupos de informes disponibles para los elementos resultantes del filtro actual.</li><li>4︎⃣: número de elementos asociados con el grupo de informes específico.</li></ul></li></ul> |

## Sección de filtro Estado habilitado {#enabledstatusfiltersection}

| Estado habilitado | Descripción |
|---|---|
| ![Estado habilitado](/help/assets/filter-enabledstatus.png){width="300"} | La sección **[!UICONTROL Estado habilitado]** le permite filtrar según el estado habilitado. <ul><li>Puede seleccionar más de un estado.</li><li>Los números indican lo siguiente:<ul><li>**(2)**: el número de estados seleccionados (si se seleccionan uno o más estados).</li><li>**2︎⃣**: el número de estados disponibles para los elementos resultantes del filtro actual.</li><li>1︎⃣: el número de elementos asociados al estado específico.</li></ul></li></ul> |

## Sección de filtro Tipo {#typefiltersection}

| Tipo | Descripción |
|---|---|
| ![Tipo](/help/assets/filter-type.png){width="300"} | La sección **[!UICONTROL Tipo]** le permite filtrar según el tipo. <ul><li>Puede seleccionar más de un tipo.</li><li>Los números indican lo siguiente:<ul><li>**(2)**: el número de tipos seleccionados (si se seleccionan uno o más tipos).</li><li>**1︎⃣**: el número de tipos disponibles para los elementos resultantes del filtro actual.</li><li>3︎⃣: el número de proyectos asociados al tipo específico.</li></ul></li></ul> |

## Sección de filtro Propietario {#ownerfiltersection}

| Propietario | Descripción |
|---|---|
| ![Propietarios](/help/assets/filter-owners.png){width="300"} | La sección **[!UICONTROL Propietario]** le permite filtrar por los propietarios. <ul><li>Utilice ![Búsqueda](/help/assets/icons/Search.svg) *Buscar propietarios* para buscar los propietarios que puede utilizar para filtrar.</li><li>Puede seleccionar más de un propietario. Los propietarios disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican lo siguiente:<ul><li>**(2)**: el número de propietarios seleccionados (si se seleccionan uno o más propietarios).</li><li>**3︎⃣**: el número de propietarios disponibles para los elementos resultantes del filtro actual.</li><li>4︎⃣: el número de elementos asociados al propietario específico.</li></ul></li></ul> |

## Sección de filtro Otros filtros {#otherfiltersfiltersection}

| Otros filtros | Descripción |
|---|---|
| ![Otros filtros](/help/assets/filter-other.png){width="300"} | La sección **[!UICONTROL Otros filtros]** le permite filtrar otros filtros predefinidos.<ul><li>Puede seleccionar una o varias de las siguientes opciones:<ul><li> **[!UICONTROL Mostrar todo]**</li><li>**[!UICONTROL Compartidos conmigo]**</li><li>**[!UICONTROL Míos]**</li><li>**[!UICONTROL Aprobado]**</li><li>**[!UICONTROL Favoritos]**</li></ul> Lo que puede seleccionar depende de la función y los permisos.</li><li>Puede seleccionar más de un otro filtro. Los otros filtros disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican lo siguiente:<ul><li>**(1)**: el número de otros filtros seleccionados (si se seleccionan uno o más filtros).</li><li>**5︎⃣**: el número de otros filtros disponibles para los elementos resultantes del filtro actual.</li><li>4︎⃣: el número de proyectos asociados al otro filtro específico.</li></ul></li></ul> |

## Sección de filtro Intervalo de fecha  {#daterangefiltersection}

| Intervalo de fecha aplicado | Descripción |
|---|---|
| ![Intervalo de fecha](/help/assets/filter-daterange.png){width="300"} | La sección Intervalo de fecha aplicado permite filtrar un intervalo de fecha aplicable a los elementos.<ol><li>Seleccione un intervalo de fecha.</li><li>En la ventana emergente del calendario, defina un intervalo de fecha o seleccione uno de los ajustes preestablecidos disponibles.<br>Como alternativa, también puede especificar un intervalo de fecha directamente en la sección Intervalo de fecha del panel Filtro.</li></ol><ul><li>Los números indican lo siguiente:<ul><li>**(1)**: el número de intervalos de fechas modificados a partir de los ajustes preestablecidos predeterminados.</li><li>**5︎⃣**: el número de intervalos de fechas disponibles para los elementos resultantes del filtro actual.</li></ul> |


## Desaprobación del importador de clasificaciones {#classification-importer-deprecation}

>[!WARNING]
>
>El importador de clasificaciones está obsoleto y ya no estará accesible después del **31 de agosto de 2026**. Cambie a la experiencia [Conjuntos de clasificaciones](/help/components/classifications/sets/overview.md) para garantizar la funcionalidad continua.
>



## Desaprobación del Generador de reglas de clasificación {#classification-rulebuilder-deprecation}

>[!WARNING]
>
>El generador de reglas de clasificación está obsoleto y ya no se podrá acceder a él después del **31 de agosto de 2026**. Cambie a la experiencia [Conjuntos de clasificaciones](/help/components/classifications/sets/overview.md) para garantizar la funcionalidad continua.
>

