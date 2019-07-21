---
description: 'null'
seo-description: 'null'
seo-title: Preguntas más frecuentes sobre Attribution IQ
title: Preguntas más frecuentes sobre Attribution IQ
uuid: 90961172-869 d -4 ed 3-aba 5-52374 e 53 b 603
translation-type: tm+mt
source-git-commit: ab2cda6d10bfeee13262581578bcdb4746112296

---


# Preguntas más frecuentes sobre Attribution IQ

<table id="table_590341C2F0DA4511ADEFDC1DB49CD248"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta </th> 
   <th colname="col2" class="entry"> Respuesta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿ Por qué a veces el elemento de línea “ninguno” obtiene más crédito de lo que yo esperaba cuando uso los modelos de atribución nuevos?</b> </p> </td> 
   <td colname="col2"> <p>R: Esto se debe probablemente a que la ventana de creación de informes que ha seleccionado según se describe <a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md#section_BC71DA030E45487AA3C3F6ED247A3C4A" format="dita" scope="local">aquí </a>. Esto ocurre normalmente cuando la ventana de creación de informes empieza en el primer día del mes y usted está usando un visitante (ventana de creación de informes) retroactivo. Para capturar atribuciones retroactivas adicionales (y reducir elemento de línea “Ninguno”), pruebe a incluir un intervalo de tiempo más largo en la ventana de creación de informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: A veces veo fechas fuera de mi ventana de informes que aparecen en el informe al utilizar modelos de atribución. ¿Por qué?</b> </p> </td> 
   <td colname="col2"> <p>R: Estas fechas extra son un artefacto de la ventana de retrospectiva de informes del visitante que se describe <a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md" format="dita" scope="local">aquí </a>. El artículo <a href="https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html" format="html" scope="external">Datos que aparecen fuera de la ventana de informes</a> explica por qué esto ocurre actualmente. Adobe Analytics filtrará estas filas extra en una próxima versión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Puedo utilizar una ventana de retrospectiva personalizada con mis modelos de atribución?</b> </p> </td> 
   <td colname="col2"> <p>A: Currently, attribution models rely on either a visitor or visit lookback window - but either of these lookback windows are adjustable by either changing the reporting date range (for visitor lookback) or by using a custom visit definition as part of Virtual Report Suites and <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-mobile-visit-processing.html" format="html" scope="external"> Context-Aware Sessions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Cuándo debería utilizar una retrospectiva de atribución de “visita” frente a una retrospectiva de atribución de “visitante”?</b> </p> </td> 
   <td colname="col2"> <p>R: La elección de la retrospectiva de atribución depende realmente de su caso de uso. Si la conversión tiene generalmente un ciclo de consideración más largo (algo que demora más tiempo que una sola visita), recomendamos utilizar una retrospectiva de visitante o crear un VRS con una visita más larga que refleje con mayor precisión ese ciclo de consideración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Los modelos de atribución están disponibles en Fuentes de datos o Data Warehouse?</b> </p> </td> 
   <td colname="col2"> <p>R: No. Como los modelos de atribución se calculan en el tiempo de informes con <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">Procesamiento de tiempo de informes</a>, no es posible tenerlos reflejados en Fuentes de datos o Data Warehouse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Los modelos de atribución solo están disponibles si utilizo un Grupo de informes virtuales con Procesamiento de tiempo de informes activado?</b> </p> </td> 
   <td colname="col2"> <p>R: No, mientras los modelos de atribución aprovechan <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">Procesamiento de tiempo de informes</a> en el backend, lo hemos puesto a disposición tanto para los grupos de informes base como VRS para su comodidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Attribution IQ en Analysis Workspace admite un modelo de atribución algorítmica o controlada por datos?</b> </p> </td> 
   <td colname="col2"> <p>R: Aún no está disponible en Analysis Workspace, pero es algo que estamos analizando activamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Algunas dimensiones o métricas no son compatibles con Attribution IQ?</b> </p> </td> 
   <td colname="col2"> <p>A: IQ de atribución se admite en todas las dimensiones.</p> 
    <p>Algunas métricas <u>no</u> compatibles (principalmente porque no tendrían sentido) son las siguientes: </p> 
    <ul id="ul_B12A1291DEEF41FDBAD110C4A9265234"> 
     <li id="li_245571C5377C45ADBAE6F735B91FCD1F"> Visitantes únicos </li> 
     <li id="li_000CA7680A0745D9860CA7D5F62288D4">Visitas </li> 
     <li id="li_53CAD3ECAE54451BBB0750FB62AF1243">Ocurrencias </li> 
     <li id="li_C589008CA92E4C69866E85EEEC88EF90"> Vistas de páginas </li> 
     <li id="li_ACF8D24E3AC746E280DB0F71D4B772A3">Métricas de A4T </li> 
     <li id="li_78BFE0A4F8024301A218C0415537F632">Métricas de tiempo empleado </li> 
     <li id="li_29774EEFE9A04759B7929EA35AA9BEAD">Devoluciones </li> 
     <li id="li_B163C6F24240465F85AB5C9792F0F013">Porcentaje de rebote </li> 
     <li id="li_CF065E227A634C77BC2C48C2A6EC849A">Entradas </li> 
     <li id="li_ED962C5063B047F185EFC58EB43C661F">Salidas </li> 
     <li id="li_029F6D09433F48A38303E5C96E77480B">Páginas no encontradas </li> 
     <li id="li_8410AF29208247B5B3E49F72208913BA">Búsquedas </li> 
     <li id="li_8421F1D5F58148D98B1AB5C04FCCA9CF">Visitas a una sola página </li> 
     <li id="li_50D4EA0FF2E6438C8DD2A1B2EAD7B9D7">Acceso único </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿En qué difiere Attribution IQ con respecto a la atribución en Data Workbench?</b> </p> </td> 
   <td colname="col2"> <p>R: Data Workbench ofrece cada vez más: </p> 
    <ul id="ul_5A8C979CDCD04FF5B9625C84B2678CC7"> 
     <li id="li_115DC58D4BDF40A4A0036E76F6E64158">La capacidad de atribuir a través de más fuentes de datos de nivel de visitante, como impresiones de anuncios y punto de venta. </li> 
     <li id="li_C31891A4D5594D93AF97340F6D3A2E3E">Modelado algorítmico (<a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html" format="html" scope="external">más adecuado</a>). Attribution IQ incluye modelos basados en reglas únicamente. </li> 
     <li id="li_749D5D11B34E40E9AB53908A38979CAA">Visualizaciones adicionales, como <a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html" format="html" scope="external">tablas de latencia </a>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Attribution IQ trabaja con orígenes de datos?</b> </p> </td> 
   <td colname="col2"> <p>R: Actualmente, Attribution IQ trabaja con orígenes de datos que no sean orígenes de datos de nivel de resumen. </p> <p> Debido a que los orígenes de datos de nivel de resumen no se vinculan a un identificador de visitante de Analytics, la atribución avanzada no es posible. Los orígenes de datos del ID de transacción también se admiten, excepto si se usan en un grupo de informes virtuales con <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">procesamiento de tiempo de informe</a> habilitado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: ¿Attribution IQ trabaja con la integración de <a href="https://marketing.adobe.com/resources/help/en_US/analytics/advertising/overview.html" format="html" scope="external">Advertising Analytics</a>?</b> </p> </td> 
   <td colname="col2"> <p>R: Las métricas integradas, que incluyen impresiones, costes, clics, posición media y puntuación de calidad media, son orígenes de datos de nivel de resumen y por lo tanto son incompatibles con Attribution IQ. Sin embargo, las dimensiones de metadatos (p. ej., tipo de coincidencia y palabra clave) funcionarán con la atribución cuando se usen con eventos o métricas de Analytics estándares. </p> </td> 
  </tr> 
 </tbody> 
</table>

