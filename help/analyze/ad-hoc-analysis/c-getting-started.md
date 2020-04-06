---
description: Introducción a Ad Hoc Analysis.
title: Introducción
uuid: 6a698e18-4e62-405e-b020-b973c9c4008b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Introduccción a Ad Hoc Analysis {#concept_48936BA28FAE42DB81F1B2CD4726EB17}

>[!IImportante]
>El 6 de agosto de 2018 Adobe anunció su intención de finalizar el servicio de Ad Hoc Analysis. La fecha se hará pública una vez que esté disponible. Para obtener más información, incluidas las versiones de Java compatibles durante este periodo, visite [https://adobe.ly/discoverworkspace](https://adobe.ly/discoverworkspace).

Puede realizar análisis instantáneas y avanzadas en la actividad del sitio web. Puede realizar vistas de varios informes simultáneamente y aplicar segmentos en varias dimensiones. Puede analizar los datos desde las perspectivas micro y macro para vista su impacto en las métricas comerciales importantes.

Estas funciones le permiten responder preguntas sobre el tráfico del sitio, la demografía del visitante, los ingresos y el movimiento del producto. A continuación, puede filtrar, ordenar y segmentar los datos para encontrar las respuestas a preguntas precisas. Los resultados se devuelven casi instantáneamente, lo que permite analizar rápidamente los efectos de una combinación de factores.

<table id="table_C9C0444687FC418580F996E1D2ADB61A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tareas introductorias </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1. Iniciar sesión en Adobe <span class="keyword">Analytics</span>. </p> </td> 
   <td colname="col2"> <p>Vaya a <a href="https://marketing.adobe.com"  >marketing.adobe.com</a> e inicie sesión con sus credenciales de Adobe Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2. Iniciar Ad Hoc Analysis. </p> </td> 
   <td colname="col2">Haga clic en <span class="uicontrol">Adobe Analytics</span> &gt; <span class="uicontrol">Herramientas</span> &gt; <span class="uicontrol">Ad Hoc Analysis</span> y luego haga clic en el botón <span class="uicontrol">Iniciar Ad Hoc Analysis</span>. <p> <p>Nota: Si no ve el botón <b>Iniciar Ad Hoc Analysis</b> en esta página, asegúrese de que el administrador lo haya agregado al grupo <i>Usuarios con licencias de Ad Hoc Analysis</i> en las herramientas de administración. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3. Crear un proyecto. </p> </td> 
   <td colname="col2"> <p>En la página de inicio, seleccione un grupo de informes y haga clic en <span class="uicontrol">Crear proyecto</span>. </p> <p>Consulte <a href="/help/analyze/ad-hoc-analysis/c-getting-started.md"   > Proyectos y espacios de trabajo</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4. Abra un informe. </p> </td> 
   <td colname="col2"> <p>Busque un informe utilizando el menú de informes estándar de Cloud. También puede elegir una plantilla. </p> <p>Consulte <a href="/help/analyze/ad-hoc-analysis/c-getting-started.md"   > Plantillas</a>de informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5. Configure el informe. </p> </td> 
   <td colname="col2"> <p>Configure los informes realizando tareas como: </p> 
    <ul id="ul_0D2E8C614F2A4899A376BCEECEA374C6"> 
     <li id="li_FA925D52A8FD4DFAB0C88B797B24E72B"> Crear segmentos para profundizar en los datos </li> 
     <li id="li_5E91632551D2473BA8BD0637CDC1A9F6"> Agregar métricas, dimensiones y segmentos al  <a href="/help/analyze/ad-hoc-analysis/c-tablebuilder.md"   > Generador de tablas</a> </li> 
     <li id="li_019316C9A94B4A8C8A77D07C04E50278">Configuración de <a href="/help/analyze/ad-hoc-analysis/c-dates.md"   >intervalos de fechas</a> </li> 
     <li id="li_2B33B325D5EE420AB412B73AD1D231C5"> <a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   > Programar</a> el envío de informes </li> 
    </ul> <p>Busque en este sistema de ayuda para encontrar la ayuda que necesita. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recomendaciones de sistemas {#concept_6691331B45174290BD9B839806A9B52D}

Aunque los informes deberían funcionar correctamente con los navegadores web más usuales, se verán y funcionarán mejor en sistemas que se ajusten a las siguientes recomendaciones.

<!-- 

c_sys_reqs.xml

 -->

>[!NOTE] A partir de julio de 2018, Ad Hoc Analysis solo admitirá Java 8 o versiones posteriores. Si ejecuta Ad Hoc Analysis en Java 7 después de la actualización de mantenimiento de julio de 2018, Adobe no ofrecerá compatibilidad para su implementación de análisis específicos.

* Tarjeta de vídeo compatible con OpenGL 2.0
* Cookies: Requerido
* Sistema operativo: Windows y Mac OS.
* Macromedia Flash Player: versión 6 o posterior
* Resolución del monitor: 800 x 600 (se recomienda 1024 x 768)
* Profundidad de color: 16 bits o bueno
* JavaScript: Habilitado
* Versión de Java: Java 1.7 o posterior (consulte la nota anterior)

   Si no tiene instalada la versión correcta de Java, se instalará automáticamente. Si tiene instalada una versión incompatible de Java, la Análisis ad hoc descargará las actualizaciones y le pedirá que las instale.

## Instrucciones de actualización de Java  {#section_E4C0C6492FF24636A0FF71A59331111D}

A partir de julio de 2018, Ad Hoc Analysis solo admitirá Java 8 o versiones posteriores. Si ejecuta Ad Hoc Analysis en Java 7 después de la actualización de mantenimiento de julio de 2018, Adobe no ofrecerá compatibilidad para su implementación de análisis específicos.

Nuestros archivos .jar están firmados con un cifrado seguro de 256 bits con el que las versiones de Java anteriores a la 1.7.0_76 no son compatibles. Este certificado de 256 bits nos permite ofrecerle una mayor seguridad.

Si todavía tiene Java 7 instalado, debe actualizar primero a la versión de mantenimiento de julio de 2018. A continuación se muestra cómo:

* Si puede instalar programas en su equipo:

   1. Vaya a https://www.java.com.
   1. Haga clic en **[!UICONTROL Free Java Download]**.
   1. Haga clic en **[!UICONTROL Agree and Start Free Download]**.
   1. Instale la última versión de Java específica para su sistema operativo.

* Si **no tiene** permiso para instalar programas en su equipo:

   1. Trabaje con su departamento de TI para instalar la versión más reciente de Java.

## Iniciar Ad Hoc Analysis {#concept_B1CE3C1E6D1A4311B9835BEB69812E55}

<!-- 

c_login.xml

 -->

Puede iniciar sesión desde [!DNL Experience Cloud] o desde una dirección URL. Si inicia sesión desde Informes y análisis, se iniciará sesión automáticamente. El inicio de sesión con una URL solo es necesario si accede a la URL de análisis ad hoc desde otra ubicación, como un vínculo o un menú Favoritos.

## Inicio de sesión desde Experience Cloud {#task_128ED319F3AE49ED886EA3DFA8D0987F}

Instrucciones sobre cómo iniciar sesión desde [!DNL Experience Cloud].

<!-- 

t_login_suite.xml

 -->

1. En un navegador, vaya a [!DNL marketing.adobe.com].
1. Type your company name, your username, and your password. Then click **[!UICONTROL Sign In]**.
1. Haga clic **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Ad Hoc Analysis]**.

   Si no ve el botón **Iniciar Ad Hoc Analysis** en esta página, asegúrese de que el administrador lo haya agregado al grupo *Usuarios con licencias de Ad Hoc Analysis* en las herramientas de administración.
1. Haga clic en **[!UICONTROL Launch Ad Hoc Analysis]**.
1. Guarde el archivo [!DNL discover.jnlp] localmente.

   Puede ejecutar este archivo que guardó cada vez que desee iniciar Ad Hoc Analysis.

## Proyectos y espacio de trabajo {#concept_FAE346335B0347A192C6C806C775D72B}

Un proyecto define el conjunto de datos que se importa, incluidos un grupo de informes y un intervalo de fechas. Un proyecto consiste en cualquier número de informes con todas sus métricas, configuraciones, dimensiones y segmentos. Puede iniciar un nuevo proyecto, cargar un proyecto guardado o cargar el proyecto que guarda automáticamente.

<!-- 

c_projects.xml

 -->

Los informes se agrupan en un *espacio de trabajo*. Un proyecto puede contener varios espacios de trabajo y un espacio de trabajo puede contener varios informes. La mejor forma de entender la relación entre estos elementos es verla como una relación anidada:

![](assets/project_workspace.png)

Solo puede abrir un proyecto a la vez. Sin embargo, puede abrir varias áreas de trabajo en un proyecto. En cada área de trabajo puede tener varios informes abiertos.

El intervalo de fechas predeterminado para un nuevo proyecto es [!UICONTROL Last 90 Days].

## Inicio de proyectos {#task_918A4539134E4E62B00486DCB8D3D403}

Instrucciones sobre cómo iniciar un proyecto.

<!-- 

t_project_start.xml

 -->

1. Inicie sesión.
1. Open a saved project or click **[!UICONTROL Create Project]**.
1. Busque un informe o elija una plantilla.

## Apertura de espacios de trabajo guardados recientemente {#task_DE4A54180BC24E9DAEC98E2171DC6B40}

Instrucciones sobre cómo abrir espacios de trabajo guardados recientemente.

<!-- 

t_recent_workspace.xml

 -->

1. Haga clic **[!UICONTROL File]** > **[!UICONTROL Recent Workspace]**.

   Puede abrir hasta cinco espacios de trabajo recientes. Los espacios de trabajo recientes no están disponibles después de salir de la sesión.

## Proyectos compartidos {#task_5911780D90164F3A8A677C8BC719750D}

Los proyectos compartidos estarán disponibles para todos los usuarios de Ad Hoc Analysis de la empresa.

<!-- 

t_share_projects.xml

 -->

1. Vaya a **[!UICONTROL File]** > **[!UICONTROL Save As]**.
1. Seleccione **[!UICONTROL Shared Projects]** en la **[!UICONTROL Save in:]** lista desplegable.

   ![](assets/shared_projects.png)

1. Click **[!UICONTROL Save]** to save the project.

   Los proyectos compartidos se pueden abrir mediante **[!UICONTROL File]** > **[!UICONTROL Open]** > **[!UICONTROL Shared Projects]**.

   >[!NOTE]
   >
   >Puede eliminar sus proyectos compartidos en el mismo cuadro de diálogo de proyectos compartidos seleccionando uno o más proyectos.

## Cambio de nombre de un espacio de trabajo {#task_0DB177DD6DB54B7F9FE60A0B3FC7CFC3}

Instrucciones sobre cómo cambiar el nombre de espacio de trabajo.

<!-- 

t_rename_workspace.xml

 -->

1. Haga clic con el botón derecho en el nombre del espacio de trabajo.
1. Elegir **[!UICONTROL Rename Workspace]**.
1. Type a name, then click **[!UICONTROL OK]**.

## Abrir un proyecto local {#task_1B3EF63A80C74776B24B99D80EAC74AC}

Instrucciones sobre cómo abrir una copia local de un proyecto.

<!-- 

t_open_local_project.xml

 -->

1. Haga clic **[!UICONTROL File]** > **[!UICONTROL Open Local Copy]**.
1. Navigate to the local [!DNL .dproj] file, then click **[!UICONTROL Open]**.

## Plantillas de informe {#concept_370F674C5B4C45368731AA801C5A45F8}

Las plantillas son puntos de partida para el tipo de análisis que desea realizar. Una plantilla puede ser un lienzo en blanco, como un informe de clasificación o de visitas en el orden previsto. O bien, la plantilla es un informe que inicio con métricas y dimensiones predeterminadas.

<!-- 

c_templates.xml

 -->

You can access templates when creating a project ( **[!UICONTROL File]** > **[!UICONTROL New Project]**), or by adding a workspace or report.

| Plantilla | Descripción |
|--- |--- |
| Clasificación | Proporciona un lienzo en blanco en el que puede crear una tabla. Por ejemplo, los informes de páginas clasifican las páginas del sitio según el tráfico, y la tabla de detalles muestra los porcentajes y las cantidades correspondientes a diversas métricas, por ejemplo, las vistas de páginas y los ingresos. |
| Tendencias | Permite examinar la tendencia de las conversiones y los eventos en una granularidad de tiempo seleccionada (hora, día, semana, mes, trimestre o año) durante un período de sistema de informes. |
| Totales | Informe de nivel ejecutivo que muestra las cifras finales. Contiene datos para Ingresos totales, Vistas de página y Pedidos. |
| Abandono | Permite construir un canal que muestra las tasas de conversión y de visitas en el orden previsto entre puntos de comprobación. Por ejemplo, puede rastrear los puntos de abandono de un visitante durante un proceso de compra. |
| Flujo | Muestra las rutas más comunes que toman los usuarios en páginas, secciones del sitio y servidores. |
| Canal de conversión | Muestra los porcentajes de conversión entre eventos de métricas específicos. Puede utilizar este informe para comprender la cantidad de pulsaciones que generan ventas y la cantidad de unidades vendidas. |
| Análisis del sitio | Herramienta de ruta de sitios tridimensional que muestra cómo se mueven los visitantes por páginas y eventos especificados. |
| Grupo de enfoque virtual | Realiza una visita al azar desde sus visitas y muestra una gran cantidad de datos sobre la visita. Puede utilizar el informe para crear grupos de enfoque a partir de la población de visitantes. |

## Abrir un informe {#task_0AC455CDA198497AA546622FB05F300D}

Puede abrir un informe o una plantilla al crear un proyecto o desde un proyecto existente. Utilice una plantilla para configurar un informe desde cero.

<!-- 

t_reports_opening.xml

 -->

Existen varias formas de abrir un informe:

* En la [!UICONTROL New Report] página, busque un informe o elija una plantilla.
* Haga clic **[!UICONTROL Reports]** en el menú y, a continuación, seleccione un informe o una plantilla de informe.
* Launch a report from a dimension: right-click a dimension name, then select **[!UICONTROL Run Report]** > **`report name`**.
