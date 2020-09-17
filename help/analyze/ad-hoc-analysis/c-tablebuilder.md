---
description: El Generador de tablas permite crear informes con cualquier configuración de métricas, dimensiones y segmentos. Por ejemplo, puede agregar varias métricas al Generador de tablas y aplicar segmentos a todas ellas a la vez. Puede aplicar artículos de los paneles de herramientas como filas o desgloses, o como columnas, y girar la tabla para verla de otro modo. Después de crear la tabla, puede interactuar directamente con la tabla de datos resultantes, para profundizar el análisis. Tenga presente que al generar una tabla de datos desde el Generador de tablas se ejecuta una consulta y se crea una nueva tabla de datos.
title: Generador de tablas
uuid: d5dbd05e-9ebd-4571-b3a5-3856c28b65f3
translation-type: tm+mt
source-git-commit: 5d96a2868bee48e2294ec2fb27e0340a3bcc50ae
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 98%

---


# Generador de tablas

>[!IMPORTANT]
>
>El Adobe está llevando a Ad Hoc Analysis al final de su vida útil el 1 de marzo de 2021. [Más información](https://adobe.ly/discoverworkspace)

El Generador de tablas permite crear informes con cualquier configuración de métricas, dimensiones y segmentos. Por ejemplo, puede agregar varias métricas al Generador de tablas y aplicar segmentos a todas ellas a la vez. Puede aplicar artículos de los paneles de herramientas como filas o desgloses, o como columnas, y girar la tabla para verla de otro modo. Después de crear la tabla, puede interactuar directamente con la tabla de datos resultantes, para profundizar el análisis. Tenga presente que al generar una tabla de datos desde el Generador de tablas se ejecuta una consulta y se crea una nueva tabla de datos.

## Generador de tablas {#concept_574FEDC73B244101935D3C86C39DB70F}

El Generador de tablas permite crear informes con cualquier configuración de métricas, dimensiones y segmentos. Por ejemplo, puede agregar varias métricas al Generador de tablas y aplicar segmentos a todas ellas a la vez. Puede aplicar artículos de los paneles de herramientas como filas o desgloses, o como columnas, y girar la tabla para verla de otro modo. Después de crear la tabla, puede interactuar directamente con la tabla de datos resultantes, para profundizar el análisis. Tenga presente que al generar una tabla de datos desde el Generador de tablas se ejecuta una consulta y se crea una nueva tabla de datos.

El [!UICONTROL Generador de tablas] no está disponible para ciertos informes de ruta, como [!UICONTROL Análisis del sitio], [!UICONTROL Visitas en el orden previsto], [!UICONTROL Flujo] y [!UICONTROL Enfoque virtual].

## Descripciones del Generador de tablas  {#section_4B7B96546B864142AB91DF3996918590}

<table id="table_C11D78E62DEF48A78B50EFB8669817BC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Filas/Desgloses</span> </td> 
   <td colname="col2"> <p>Crear filas y desgloses a partir de artículos añadidos. El primer artículo que se arrastra a <span class="wintitle">Filas/Desgloses</span> se convierte en la columna de la izquierda de la tabla de datos o en el artículo principal del desglose. Si agrega más artículos, se crearán desgloses. </p> <p>Por ejemplo, si agrega las dimensiones Página y luego Ciudades, el informe desglosará las páginas por ciudades. Para configurar la cantidad de filas y desgloses que se mostrarán para cada artículo, se usan estos menús: </p> 
    <ul id="ul_702F215DFB814398B8F1879EDFEC103F"> 
     <li id="li_95C4DF2B33524C94BBD2E07397393300">  <span class="uicontrol">Mostrar</span> y <span class="uicontrol">Desglose</span>: Permite indicar la cantidad de artículos y desgloses que se mostrarán. </li> 
     <li id="li_D594C7F31A094D1EA1A070B80794E006"> <span class="uicontrol"> Predeterminado</span>: Usa las opciones configuradas en <span class="wintitle">Propiedades de desglose</span>. </li> 
    </ul> <p>También se puede configurar una lista de valores fijos, por ejemplo, para desglosar una métrica según un conjunto de otras métricas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Propiedades de desglose</span> </td> 
   <td colname="col2"> <p><img placement="inline"  src="assets/Settings_Illustrative.png" id="image_C46860621CF94E88AF592B8660F28E57"> </img> </p> <p>Permite indicar las opciones predeterminadas de cantidad de filas y desgloses que se desea ver, según el orden en que se agregan los artículos. Se puede indicar la cantidad de resultados totales por página y cuántas de esas filas se deben desglosar. </p> <p>Las opciones que se configuran en el <span class="wintitle">Generador de tablas</span> tienen prioridad sobre las que se configuran en <span class="wintitle">Propiedades de desglose</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Editar artículos</span> </td> 
   <td colname="col2"> <p><img  src="assets/Edit_Buttcon.png" id="image_E44BCC4B0BFF453D8564047E3DA2501A"> </img> </p> <p>Elija una lista de artículos de dimensión para crear una lista fija de desgloses. Al agregar artículos a esta lista, se convertirán en persistentes en un informe guardado y no se contraerán cuando abra un informe programado o guardado. </p> <p>Consulte <a href="/help/analyze/ad-hoc-analysis/c-reports-configure.md#task_29BEE0AF09DA4625B9B44BAB77D7C841"  > Desglose de datos de tabla</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Columnas</span> </td> 
   <td colname="col2"> <p>Permite crear columnas con artículos tomados de dimensiones, segmentos y métricas. También permite girar las columnas mediante el icono de flecha, que invierte los ejes X e Y. </p> <p> <span class="uicontrol"> Mostrar</span>: Permite limitar la cantidad de columnas que se generarán en la tabla de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Resumen</span> </td> 
   <td colname="col2"> <p>Muestra el diseño estructural del informe, para saber cuántas filas y columnas se crearán. El resumen refleja la configuración indicada en los grupos <span class="uicontrol">Filas / Desgloses</span> y <span class="uicontrol">Columnas</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Reemplazar tabla</span> </td> 
   <td colname="col2"> <p>Genera una tabla y reemplaza la anterior, según la configuración del <span class="wintitle">Generador de tablas</span>. </p> <p>Nota: Al hacer clic en <span class="uicontrol">Reemplazar tabla</span> se volverá a ejecutar el informe y se sobrescribirán los datos en la cuadrícula de la tabla. Si el usuario agrega artículos a la cuadrícula de la tabla, la correlación entre la tabla y el <span class="wintitle">Generador de tablas</span> deja de ser válida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Advertencia </td> 
   <td colname="col2"> <p><img id="image_619E1068C6084D41853DA3DD6B85DFC9"  src="assets/AlertRed_Illustrative.png" placement="inline" /> </p> <p>Indica que la configuración del <span class="wintitle">Generador de tablas</span> no devolverá datos, o que no se seleccionaron métricas. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Generar un informe desde el Generador de tablas {#task_B04801AC9848485C93DF02E96C9A9902}

Instrucciones sobre cómo usar el [!UICONTROL Generador de tablas].

<!-- 

t_table_builder.xml

 -->

1. Para acceder al [!UICONTROL Generador de tablas], ejecute un informe compatible y, a continuación, haga clic en **[!UICONTROL Generador de tablas]**.
1. Arrastre artículos (dimensiones, métricas y segmentos) desde los paneles de herramientas hasta el [!UICONTROL Generador de tablas].
1. Configure los artículos como filas, desgloses y columnas.
1. Haga clic en **[!UICONTROL Reemplazar tabla]** para generar el informe.

   Al hacer clic en **[!UICONTROL Reemplazar tabla]** se ejecutará una consulta nueva y se creará una tabla de datos nueva. Si se realizan modificaciones manuales en la tabla de detalles, estas no aparecerán en el Generador de tablas.

