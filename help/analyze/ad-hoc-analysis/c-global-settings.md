---
description: Configurar las opciones globales de comportamiento. Por ejemplo, se puede configurar el guardado automático, las opciones de gráficos y tablas y especificar la fuente y la configuración regional.
title: Configuración
uuid: 34444052-479b-4923-b379-a03ca614bf3e
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 98%

---


# Configuración

>[!IMPORTANT]
>
>Adobe está moviendo Ad Hoc Analysis al estado de fin de vida el 1 de marzo de 2021. [Más información...](https://adobe.ly/discoverworkspace).

Configurar las opciones globales de comportamiento. Por ejemplo, se puede configurar el guardado automático, las opciones de gráficos y tablas y especificar la fuente y la configuración regional.

## Configuración {#concept_D21E3D6F13EA4F97913F60C243B72173}

Configurar las opciones globales de comportamiento. Por ejemplo, se puede configurar el guardado automático, las opciones de gráficos y tablas y especificar la fuente y la configuración regional.

Haga clic en **[!UICONTROL Herramientas]** > **[!UICONTROL Configuración]** para acceder a la [!UICONTROL Configuración global].

## Pestaña Configuración general: definiciones {#reference_EADAF83466994F89BCC6B0F49A9A53DB}

Permite configurar las opciones de comportamiento para las fuentes de datos, el guardado de proyectos, los gráficos y las tablas.

<!-- 

r_dsc_general_settings.xml

 -->

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definición </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Configuración de datos </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Contar instancias repetidas</span>: Especifica si se cuentan las instancias en los informes. Significa que, si hay varios valores secuenciales para una misma variable, puede contarlos como una o como varias instancias de la variable. </p> <p>Por ejemplo, puede ver recargas de página repetidas, que es la cantidad de veces que se recargan o actualizan esas páginas en el sitio Web durante una sola visita. Esta opción permite especificar si varias visitas a la misma página se cuentan como una o como varias vistas de la página. </p> <p> <span class="uicontrol"> <span class="keyword"> Ad Hoc</span> </span>: Permite especificar <span class="keyword">Ad Hoc</span> como la única fuente de datos para los informes. Los datos se recopilan mediante solicitudes de imagen generadas desde las páginas web. </p> <p> <span class="uicontrol"> <span class="keyword">Fuentes de datos</span></span>: Indica si se usarán datos cargados desde otras fuente de Adobe o fuentes de datos personalizadas. Los datos estarán disponibles en los productos de <span class="keyword">Experience Cloud</span>. Consulte <a href="https://docs.adobe.com/content/help/es-ES/analytics/import/data-sources/datasrc-home.html"  >Fuentes de datos</a> para obtener más información. </p> <p> <span class="uicontrol"> Ambos</span>: (opción predeterminada) Usa datos de <span class="keyword">Ad Hoc Analysis</span> y otras fuentes de datos. </p> <p>Nota: Si cambia estas opciones, pueden producirse discrepancias en los informes entre los datos de <span class="keyword">Ad Hoc Analysis</span> y los <span class="keyword">datos de Reports and Analytics de marketing.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Configuración de guardado automático </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Guardado automático habilitado</span>: Habilita la funcionalidad de guardado automático. </p> <p> <span class="uicontrol"> Frecuencia para guardar el proyecto automáticamente</span>: Permite ajustar el intervalo temporal para la función de guardado automático. Un proyecto se guarda automáticamente solo si Análisis específicos deja de funcionar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Configuración de gráfico </p> </td> 
   <td colname="col2"> <p><b>Contraer gráficos de forma predeterminada</b>: haga clic en este botón para mostrar los informes sin gráfico en la sección superior. Cuando se muestra un informe con esta opción, puede ampliarlo manualmente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Configuración de tabla </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Mostrar números de línea</span>: Activa o desactiva los números de línea en la tabla del informe. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Pestaña Clasificación: Definiciones {#reference_FB9BADD7E3DA42C1BB2A02A6E9D5C1CF}

Permite configurar la presentación de los datos en columnas y seleccionar métricas predeterminadas para los informes de tráfico y conversión.

<!-- 

r_dsc_ranked_tab.xml

 -->

| Campo | Definición |
|--- |--- |
| Configuración de columna | Permite configurar la presentación de los datos en las tablas y de los gráficos de barras en los diagramas. |
| Seleccionar métricas predeterminadas | Especifique las métricas predeterminadas de los informes de tráfico y conversión, además de las métricas disponibles en todos los informes.    Incluir valor predeterminado específico del informe: indica si se desean incluir las métricas predeterminadas al personalizar la vista. |

## Pestaña Análisis del sitio: Definiciones {#reference_9DD37C8EF718409E990E149596282FF8}

Permite configurar opciones de métricas y gráficos para el informe de análisis del sitio.

<!-- 

r_dsc_site_analysis_tab.xml

 -->

| Campo | Definición |
|--- |--- |
| Métricas | Permite seleccionar las métricas representadas por el ancho y la altura del cilindro y determinar qué métrica se representa mediante colores; también permite configurar los colores usados para representar valores altos y bajos de la métrica. Se pueden configurar métricas para los ejes X e Y; también se pueden agregar otras métricas para que aparezcan en el texto emergente del informe. También puede invertir cualquiera de las métricas seleccionadas para la presentación. |
| General y alertas | Permite habilitar y deshabilitar ciertos elementos gráficos del informe. Se pueden configurar alertas para que aparezcan en el informe cuando las métricas asociadas con las páginas y representadas por los cilindros superen cierto valor. |

## Pestaña Fuente y configuración regional: definiciones {#reference_5F2129B67CC44E5BA9EA7E30A35BFB49}

Permite indicar la configuración regional de idioma y la fuente predeterminada. Los cambios de fuente y configuración regional entrarán en efecto la próxima vez que reinicie.

<!-- 

r_dsc_font_locale.xml

 -->

| Campo | Definición |
|--- |--- |
| Seleccione una configuración regional | Permite especificar el idioma que se mostrará en la interfaz de usuario. |
| Seleccione una fuente | Permite indicar la fuente de presentación. |
