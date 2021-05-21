---
title: Resumen general de las clasificaciones
description: Personalice la agrupación de los elementos de dimensión.
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '605'
ht-degree: 100%

---

# Resumen general de las clasificaciones

Las clasificaciones permiten aplicar categorías a los datos de variables de Analytics para mostrarlos de distintos modos cuando se generan los informes.

Vídeo con información general sobre las [Clasificaciones de Analytics](https://video.tv.adobe.com/v/16853/).

**[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > *`<Traffic or Conversion>`*

Con las clasificaciones se establece una relación entre la variable y los metadatos relacionados con ella. Por lo general, las clasificaciones se usan en campañas. Para resumir los datos que se recopilan a través de la información de las variables (eVars, props y eventos), pueden aplicarse metadatos a los valores recopilados en las variables.

![Información sobre los pasos](assets/sub_class_create.png)

Una vez clasificado, los informes que pueden generarse con la variable clave pueden hacerlo también con los atributos asociados. Por ejemplo, los [!UICONTROL ID de producto] pueden clasificarse con atributos de producto adicionales, como el nombre, el color, el tamaño, la descripción y la SKU del producto. Si se aumentan los datos de informes y análisis con atributos adicionales, podrán generarse informes más profundos y complejos.

Una vez creadas las clasificaciones, pueden aprovecharse los nuevos atributos de datos en otros análisis e informes de Adobe Analytics.

## Ejemplo de códigos de seguimiento

Supongamos que, en lugar de ver las campañas tan solo por el código de seguimiento, deseamos ver sus resultados por Motor de búsqueda, Palabra clave y Canal de campaña. En lugar de dedicar variables de conversión a cada uno de estos elementos, se crean tres clasificaciones de la variable de campaña para representar a Motor de búsqueda, Palabra clave y Canal de campaña. Esta estrategia permite ver los eventos de éxito del sitio por las cuatro variables, sin necesidad de etiquetado adicional.

Informes y análisis incluye clasificaciones predefinidas para la variable de código de seguimiento, lo que permite obtener informes basados en clasificaciones, denominados Elementos creativos y Campañas. Para el resto de variables de tráfico y conversión, las clasificaciones deben configurarse manualmente.

Consulte [Clasificaciones de tráfico](/help/admin/admin/c-traffic-variables/traffic-classifications.md) y [Clasificaciones de las conversiones](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html).

En la tabla siguiente se describen los distintos tipos de clasificaciones disponibles y los tipos de variables que admiten. Consulte la información de [Estructura general de archivos](/help/components/classifications/importer/c-saint-data-files.md) antes de cargar archivos de datos.

<table id="table_279728C28D9C40EE832ACC9F211B5F17"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>TIPO </p> </th> 
   <th colname="col2" class="entry"> <p>DISPONIBILIDAD </p> </th> 
   <th colname="col3" class="entry"> <p>DESCRIPCIÓN </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Texto</span> </p> </td> 
   <td colname="col2"> <p>Variables de tráfico y conversión </p> </td> 
   <td colname="col3"> <p>Las clasificaciones de texto definen una categoría que le permite agrupar datos variables para generar informes. </p> <p>Por ejemplo, si vende camisas, puede que le interese categorizar las ventas de camisas (conversiones) por color, talla y estilo para poder generar informes en los que las ventas de camisas aparezcan organizadas según dichas categorías. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Texto con fecha habilitada</span> </p> <p>Nota: En la versión de mantenimiento de Analytics del 10 de mayo de 2018, Adobe empezó a limitar la funcionalidad de las clasificaciones habilitadas por fecha. Estos tipos de clasificaciones se eliminaron de las interfaces del Administrador y del Importador de clasificaciones. No es posible añadir nuevas clasificaciones habilitadas por fecha. Las clasificaciones existentes se podrán seguir administrando (cargado y eliminado) a través del flujo de trabajo de clasificación estándar y permanecerán disponibles en los informes. </p> </td> 
   <td colname="col2"> <p>Variables de conversión </p> </td> 
   <td colname="col3"> <p>Una clasificación de texto con fecha habilitada le permite asignar rangos de fechas a una clasificación de texto. Esto suele utilizarse con clasificaciones de campañas para poder beneficiarse de la vista del gráfico de Gantt en el informe <span class="wintitle">Campañas</span>. </p> <p>Dentro del archivo de datos que rellena los datos de clasificación, puede incluir las fechas de la campaña real. </p> <p>Reports &amp; Analytics recopila códigos de seguimiento de campaña incluso cuando la fecha de finalización de una campaña ya ha transcurrido (aunque estos datos no aparecen asociados con la campaña). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Numéricos</span> <p>Nota: En la versión de mantenimiento de Analytics del 10 de mayo de 2018, Adobe empezó a limitar la funcionalidad de las clasificaciones numéricas. Estos tipos de clasificaciones se eliminaron de las interfaces del Administrador y del Importador de clasificaciones. No es posible añadir nuevas clasificaciones numéricas. Las clasificaciones existentes se podrán seguir administrando (cargado y eliminado) a través del flujo de trabajo de clasificación estándar y permanecerán disponibles en los informes. </p> </p> </td> 
   <td colname="col2"> <p>Variables de conversión </p> </td> 
   <td colname="col3"> <p>Las clasificaciones numéricas le permiten aplicar valores numéricos fijados a los informes de <span class="wintitle">Conversión</span>. Estas clasificaciones aparecen como métricas en los informes. </p> <p>Cuando se considere la posibilidad de agregar una clasificación <span class="wintitle">numérica</span>, el valor numérico deberá fijarse sin sufrir modificaciones a lo largo del tiempo. </p> </td> 
  </tr> 
 </tbody> 
</table>
