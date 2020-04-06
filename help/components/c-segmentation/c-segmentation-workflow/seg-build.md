---
description: El Generador de segmentos proporciona un lienzo al que arrastrar y en el que soltar las dimensiones de métricas, los segmentos y los eventos para segmentar a los visitantes en función de la lógica, las reglas y los operadores de la jerarquía de contenedor. Esta herramienta de desarrollo integrado le permite generar y guardar segmentos simples o complejos que identifican atributos y acciones de visitantes en visitas y visitas individuales de páginas.
title: Generar segmentos
topic: Segments
uuid: c01393df-ccdd-431c-83a6-3c2700bd4999
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Generador de segmentos

The [!UICONTROL Segment Builder] provides a canvas to drag and drop Metrics, Dimensions, Segments, and Events to segment visitors based on container hierarchy logic, rules, and operators. Esta herramienta de desarrollo integrado le permite generar y guardar segmentos simples o complejos que identifican atributos y acciones de visitantes en visitas y visitas individuales de páginas.

>[!IMPORTANT]
>
>Hemos introducido modelos de atribución de dimensión en la versión de junio de 2019. Consulte la sección 6 de Funciones de la interfaz de usuario web más abajo.

Existen varias formas de acceder al Generador de segmentos:

* **Navegación** superior de Analytics: Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Segments]**.
* **[!UICONTROL Analysis Workspace]**:: Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, abra un proyecto y haga clic en **[!UICONTROL + New]** > **[!UICONTROL Create Segment]**.
* **[!UICONTROL Reports & Analytics]**:: Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**, abra un informe existente, haga clic en el icono Segmentos ![](assets/segment_icon.png) en el panel de navegación izquierdo y, a continuación, haga clic en **[!UICONTROL Add]**.
* **[!UICONTROL Ad Hoc Analysis]**:: [Generar segmentos en Análisis](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md#build-segments)ad hoc.
* **[!UICONTROL Report Builder]**:: [Añada o edite segmentos en el Creador](https://marketing.adobe.com/resources/help/es_ES/arb/segmentation.html)de informes.

## Interfaz de usuario del Generador de segmentos {#concept_643F2DF74C544796B58F4656ABC5F726}

Le [!UICONTROL Segment Builder] permite generar segmentos simples o complejos que identifican atributos y acciones de visitante en visitas y visitas individuales de página. Proporciona un lienzo para arrastrar y soltar dimensiones de métricas, eventos u otros segmentos con el fin de segmentar visitantes según la lógica de jerarquía, las reglas y los operadores.

## Características de la interfaz de usuario web  {#section_F61C4268A5974C788629399ADE1E6E7C}

The [!UICONTROL Segment Builder] lets you build and edit segments in the web UI (or in a [Java UI in Ad Hoc Analysis](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)). Puede agregar definiciones de reglas y contenedores para refinar sus segmentos, apilar segmentos y anidarlos para refinarlos. También puede validar cuántas vistas de páginas, visitas y visitantes únicos tiene como resultado su definición de segmento actual. A continuación, guarde el segmento para satisfacer necesidades futuras.

Acceda al Generador de segmentos mediante:

* Muestre un informe existente y haga clic en el icono de Segmentos ![](assets/segment_icon.png) en el menú de navegación de la izquierda. In the segment rail that displays, click **[!UICONTROL Add]**.

* From within the Segment Manager, clicking **[!UICONTROL + Add]**.
* Haciendo clic en un título de segmento existente en el Administrador de segmentos para editarlo en el Generador de segmentos.

![](assets/segment_builder_ui.png)

1. **[!UICONTROL Title]**:: Permite asignar un nombre al segmento o cambiarlo por otro.
1. **[!UICONTROL Description]**:: Proporcione una descripción para el segmento. Debe proporcionar una descripción si desea compartir el segmento.
1. **[!UICONTROL Tags]**:: [Etiquete el segmento](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) que esté creando eligiendo de una lista de etiquetas existentes o creando una nueva etiqueta.
1. **[!UICONTROL Definitions]**:: Aquí es donde [crea y configura segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md), agrega reglas y anida y secuencia contenedores. Permite introducir una descripción del nuevo segmento seleccionando el contenedor y arrastrando y soltando las dimensiones, los segmentos o las métricas en la definición.
1. **[!UICONTROL Show]**:: (Selector de Contenedor superior). Permite seleccionar el [contenedor](/help/components/c-segmentation/seg-overview.md) de nivel superior ( [!UICONTROL Visitor], [!UICONTROL Visit], [!UICONTROL Hit]). El contenedor de nivel superior predeterminado es el contenedor de visita individual.
1. **[!UICONTROL Options]**:: Icono (de engranaje)

   * **[!UICONTROL + Add container]**:: Permite agregar un nuevo contenedor (debajo del contenedor de nivel superior) a la definición del segmento.
   * **[!UICONTROL + Add container from selection]**:: Permite crear un nuevo contenedor a partir de los elementos que haya seleccionado (varios) en el campo Definiciones.
   * **[!UICONTROL Exclude]**:: Permite definir el segmento excluyendo una o más dimensiones, segmentos o métricas.

1. **[!UICONTROL Attribution Models]**:: Para la segmentación de dimensiones. Los modelos de dimensión son especialmente útiles en la segmentación secuencial, como en aquellos que admiten visualizaciones de flujo:

   * **[!UICONTROL Repeating]** (predeterminado): Incluye instancias y valores persistentes para la dimensión.
   * **[!UICONTROL Instance]**: Incluye instancias para la dimensión.
   * **[!UICONTROL Non-repeating instance]**: Incluye instancias únicas (no repitadas) para la dimensión.
   ![](assets/attribution-models.jpg)

1. **[!UICONTROL Dimensions]**:: Las dimensiones se arrastran y se sueltan desde la lista Dimensiones (barra lateral naranja).
1. **[!UICONTROL Comparison]**:: Puede comparar y restringir valores usando operadores seleccionados.
1. **[!UICONTROL Value]**:: El valor introducido o seleccionado para la dimensión, segmento o métrica.
1. **[!UICONTROL And/Or/Then]**:: Asigna los [!UICONTROL AND/OR/THEN] operadores entre contenedores o reglas. El operador THEN le permite [definir segmentos secuenciales](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md).
1. **[!UICONTROL Metric]**:: Métrica (barra lateral verde) que se arrastró y soltó desde la lista Métricas.
1. **[!UICONTROL Comparison]** operador: Puede comparar y restringir valores usando operadores seleccionados.
1. **[!UICONTROL Value]**:: El valor introducido o seleccionado para la dimensión, segmento o métrica.
1. **[!UICONTROL X]**: Le permite eliminar esta parte de una definición de segmento.
1. **[!UICONTROL Save]** o **[!UICONTROL Cancel]**: Guarda o cancela el segmento. After clicking **[!UICONTROL Save]**, you are taken to the Segment Manager where you can manage the segment.
1. **[!UICONTROL Search]**:: Busca la lista de dimensiones, segmentos o métricas.
1. **[!UICONTROL Dimensions]**:: (Lista) Haga clic en el encabezado para expandirlo.
1. **[!UICONTROL Metrics]**:: Haga clic en el encabezado para expandirlo.
1. **[!UICONTROL Segments]**:: Haga clic en el encabezado para expandirlo.
1. **[!UICONTROL Report suite selector]**:: Permite seleccionar el grupo de informes en el que se guardará este segmento. Puede seguir utilizando el segmento en todos los grupos de informes.
1. **[!UICONTROL Segment Preview]**:: Le permite realizar una previsualización de las métricas clave para ver si tiene un segmento válido y cuán amplio es el segmento. Representa el desglose del conjunto de datos que verá si aplica este segmento. Shows 3 concentric circles and a list to show the number and percentage of matches for [!UICONTROL Hits], [!UICONTROL Visits], and [!UICONTROL Visitors] for a segment run against a data set. Este gráfico se actualiza inmediatamente después de crear o realizar cambios en la definición del segmento.
1. **[!UICONTROL Product Compatibility]**:: Proporciona una lista de los productos de Adobe Analytics (Espacio de trabajo de Análisis, [!UICONTROL Reports & Analytics], Análisis ad hoc, Almacén de datos) con los que el segmento que ha creado es compatible. La mayoría de los segmentos son compatibles con todos los productos. Sin embargo, no todos los operadores y dimensiones son compatibles con todos los productos de Analytics, en especial  [Data Warehouse](/help/components/c-segmentation/seg-reference/seg-compatibility.md). Esta tabla se actualiza inmediatamente después de cambiar la definición del segmento.

Los segmentos con intervalos de fechas incorporados siguen operando en Analysis Workspace de forma distinta a como lo hacen en [!UICONTROL Reports & Analytics]. En Workspace, un segmento con un intervalo de fechas integrado anula el intervalo de fechas del panel. Por su parte, en [!UICONTROL Reports & Analytics] se emplea la intersección del intervalo de fechas del informe y el intervalo de fechas integrado del segmento.

**[!UICONTROL Publish to Experience Cloud (for `<report suite name>`)]**: (No se muestra en pantalla) Esta opción solo aparece si el grupo de informes en el que está guardando este segmento está [habilitado para Experience Cloud](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md). By publishing a segment to the Experience Cloud, you can use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], and [!DNL Audience Manager]. Es necesario introducir un título y una descripción de segmento.

>[!NOTE] En Analytics, puede editar o eliminar un segmento publicado. Si el segmento se encuentra en uso, aparece un mensaje de advertencia al editar un segmento. No puede eliminar un segmento publicado que Adobe [!DNL Target] esté usando.

![](assets/segment_publish_to_mac_copy.png)

>[!IMPORTANT]
>
>Debe limitar la cantidad de audiencias compartidas de Analytics a 20 para evitar retrasos de procesamiento adicionales. Las Audiencias compartidas en Experience Cloud desde Analytics no pueden superar los 20 millones de miembros únicos. Además, debido al almacenamiento en caché, los grupos de informes eliminados en Analytics tardan 12 horas en desaparecer de Experience Cloud.

>[!IMPORTANT]
>
>Una vez que un visitante se califica para la audiencia compartida desde Analytics, deben pasar de 24 a 48 horas antes de que pueda realizarse alguna acción sobre esa información en [!DNL Target], [!DNL Advertising Cloud] y [!DNL Campaign].

## Generar segmentos {#build-segments}

1. Basta con arrastrar un Evento de dimensión, segmento o métrica del panel izquierdo al [!UICONTROL Definitions] campo.

   ![](assets/drag_n_drop_dimension.png)

   The default top-level [!UICONTROL Hit] container is shown after dragging an element to [!UICONTROL Definitions]. You can change the container type to Visit or Visitor from the **[!UICONTROL Show]** drop-down menu.

1. Establezca el [operador](/help/components/c-segmentation/seg-reference/seg-operators.md) en el menú desplegable.
1. Introduzca o seleccione un valor para el elemento seleccionado.
1. Add additional containers if needed, using **[!UICONTROL And]**, **[!UICONTROL Or]**, or **[!UICONTROL Then]** rules.
1. Después de colocar los contenedores y configurar las reglas, consulte los resultados del segmento en la tabla de validación, en la parte superior derecha. El validador indica el porcentaje y el número absoluto de vistas de página, visitas y visitantes únicos que coinciden con el segmento creado.
1. Under **[!UICONTROL Tags]**, [tag](/help/components/c-segmentation/c-segmentation-workflow/seg-tag.md) the container by selecting an existing tag or creating a new one.
1. Click **[!UICONTROL Save]** to save the segment.

Ahora se le redirige al [Administrador de segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-manage.md), donde puede etiquetar, compartir y administrar el segmento de varias formas.

## Generar y anidar contenedores {#section_1C38F15703B44474B0718CEF06639EFD}

Puede [generar un marco de contenedores](/help/components/c-segmentation/seg-overview.md) y luego colocar reglas lógicas y operadores entre medias.

1. Haga clic en **[!UICONTROL Options > Add Container]**.

   ![](assets/add_container.png)

   Se abre un nuevo [!UICONTROL Hit] contenedor sin una [!UICONTROL Hit] (Vista de página) identificada.

   ![](assets/new_container.png)

1. Cambie el tipo de contenedor según sea necesario.
1. Arrastre una dimensión, segmento o Evento desde el panel izquierdo al contenedor.
1. Continue to add new containers from the top-level **[!UICONTROL Options]** > **[!UICONTROL Add container]** button at the top of the definition, or add containers from within a container to nest logic.

   **OR**

   Select one or more rules and then click **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**. Esto convierte su selección en un contenedor separado.

## Usar intervalos de fechas en los segmentos {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Puede generar segmentos que contienen intervalos de fechas móviles para responder a preguntas sobre campañas o eventos en curso.

Por ejemplo, puede crear fácilmente un segmento que incluya a “todas las personas que hayan efectuado una compra en los últimos 60 días”.

Puede crear un contenedor de visita y, dentro de él, agregar el intervalo de [!UICONTROL Last 60 days] tiempo y la métrica [!UICONTROL Orders is greater than or equal to 1], con un operador Y:

![](assets/date-ranges.png)

## Apilar segmentos {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

El apilamiento de segmentos funciona combinando los criterios de cada segmento con un operador &#39;y&#39; y, a continuación, aplicando los criterios combinados.

Por ejemplo, apilar un segmento &quot;usuarios de teléfonos móviles&quot; y un segmento &quot;geográfico de EE. UU.&quot; devolverá datos sólo para usuarios de teléfonos móviles en EE. UU.

Considere estos segmentos como bloques de creación o módulos que puede incluir en una biblioteca de segmentos, para que los usuarios los utilicen como consideren oportuno. De este modo, puede reducir drásticamente el número de segmentos necesarios. Por ejemplo: supongamos que tiene 40 segmentos:

* 20 para usuarios de teléfonos móviles en diferentes países (US_mobile, Alemania_mobile, Francia_mobile, Brasil_mobile, etc.)
* 20 para usuarios de tabletas en diferentes países (US_tableta, Alemania_tableta, Francia_tableta, Brasil_tableta, etc.)

Mediante el apilamiento de segmentos, puede reducir el recuento de segmentos a 22 y apilarlos según sea necesario. Debe crear estos segmentos:

* un segmento para usuarios móviles
* un segmento para usuarios de tabletas
* 20 segmentos para las diferentes regiones geográficas

>[!NOTE] Al apilar dos segmentos, se unen de manera predeterminada con una instrucción AND. No es posible cambiarlo a una instrucción OR.

1. Vaya al Generador de segmentos.
1. Proporcione un título y una descripción para el segmento.

   Resultado (1). Click **[!UICONTROL Show Segments]** to bring up the list of segments in the left navigation.

   Resultado (1). Arrastre y suelte los segmentos que desee apilar en el lienzo de definición de segmento. Este es un ejemplo de un segmento que apila los segmentos existentes &quot;Visitas desde tabletas&quot; y &quot;Geografía de EE. UU.&quot;:

   ![](assets/seg_stack2.png)

1. Guarde el segmento.

   Resultado de los pasos

## Usar plantillas de segmentos {#concept_5098446CC78D441E93B8E4D1D1EA6558}

Las plantillas representan los antiguos segmentos preconfigurados y de grupo.

In the Segment Manager, click **[!UICONTROL Add]**, which takes you to the Segment Builder. A continuación, haga clic en el icono Segmentos ![](assets/segment_icon.png)

para que aparezca el carril del segmento. Las plantillas de segmentos aparecen en la parte inferior de la lista de segmentos. Se distinguen por un icono de carpeta a la izquierda del nombre de la plantilla:

![](assets/seg_template.png)

Puede arrastrar estas plantillas al lienzo Definiciones y utilizarlas tal como se han definido o modificarlas.

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre de la plantilla </th> 
   <th colname="col2" class="entry"> Definición </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Vaciar carro </td> 
   <td colname="col2">Datos de Vista de visitantes que agregaron artículos a sus carros pero no pidieron nada. En la Definición de segmento, el contenedor es Visita. La regla de este segmento secuencial es <p> Adiciones al carro de compras no es nulo </p> <p>Y LUEGO  </p> <p>Pedidos es igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas por primera vez </td> 
   <td colname="col2">Datos de Vista de visitantes que han visitado el sitio como máximo una [1] vez. En la Definición de segmento, el contenedor es Visita. La regla es <p>Número de visita es igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> No compradores </td> 
   <td colname="col2">Datos de Vista para visitantes que no han participado en un evento de pedido. En la Definición de segmento, el contenedor es Visitante. Este segmento utiliza la lógica Excluir. La regla es <p>Pedidos no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visita a más de una página (sin salidas hacia otro sitio) </td> 
   <td colname="col2">Datos de Vista de visitantes que visitaron más de una vez. En la Definición de segmento, el contenedor es Visitante. Este segmento utiliza la lógica Excluir. La regla es <p>El acceso único no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Búsqueda de pago </td> 
   <td colname="col2">Datos de Vista de visitantes procedentes de una búsqueda paga. En la Definición de segmento, el contenedor es Visita. La regla es <p>La búsqueda paga es igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compradores </td> 
   <td colname="col2">Datos de Vista para visitantes que han participado en un evento de pedidos. En la Definición de segmento, el contenedor es Visitante. La regla es <p>Pedidos no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de retorno </td> 
   <td colname="col2">Datos de Vista de visitantes que han visitado al menos una vez. En la Definición de segmento, el contenedor es Visita. La regla es <p>El número de visitas es bueno a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas a una sola página </td> 
   <td colname="col2"> Datos de Vista de visitas en las que se ve un valor de una sola página, aunque se envíen varias vistas de página durante esa visita. Las visitas a una sola página con eventos de vínculo de salida se incluyen en el segmento. En la Definición de segmento, el contenedor es Visita. La regla es <p>Visitas a una sola página es igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Producto visualizado no Añadido al carro </td> 
   <td colname="col2">Datos de Vista para visitantes que vieron productos pero no agregaron productos al carro de compras. En la Definición de segmento, el contenedor es Visita. La regla de este segmento secuencial es <p>Las Vistas del producto no son nulas </p> <p>Y LUEGO  </p> <p> Adiciones al carro de compras es igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde campaña </td> 
   <td colname="col2">Datos de Vista de visitantes referidos por campañas. En la Definición de segmento, el contenedor es Visita. La regla es <p>El código de seguimiento no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde dispositivos móviles </td> 
   <td colname="col2">Vista de datos de visitantes mediante dispositivos móviles. En la Definición de segmento, el contenedor es Visita. La regla es <p>El dispositivo móvil no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de búsqueda natural </td> 
   <td colname="col2">Datos de Vista de visitantes que no proceden de una búsqueda paga. En la Definición de segmento, el contenedor es Visita. La regla es <p>La búsqueda paga es igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde dispositivos no móviles </td> 
   <td colname="col2">Datos de Vista de visitantes que no utilizan dispositivos móviles. En la Definición de segmento, el contenedor es Visita. Este segmento utiliza la lógica Excluir. La regla es <p>Tipo de dispositivo móvil es igual a teléfono móvil </p> <p>O </p> <p>El tipo de dispositivo móvil es igual a Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde móviles </td> 
   <td colname="col2">Datos de Vista de visitantes que utilizan teléfonos. En la Definición de segmento, el contenedor es Visita. La regla es <p>El tipo de dispositivo es igual que el teléfono móvil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde motores de búsqueda </td> 
   <td colname="col2">Datos de Vista de visitantes referidos por los motores de búsqueda. En la Definición de segmento, el contenedor es Visita. La regla es <p>El tipo de Remitente del reenvío es igual a los motores de búsqueda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde sitios sociales </td> 
   <td colname="col2">Datos de Vista de visitantes referidos por sitios sociales. En la Definición de segmento, el contenedor es Visita. La regla es <p>El tipo de Remitente del reenvío es igual que las redes sociales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde tabletas </td> 
   <td colname="col2">Datos de Vista de visitantes que utilizan tabletas. En la Definición de segmento, el contenedor es Visita. La regla es <p>El tipo de dispositivo es igual a Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas con cookie de ID de visitante </td> 
   <td colname="col2">Vista de datos desde visitantes a su sitio, donde se requiere una cookie persistente. En la Definición de segmento, el contenedor es Visita. La regla es <p>La cookie persistente es igual a 1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplo: Segmento de visitantes de Campaign {#concept_61AC6115097B4EB3AEFE8CE98F38315D}

Muestra un ejemplo de este segmento utilizado con frecuencia.

Muchos clientes desean ver métricas de visitantes que respondieron a campañas específicas. La creación de un segmento de visitantes de campaña es una forma sencilla de obtener estos datos.

La creación de este segmento en el Generador de segmentos significa que, desde un contenedor de visita de nivel superior, arrastra una dimensión de campaña, en este caso Nombre de Campaña:

![](assets/seg_campaign_visitor.png)

(Opcional) También puede aplicar una etiqueta de Campañas a este segmento si desea filtrar fácilmente todos los segmentos relacionados con la campaña.
