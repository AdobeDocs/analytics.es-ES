---
description: Un panel es una colección de informes en miniatura llamados informes breves. Un panel es muy útil cuando contiene informes breves relacionados que le proporcionan información general completa sobre ciertos aspectos del sitio, como métodos de búsqueda, perfiles de visitante, etc.
subtopic: Dashboards
title: Paneles e informes breves
topic: Reports and analytics
uuid: 7a7b3bc9-0a3c-49b0-9168-e2878ae67b97
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Paneles e informes breves

Un panel es una colección de informes en miniatura llamados informes breves. Un panel es muy útil cuando contiene informes breves relacionados que le proporcionan información general completa sobre ciertos aspectos del sitio, como métodos de búsqueda, perfiles de visitante, etc.

## Paneles e informes breves {#concept_8CD3ACA2830A4994A68A31D8773B57E0}

Un tablero es una colección de informes en miniatura, llamados *`reportlets`*. Un panel es muy útil cuando contiene informes breves relacionados que le proporcionan información general completa sobre ciertos aspectos del sitio, como métodos de búsqueda, perfiles de visitante, etc.

Puede agregar la mayoría de los informes de marketing a un panel, incluidos los informes con gran cantidad de gráficos como el [!UICONTROL Fallout Report], [!UICONTROL Conversion Funnel Report]y el [!UICONTROL Pathfinder Report].

También puede establecer un panel como página de aterrizaje, compartir paneles con otros usuarios y programarlos para envío. Si no establece un panel (o un marcador) como página de aterrizaje, se muestra el [!UICONTROL My Recommended Reports] panel. **[!UICONTROL My Recommended Reports]** La muestra el **[!UICONTROL Key Metrics]** informe más los cinco informes vistos con más frecuencia. Es dinámico y se basa en los informes concretos que visualiza más.

Tenga en cuenta que algunos informes vistos con frecuencia no se pueden mostrar en el tablero ni se mostrarán. Estos incluyen:

* Informes de detección de anomalías
* Informes de Análisis de contribución
* Informes de visitas en el orden previsto
* Informes de Pathfinder
* Informes en tiempo real
* Otros paneles

>[!NOTE] El **[!UICONTROL Site Overview]** panel ya no aparece en Informes y análisis. Sin embargo, todavía hay un par de circunstancias en las que verá algunos o todos sus informes breves.

* Si, por ejemplo, solo tiene tres informes vistos con frecuencia, Informes y análisis tomará dos informes del panel Información general de sitio para completar el **[!UICONTROL My Recommended Reports]** panel.
* Los grupos de informes completamente nuevos también incluirán inicialmente los informes breves Información general de sitio, hasta que sean reemplazados por los informes que ve con frecuencia. Aun así, ahora se llamará al panel **[!UICONTROL My Recommended Reports]**.

Además de los tableros que cree, se incluyen los siguientes tableros empaquetados previamente para cada usuario:

**[!UICONTROL Components]>[!UICONTROL Dashboards]>[!UICONTROL Shared Dashboards]>[!UICONTROL Local Sites]**

Este panel personalizable le permite colocar informes breves en la plantilla proporcionada.

**[!UICONTROL Components]>[!UICONTROL Dashboards]>[!UICONTROL Shared Dashboards]>[!UICONTROL Site Operations Dashboard]**

Este panel proporciona información general sobre las métricas clave relacionadas con las operaciones del sitio web. Los informes sobre este panel incluyen:

* Páginas de salida
* Páginas más populares
* Secciones del sitio más populares
* KPI/informe breve de medición
* Informe breve de texto
* Informe breve de resumen de la empresa

Utilice [!UICONTROL Dashboard Manager] para editar y administrar paneles y habilitarlos para DirectAccess.

Consulte [Administración de tableros](/help/analyze/reports-analytics/dashboard-manage.md).

## Crear un tablero {#task_54EFBED59BDC4418A919E6EF84AB9CFF}

Instrucciones sobre cómo crear un panel.

<!-- 

t_dashboard_add.xml

 -->

Antes de agregar un informe (como informe breve) a un panel, defina el diseño del panel.

1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. Haga clic en **[!UICONTROL Add Dashboard]**.
1. Escriba un nombre para el tablero.
1. Haga clic en **[!UICONTROL 3 x 2]** o **[!UICONTROL 2 x 2]** para especificar cuántos informes breves desea que se muestren en la página del tablero.
1. Configure el diseño de página del tablero:

   * **[!UICONTROL Add Page]**:: Añade una página en blanco al panel, en la que puede arrastrar contenido para crear informes breves.
   * **[!UICONTROL Paper]**:: Permite especificar un tamaño de papel, como horizontal, vertical y A4.
   * **[!UICONTROL Find Content]**:: Permite buscar contenido en los menús [!UICONTROL Add Content] y [!UICONTROL Dashboard Contents] .

1. Añada el contenido disponible al tablero, arrastrando artículos al lienzo de informes breves.

   Consulte [Creación de un informe breve](/help/analyze/reports-analytics/dashboard.md#task_EC3AFBBAA51C45CEBAF632F841C305B3) y [Edición de la configuración del tablero](/help/analyze/reports-analytics/dashboard.md#task_90D7FAC1CC3E4DB786B4C87CC33B5459).
1. Haga clic en **[!UICONTROL Save.]**

   Saving a dashboard makes it available in the **[!UICONTROL Dashboard]** menu. The new dashboard is also available in the [!UICONTROL Dashboard Manager] ( **[!UICONTROL Favorites]** > **[!UICONTROL Dashboards]** > **[!UICONTROL Manager]**), where you can edit, organize, share, schedule, archive dashboards, and more. (Consulte [Administración de tableros](/help/analyze/reports-analytics/dashboard-manage.md).)

1. (Opcional) Para establecer el panel como su página de aterrizaje, haga clic en **[!UICONTROL More Options]** > **[!UICONTROL Set as Landing Page]**.

## Crear un informe breve {#task_EC3AFBBAA51C45CEBAF632F841C305B3}

Instrucciones sobre cómo crear un informe breve. Una vez que haya creado un informe breve, estará disponible para mostrarlo en un panel.

<!-- 

t_dashboard_add_report.xml

 -->

1. Ejecutar un informe.
1. Haga clic en **[!UICONTROL Dashboard.]**
1. En la [!UICONTROL Add Reportlet] página, asigne un nombre al informe y, a continuación, seleccione un panel de **[!UICONTROL Place in Dashboard]**.
1. (Opcional) Configure el intervalo de fecha.

   * **[!UICONTROL Rolling]**:: Cambia la fecha a medida que pasa el tiempo, según el lapso de tiempo (diario, mensual, etc.). Por ejemplo, si hoy es 17 de enero, puede que establezca las fechas del 15 al 16 de enero. Luego, si selecciona **[!UICONTROL Rolling]**, el 27 de enero el informe breve muestra los datos del 25 al 26 de enero.
   * **[!UICONTROL Fixed]**:: Impide que la fecha avance con el transcurso del tiempo.

1. (Opcional) Anule la lista de distribución de publicación.

   **[!UICONTROL Publishing List Override]**:: Si habilita esta opción, el grupo de informes al que se hace referencia en este informe breve siempre se utiliza cuando se distribuye en una lista de publicación. Si deshabilita esta opción, el grupo de informes identificado en la lista de publicación reemplaza al grupo de informes de este informe breve.

1. Haga clic en **[!UICONTROL Create New]**.

   The reportlet is added to the **[!UICONTROL Dashboard Contents]** menu in the dashboard editor.

## Añadir contenido a un tablero {#task_90D7FAC1CC3E4DB786B4C87CC33B5459}

Instrucciones sobre cómo agregar contenido de otros paneles y paneles compartidos. También puede agregar contenido de fuentes personalizadas y externas, como texto e imágenes.

<!-- 

t_dashboard_content.xml

 -->

1. Open a dashboard, then click **[!UICONTROL Layout]**.
1. Click **[!UICONTROL Add Content]**, then drag items to the dashboard.

   The [!UICONTROL Add Content] menu displays reportlet content from other dashboards, legacy dashboards, and shared dashboards.

   >[!NOTE]
   >
   >El límite actual del número de páginas en un panel es de 30.

   **Informes breves personalizados**

   *Contenido de datos:*

   * Resumen de la empresa: muestra las vistas de página de varios grupos de informes y métrica que seleccione.
   * Medición de las métricas: muestra una medición que le dice dónde están las cifras de las métricas en relación con los umbrales seleccionados.

      Puede seleccionar una métrica, un tipo de gráfico, una gama de colores y valores de umbral. Si el recuento de la métrica supera el umbral Mayor que, la medición así lo indicará en el informe breve, mediante el uso de color encima del campo Mayor que. Si el recuento de la métrica se encuentra por debajo del umbral Menor que, la medición así lo indicará en el informe breve, mediante el uso de color encima del campo Menor que. Los valores que especifique en estos campos son el valor contable de la métrica, como el número de vistas de página, las cantidades en dólares, las vistas del carro de compras, etc. (No utilice caracteres especiales.)
   * Resumen de los grupos de informe: muestra una métrica seleccionada y los valores totales, altos y bajos de un grupo de informes.
   * Resumen de uso: muestra datos sobre el acceso a la interfaz por parte de las personas de su organización. Este informe breve puede mostrar datos por acceso de nombre de usuario, acceso al informe o acceso al grupo de informes.
Puede crear los informes breves de Contenido de usuario siguientes siempre que indique las direcciones URL. Si la dirección URL de una imagen o de otro recurso no comienza con https://, los usuarios de Internet Explorer podrían recibir una advertencia en cuanto al contenido mixto. Puede desactivar la advertencia de contenido mixto en la configuración de seguridad del explorador.
   *Contenido de usuario:*

   * Informe externo: le permite añadir un informe externo en los formatos .xml y .csv.
   * HTML: permite añadir un informe breve HTML personalizado. La dirección URL debe utilizar HTTP o HTTPS. En caso contrario, verá un error `Specified URL could not be retrieved`. En el contenido del documento, se eliminan todas las etiquetas con atributos que utilizan los protocolos data: y javascript:. Se eliminan las secuencias de comandos, las tramas, los subprogramas, los controladores de eventos, los objetos Flash y otros objetos integrados. Si los recursos se especifican sin HTTPS, se envía una advertencia a los usuarios de IE en cuanto al contenido mixto.
   * Imagen: permite crear un tablero a partir de la dirección de URL de una imagen. Si la dirección URL utiliza el protocolo HTTP, Internet Explorer envía una advertencia de contenido mixto. Si se utiliza una dirección URL con HTTPS, se elimina la advertencia. El resto de protocolos emiten el error `Specified URL could not be retrieved`.
   * RSS: le permite añadir una fuente Web RSS. Debe ser HTTP o HTTPS. En caso contrario, verá un error `Specified URL could not be retrieved`.
   * Texto: le permite utilizar código XHTML para crear sus propios datos. Utilice HTTP o HTTPS en la dirección URL. Las imágenes utilizadas en el contenido de informe breve de texto que tengan el protocolo HTTP hacen que los usuarios de IE reciban una advertencia en cuanto al contenido mixto. Las imágenes incluidas con otros protocolos no se muestran en el informe breve.
   **Mis tableros**

   Lista los paneles actualizados desde los que puede mover contenido al nuevo panel.

   **Tableros preexistentes**

   Enumera los tableros compartidos desde los que puede mover contenido al tablero nuevo.

   **Tableros compartidos**

   Lista paneles heredados desde los que puede mover contenido al nuevo panel. Los paneles heredados son útiles si desea conservar el formato de panel de versiones anteriores.

   **Contenido de tablero**

   Muestra los elementos que ya agregó al panel.

1. Haga clic en **[!UICONTROL Save.]**

## Editar datos de informes breves y tableros {#task_B460CCD70D9F40FCAC6BBC1C044CC460}

Puede cambiar la configuración de los datos en el nivel de panel o de informe breve. Por ejemplo, puede cambiar el grupo de informes, bloquearlo, cambiar fechas, aplicar segmentos, etc. También puede personalizar un panel insertando la declaración de confidencialidad de su compañía e incluir datos de HTML, XML, API web y CSV en los informes breves personalizados.

<!-- 

t_dashboard_edit.xml

 -->

**Para editar datos de informes breves y paneles**

1. Click **[!UICONTROL Components]** > **[!UICONTROL Dashboards]** > *dashboard name* to open a dashboard.
1. Haga clic en **[!UICONTROL Layout]**.

| Hasta | Haga esto |
|--- |--- |
| Cambio del grupo de informes de un panel | Haga clic en el menú en el encabezado de Experience Cloud y, a continuación, seleccione un grupo de informes. |
| Cambiar el grupo de informes de un informe breve | In the reportlet, click the report suite name, then select a report suite from the [!UICONTROL Report Suite] menu. |
| Aplicar un segmento a un tablero | En el encabezado de Experience Cloud, haga clic en [!UICONTROL Show Segments]y, a continuación, seleccione un segmento. |
| Aplicar un segmento a un informe breve | En el tablero, haga clic en Diseño para editar un tablero.   En el informe breve, haga clic en el nombre del grupo de informes, a continuación, seleccione un valor del campo Segmento y haga clic en Actualizar. |
| Bloquear un grupo de informes (evita cambiar el grupo de informes en un informe breve) | En el informe breve, haga clic en el nombre del grupo de informes y habilite [!UICONTROL Lock Report Suite]. Haga clic en Actualizar. |
| Cambiar una fecha de sistema de informes | Para un panel, haga clic en el calendario. (Todos los informes breves del tablero reflejarán el cambio.)<br>Para un informe breve, haga clic en el vínculo de fecha y, a continuación, configure el calendario. |
| Poner nombre a un tablero | Open a dashboard, then click  [!UICONTROL More] >  [!UICONTROL Rename]. |
| Ver un archivo de tablero | Haga clic  [!UICONTROL More] >  [!UICONTROL View Archive]. |
| Establecer un tablero como página de aterrizaje | En un panel, haga clic en [!UICONTROL More] > [!UICONTROL Set As Landing Page]. |
| Descargar un tablero | In a dashboard, click  [!UICONTROL More] >  Download. |
| Imprimir un tablero | In a dashboard, click  [!UICONTROL More] >  Print. |
| Guardar un tablero | En un tablero, haga clic en Guardar como y, a continuación, especifique un nombre. |

## Promoción conjunta de marca en un tablero {#task_603BDE7700B945699AF5514C2DEB81F7}

Instrucciones sobre cómo cargar una imagen para mostrarla en un tablero.

<!-- 

t_dashboard_branding.xml

 -->

1. **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Company Settings]**.
1. En la [!UICONTROL Company Settings] página, haga clic en **[!UICONTROL Co-Brand the Adobe Experience Cloud]**.
1. Haga clic en **[!UICONTROL Enable Co-Branding]**.
1. Browse to upload the image, then click **[!UICONTROL Save.]**

   Para obtener los mejores resultados al visualizar la imagen en un navegador, cargue una imagen de 100 px por 30 px. Para obtener los mejores resultados en la salida PDF, cargue una imagen de 417 px por 125 px (300 ppp). Las imágenes de gran tamaño se reducen y se conserva la proporción de aspecto.

## Usar segmentos con tableros {#concept_ED030C3713D54D03971FB7B209285750}

Paneles, como la mayoría de los informes de Adobe Analytics, pueden utilizar segmentos para recuperar los datos deseados.

<!-- 

segments_dashboards.xml

 -->

Los segmentos se pueden aplicar en dos niveles: a un panel completo o a un informe breve específico.

* **Nivel** del informe breve: Haga clic en **[!UICONTROL Layout]**, luego en el grupo de informes del informe breve que desee segmentar. Aparece una ventana modal que le permite agregar o cambiar los segmentos que utiliza el informe breve.
* **Nivel** de Panel: Haga clic en el icono Segmento en el panel de navegación izquierdo, marque los segmentos que desee utilizar y haga clic en Aplicar. Los segmentos seleccionados anulan y reemplazan cualquier segmento de nivel de informe breve.
