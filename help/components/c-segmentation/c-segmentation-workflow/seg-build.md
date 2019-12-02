---
description: El Generador de segmentos proporciona un lienzo al que arrastrar y en el que soltar las dimensiones de métricas, los segmentos y los eventos para segmentar a los visitantes en función de la lógica, las reglas y los operadores de la jerarquía de contenedor. Esta herramienta de desarrollo integrado le permite generar y guardar segmentos simples o complejos que identifican atributos y acciones de visitantes en visitas y visitas individuales de páginas.
solution: Analytics
title: Generar segmentos
topic: Segments
uuid: c01393df-ccdd-431c-83a6-3c2700bd4999
translation-type: tm+mt
source-git-commit: a50b08cba865b61bc647ba6af9e678ef8edfe3bc

---


# Generador de segmentos

The [!UICONTROL Segment Builder] provides a canvas to drag and drop Metrics, Dimensions, Segments, and Events to segment visitors based on container hierarchy logic, rules, and operators. Esta herramienta de desarrollo integrado le permite generar y guardar segmentos simples o complejos que identifican atributos y acciones de visitantes en visitas y visitas individuales de páginas.

>[!IMPORTANT]
>
>Hemos introducido modelos de atribución de dimensión en la versión de junio de 2019. Consulte la sección 6 de Funciones de la interfaz de usuario web más abajo.

Existen varias formas de acceder al Generador de segmentos:

* **Navegación superior de Analytics**: Haga clic en **[!UICONTROL Analytics]** &gt; **[!UICONTROL Componentes]** &gt; **[!UICONTROL Segmentos]**.
* **[!UICONTROL Analysis Workspace]**: Haga clic en **[!UICONTROL Analytics]** &gt; **[!UICONTROL Workspace]**, abra un proyecto y haga clic en **[!UICONTROL + Nuevo]** &gt; **[!UICONTROL Crear segmento]**.
* **[!UICONTROL Reports &amp; Analytics]** Haga clic en **[!UICONTROL Analytics]** &gt; **[!UICONTROL Informes]**, abra un informe existente y haga clic en el icono Segmentos ![](assets/segment_icon.png) en la navegación izquierda; a continuación, haga clic en **[!UICONTROL Agregar]**.
* **[!UICONTROL Ad Hoc Analysis]**: [Generar segmentos en Ad Hoc Analysis](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md#build-segments).
* **[!UICONTROL Report Builder]**: [Añadir o editar segmentos en Report Builder](https://marketing.adobe.com/resources/help/en_US/arb/segmentation.html).

## Interfaz de usuario del Generador de segmentos {#concept_643F2DF74C544796B58F4656ABC5F726}

El [!UICONTROL Generador de segmentos] le permite generar segmentos simples o complejos que identifican atributos y acciones de visitantes en visitas y visitas individuales de páginas. Proporciona un lienzo al que arrastrar y en el que soltar las dimensiones de métricas, eventos u otros segmentos para segmentar a visitantes en función de la lógica, las reglas y los operadores de la jerarquía.

## Características de la interfaz de usuario web  {#section_F61C4268A5974C788629399ADE1E6E7C}

El [!UICONTROL Generador de segmentos] le permite generar y editar segmentos en la interfaz de usuario web (o en una [interfaz de usuario de Java en Ad Hoc Analysis](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)). Puede agregar definiciones de reglas y contenedores para refinar sus segmentos, apilar segmentos y anidarlos para refinarlos. También puede validar cuántas vistas de páginas, visitas y visitantes únicos tiene como resultado su definición de segmento actual. Luego puede guardar el segmento por si lo necesita posteriormente.

Acceda al Generador de segmentos de una de las siguientes maneras::

* Muestre un informe existente y haga clic en el icono de Segmentos ![](assets/segment_icon.png) en el menú de navegación de la izquierda. Haga clic en **[!UICONTROL Añadir en el carril de segmentos que se muestra]**.

* En el Administrador de segmentos, haga clic en **[!UICONTROL + Agregar]**.
* Haciendo clic en un título de segmento existente en el Administrador de segmentos para editarlo en el Generador de segmentos.

![](assets/segment_builder_ui.png)

1. **[!UICONTROL Título]**: Permite asignar un nombre al segmento o cambiarlo por otro.
1. **[!UICONTROL Descripción]**: Proporcione una descripción para el segmento. Debe proporcionar una descripción si desea compartir el segmento.
1. **[!UICONTROL Etiquetas]**: [ Etiquete el segmento](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) que va a generar seleccionando las etiquetas existentes en una lista o creando una etiqueta nueva.
1. **[!UICONTROL Definiciones]**: Esta es la zona de trabajo donde [se generan y configuran segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md), se agregan reglas y se anidan y secuencian contenedores. Permite introducir una descripción del nuevo segmento seleccionando el contenedor y arrastrando y soltando las dimensiones, los segmentos o las métricas en la definición.
1. **[!UICONTROL Mostrar]**: (Selector de contenedor superior). Le permite seleccionar el nivel de [contenedor](/help/components/c-segmentation/seg-overview.md) superior ([!UICONTROL visitante], [!UICONTROL visita] o [!UICONTROL visita individual]). El contenedor de nivel superior predeterminado es el contenedor de visita individual.
1. Icono de **[!UICONTROL opciones]** (engranaje)

   * **[!UICONTROL + Agregar contenedor]**: le permite agregar un contenedor nuevo (bajo el contenedor de nivel superior) a la definición del segmento.
   * **[!UICONTROL + Agregar contenedor desde selección]**: le permite crear un nuevo contenedor a partir del elemento o elementos que haya seleccionado en el campo Definiciones.
   * **[!UICONTROL Excluir]**: permite definir el segmento excluyendo una o más dimensiones, segmentos o métricas.

1. **[!UICONTROL Modelos de atribución]**: Para la segmentación de dimensiones. Los modelos de dimensión son especialmente útiles en la segmentación secuencial, como en aquellos que admiten visualizaciones de flujo:

   * **[!UICONTROL Repetir]** (predeterminado): Incluye instancias y valores persistentes para la dimensión.
   * **[!UICONTROL Instancia]**: Incluye instancias para la dimensión.
   * **[!UICONTROL Instancia]** no repetitiva: Incluye instancias únicas (no repetitivas) para la dimensión.
   ![](assets/attribution-models.jpg)

1. **[!UICONTROL Dimensiones]**: Las dimensiones se arrastran y se sueltan desde la lista Dimensiones (barra lateral naranja).
1. **[!UICONTROL Comparación]**: Puede comparar y restringir valores utilizando una selección de operadores.
1. **[!UICONTROL Valor]**: Valor introducido o seleccionado para la dimensión, el segmento o la métrica.
1. **[!UICONTROL And/Or/Then]**: Asigna los operadores [!UICONTROL AND/OR/THEN] entre contenedores o reglas. El operador THEN le permite [definir segmentos secuenciales](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md).
1. **[!UICONTROL Métrica]**: Métrica arrastrada y soltada a partir de la lista Métricas.
1. Operador de **[!UICONTROL comparación]**: Puede comparar y restringir valores utilizando una selección de operadores.
1. **[!UICONTROL Valor]**: Valor introducido o seleccionado para la dimensión, el segmento o la métrica.
1. **[!UICONTROL X]**: Le permite eliminar esta parte de una definición de segmento.
1. **[!UICONTROL Guardar]** o **[!UICONTROL Cancelar]**: Guarda o cancela el segmento. Después de hacer clic en **[!UICONTROL Guardar]**, se le redirigirá al Administrador de segmentos, donde podrá administrar el segmento en cuestión.
1. **[!UICONTROL Buscar]**: Permite buscar la lista de dimensiones, segmentos o métricas.
1. **[!UICONTROL Dimensiones]**: (Lista) Haga clic en el encabezado para ampliarlo.
1. **[!UICONTROL Métricas]**: Haga clic en el encabezado para ampliarlo.
1. **[!UICONTROL Segmentos]**: Haga clic en el encabezado para ampliarlo.
1. **[!UICONTROL Selector de grupo de informes]**: Le permite seleccionar el grupo de informes en el que se guardará este segmento. Puede seguir utilizando el segmento en todos los grupos de informes.
1. **[!UICONTROL Previsualización de segmento]**: Le permite previsualizar las métricas clave para comprobar si tiene un segmento válido y ver su amplitud. Representa el desglose del conjunto de datos que verá si aplica este segmento. Muestra tres círculos concéntricos y una lista para indicar el número y el porcentaje de coincidencias de [!UICONTROL visitas individuales], [!UICONTROL visitas] y [!UICONTROL visitantes] de un segmento comparado con un conjunto de datos. Esta tabla se actualiza inmediatamente después de crear o cambiar la definición del segmento.
1. **[!UICONTROL Compatibilidad de producto]**: Proporciona una lista de los productos de Adobe Analytics (Analysis Workspace, [!UICONTROL Reports &amp; Analytics], Ad Hoc Analysis, Data Warehouse) con los que es compatible el segmento que ha creado. La mayoría de los segmentos son compatibles con todos los productos. Sin embargo, no todos los operadores y dimensiones son compatibles con todos los productos de Analytics, en especial  [Data Warehouse](/help/components/c-segmentation/seg-reference/seg-compatibility.md). Esta tabla se actualiza inmediatamente después de cambiar la definición del segmento.

Los segmentos con intervalos de fechas incorporados siguen operando en Analysis Workspace de forma distinta a como lo hacen en [!UICONTROL Reports &amp; Analytics]. En Workspace, un segmento con un intervalo de fechas integrado anula el intervalo de fechas del panel. Por su parte, en [!UICONTROL Reports &amp; Analytics] se emplea la intersección del intervalo de fechas del informe y el intervalo de fechas integrado del segmento.

**[!UICONTROL Publicar en Experience Cloud (para`<report suite name>`)]**: (No se muestra en pantalla) Esta opción solo aparece si el grupo de informes en el que está guardando este segmento está [habilitado para Experience Cloud](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md). Al publicar un segmento en Experience Cloud, puede utilizarlo para la actividad de marketing en la [!UICONTROL biblioteca de audiencias], en [!DNL Target] y en [!DNL Audience Manager]. Es necesario introducir un título y una descripción de segmento.

> [!NOTE] En Analytics, puede editar o eliminar un segmento publicado. Si el segmento se encuentra en uso, aparece un mensaje de advertencia al editar un segmento. No puede eliminar un segmento publicado que Adobe [!DNL Target] esté usando.

![](assets/segment_publish_to_mac_copy.png)

>[!IMPORTANT]
>
>Debe limitar la cantidad de audiencias compartidas de Analytics a 20 para evitar retrasos de procesamiento adicionales. Las audiencias compartidas en Experience Cloud desde Analytics no pueden superar los 20 millones de miembros únicos. Además, debido al almacenamiento en caché, los grupos de informes eliminados en Analytics tardan 12 horas en desaparecer de Experience Cloud.

>[!IMPORTANT]
>
>Una vez que un visitante se califica para la audiencia compartida desde Analytics, deben pasar de 24 a 48 horas antes de que pueda realizarse alguna acción sobre esa información en [!DNL Target], [!DNL Advertising Cloud] y [!DNL Campaign].

## Generar segmentos {#build-segments}

1. Basta con que arrastre una dimensión, un segmento o un evento de métrica del panel izquierdo al campo [!UICONTROL Definiciones].

   ![](assets/drag_n_drop_dimension.png)

   El contenedor de [!UICONTROL visita individual] de nivel superior predeterminado se muestra tras arrastrar un elemento a [!UICONTROL Definiciones]. Puede cambiar el tipo de contenedor a visita o visitante desde el menú desplegable **[!UICONTROL Mostrar]**.

1. Establezca el [operador](/help/components/c-segmentation/seg-reference/seg-operators.md) en el menú desplegable.
1. Introduzca o seleccione un valor para el elemento seleccionado.
1. Agregue contenedores adicionales si es necesario, utilizando las reglas **[!UICONTROL And]**, **[!UICONTROL Or]** o **[!UICONTROL Then]**.
1. Después de colocar los contenedores y configurar las reglas, consulte los resultados del segmento en la tabla de validación, en la parte superior derecha. El validador indica el porcentaje y el número absoluto de vistas de la página, visitas y visitantes únicos que coinciden con el segmento que ha creado.
1. En **[!UICONTROL Etiquetas]**, [etiquete](/help/components/c-segmentation/c-segmentation-workflow/seg-tag.md) el contenedor seleccionando una etiqueta existente o creando una nueva.
1. Haga clic en **[!UICONTROL Guardar]** para guardar el segmento.

Ahora se le redirige al [Administrador de segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-manage.md), donde puede etiquetar, compartir y administrar el segmento de varias formas.

## Generar y anidar contenedores {#section_1C38F15703B44474B0718CEF06639EFD}

Puede [generar un marco de contenedores](/help/components/c-segmentation/seg-overview.md) y luego colocar reglas lógicas y operadores entre medias.

1. Haga clic en **[!UICONTROL Opciones &gt; Agregar contenedor]**.

   ![](assets/add_container.png)

   Un nuevo contenedor de [!UICONTROL visita individual] se abrirá sin una [!UICONTROL visita individual] (vista de página) identificada.

   ![](assets/new_container.png)

1. Cambie el tipo de contenedor según sea necesario.
1. Arrastre una dimensión, segmento o evento desde el panel izquierdo al contenedor.
1. Siga agregando nuevos contenedores desde el botón **[!UICONTROL Opciones]** &gt; **[!UICONTROL Agregar contenedores]** del nivel superior situado en la parte superior de la definición o agregue contenedores desde dentro de un contenedor para anidar la lógica.

   **OR**

   Seleccione una o más reglas y luego haga clic en **[!UICONTROL Opciones]** &gt; **[!UICONTROL Agregar contenedor desde selección]**. Esto convierte su selección en un contenedor separado.

## Usar intervalos de fechas en los segmentos {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Puede generar segmentos que contienen intervalos de fechas móviles para responder a preguntas sobre campañas o eventos en curso.

Por ejemplo, puede crear fácilmente un segmento que incluya a “todas las personas que hayan efectuado una compra en los últimos 60 días”.

Usted crea un contenedor de visita y, dentro del mismo, agrega el intervalo temporal [!UICONTROL Últimos 60 días] y la métrica [!UICONTROL Pedidos es mayor o igual que 1], con un operador AND:

![](assets/date-ranges.png)

## Apilar segmentos {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

El apilamiento de segmentos funciona mediante la combinación de criterios en cada segmento utilizando un operador "y", y luego aplicando los criterios combinados.

Por ejemplo, el apilamiento de los segmentos "usuarios de teléfono móvil" y "geografía de Estados Unidos" devolverá datos relativos únicamente a los usuarios de teléfono móvil en los Estados Unidos.

Considere estos segmentos como bloques de construcción o módulos que puede incluir en una biblioteca de segmentos, para que los usuarios los utilicen como mejor les convenga. De este modo, puede reducir considerablemente el número de segmentos necesarios. Por ejemplo, ponga por caso que tiene 40 segmentos:

* 20 para usuarios de teléfonos móviles en diferentes países (EEUU_móvil, Alemania_móvil, Francia_móvil, Brasil_móvil, etc.).
* 20 para usuarios de tabletas en diferentes países (EEUU_tableta, Alemania_tableta, Francia_tableta, Brasil_tableta, etc.).

Si utiliza el apilamiento de segmentos, puede reducir el número de segmentos a 22 y apilarlos según le convenga. Tendrá que crear estos segmentos:

* Un segmento para usuarios de móviles.
* Un segmento para usuarios de tabletas.
* 20 segmentos para las diferentes zonas geográficas.

> [!NOTE] Al apilar dos segmentos, se unen de manera predeterminada con una instrucción AND. No es posible cambiarlo a una instrucción OR.

1. Vaya al Generador de segmentos.
1. Introduzca un título y una descripción para el segmento.

   Resultado (1). Haga clic en **[!UICONTROL Mostrar segmentos]** para que aparezca la lista de segmentos en el panel de navegación izquierdo.

   Resultado (1). Arrastre y suelte los segmentos que desea apilar en el lienzo de definición del segmento. A continuación se muestra un ejemplo de un segmento que apila los segmentos existentes "Visitas desde tabletas" y "Geografía EE. UU.":

   ![](assets/seg_stack2.png)

1. Guarde el segmento.

   Resultado de los pasos

## Usar plantillas de segmentos {#concept_5098446CC78D441E93B8E4D1D1EA6558}

Las plantillas representan los antiguos segmentos preconfigurados y de grupo.

En el Administrador de segmentos, haga clic en **[!UICONTROL Agregar]**, que le lleva al Generador de segmentos. A continuación, haga clic en el icono Segmentos ![](assets/segment_icon.png)

para que aparezca el carril del segmento. Las plantillas de segmentos aparecen en la parte inferior de la lista de segmentos. Las distinguirá por el icono de carpeta que aparece a la izquierda del nombre de la plantilla:

![](assets/seg_template.png)

Puede arrastrar estas plantillas al lienzo de definiciones y utilizarlas tal y como están definidas, o bien modificarlas.

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre de plantilla </th> 
   <th colname="col2" class="entry"> Definición </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Abandonar carro </td> 
   <td colname="col2">Ver datos de visitantes que agregaron elementos al carro pero no realizaron ningún pedido. En la definición de segmento, el contenedor es Visita. La regla de este segmento secuencial es: <p> Adiciones al carro no es nulo </p> <p>Entonces </p> <p>Pedidos es igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas por primera vez </td> 
   <td colname="col2">Ver datos de visitantes que han visitado el sitio como máximo una [1] vez. En la definición de segmento, el contenedor es Visita. La regla es: <p>Número de visitas es igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> No compradores </td> 
   <td colname="col2">Ver datos de los visitantes que no participaron en un evento de pedido. En la definición de segmento, el contenedor es Visitante. Este segmento utiliza la lógica Excluir. La regla es: <p>El pedido no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visita de página no única (no rebotes) </td> 
   <td colname="col2">Ver datos de los visitantes que visitaron más de una vez. En la definición de segmento, el contenedor es Visitante. Este segmento utiliza la lógica Excluir. La regla es: <p>El acceso único no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Búsqueda de pago </td> 
   <td colname="col2">Ver datos de visitantes procedentes de una búsqueda de pago. En la definición de segmento, el contenedor es Visita. La regla es: <p>La búsqueda de pago es igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compradores </td> 
   <td colname="col2">Ver datos de los visitantes que participaron en un evento de pedido. En la definición de segmento, el contenedor es Visitante. La regla es: <p>El pedido no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de retorno </td> 
   <td colname="col2">Ver datos de los visitantes que han visitado por lo menos una vez. En la definición de segmento, el contenedor es Visita. La regla es: <p>Número de visitas es mayor que 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas a una sola página </td> 
   <td colname="col2"> Ver datos de las visitas en las que se ve el valor de una sola página, aunque se envíen varias vistas de página durante esa visita. En el segmento se incluyen las visitas a una sola página con eventos de vínculo de salida. En la definición de segmento, el contenedor es Visita. La regla es: <p>Visitas de página única es igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Producto visto no se agregó al carro </td> 
   <td colname="col2">Ver datos de los visitantes que vieron productos pero no agregaron nada al carro. En la definición de segmento, el contenedor es Visita. La regla de este segmento secuencial es: <p>Vistas de producto no es nulo </p> <p>Entonces </p> <p> Adiciones al carro es igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde campaña </td> 
   <td colname="col2">Ver datos de visitantes remitidos desde campañas. En la definición de segmento, el contenedor es Visita. La regla es: <p>El código de seguimiento no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde dispositivos móviles </td> 
   <td colname="col2">Ver datos de visitantes que utilizan dispositivos móviles. En la definición de segmento, el contenedor es Visita. La regla es: <p>El dispositivo móvil no es nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de búsqueda natural </td> 
   <td colname="col2">Ver datos de visitantes que no proceden de una búsqueda de pago. En la definición de segmento, el contenedor es Visita. La regla es: <p>La búsqueda de pago es igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde un dispositivo no móvil </td> 
   <td colname="col2">Ver datos de visitantes que no utilizan dispositivos móviles. En la definición de segmento, el contenedor es Visita. Este segmento utiliza la lógica Excluir. La regla es: <p>El tipo de dispositivo móvil es igual a teléfono móvil </p> <p>O </p> <p>El tipo de dispositivo móvil es igual a tableta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde teléfonos </td> 
   <td colname="col2">Ver datos de los visitantes que utilizan teléfonos. En la definición de segmento, el contenedor es Visita. La regla es: <p>El tipo de dispositivo es igual a teléfono móvil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde motores de búsqueda </td> 
   <td colname="col2">Ver datos de visitantes remitidos desde motores de búsqueda. En la definición de segmento, el contenedor es Visita. La regla es: <p>El tipo de referente es igual a motores de búsqueda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas provenientes de sitios sociales </td> 
   <td colname="col2">Ver datos de visitantes remitidos desde sitios sociales. En la definición de segmento, el contenedor es Visita. La regla es: <p>El tipo de referente es igual a redes sociales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas desde tabletas </td> 
   <td colname="col2">Ver datos de los visitantes que utilizan tabletas. En la definición de segmento, el contenedor es Visita. La regla es: <p>El tipo de dispositivo es igual a tableta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas con cookie de ID de visitante </td> 
   <td colname="col2">Ver datos de los visitantes del sitio con los que se requiere una cookie persistente. En la definición de segmento, el contenedor es Visita. La regla es: <p>La cookie persistente es igual a 1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplo: Segmento de visitantes de Campaign {#concept_61AC6115097B4EB3AEFE8CE98F38315D}

Muestra un ejemplo de este segmento frecuentemente utilizado.

Muchos clientes desean ver la métrica de los visitantes que respondieron a campañas específicas. Una sencilla manera de obtener estos datos consiste en crear un segmento de visitantes de campaña.

Al crear este segmento en el Generador de segmentos, arrastre una dimensión de campaña, en este caso Nombre de campaña, desde un contenedor de visita de nivel superior:

![](assets/seg_campaign_visitor.png)

(Opcional) También puede aplicar una etiqueta Campañas a este segmento, si desea filtrar fácilmente todos los segmentos relacionados con la campaña.
