---
description: Complete los pasos de la integración de Data Connectors DFA.
seo-description: Complete los pasos de la integración de Data Connectors DFA.
seo-title: Configurar la integración de DFA
title: Configurar la integración de DFA
uuid: 4 c 2 ac 58 a -87 c 6-46 f 3-9033-9404 beb 18 c 39
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configurar la integración de DFA{#configure-the-dfa-integration}

Complete los pasos de la integración de Data Connectors DFA.

Las páginas de configuración proporcionan información general sobre la integración, junto con vínculos útiles para obtener más información. Existen tarifas de Adobe como DoubleClick asociadas con esta integración. Póngase en contacto con los Representantes de ventas correspondientes para ambas organizaciones y asegúrese de comprender la estructura de tarifas.

1. Log in to the [!DNL Adobe Analytics].
1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Connectors]**.

   ![](assets/data_connectors.png)

1. Locate **[!UICONTROL DoubleClick DFA]**, then click **[!UICONTROL Add New]**.

   ![Resultado de los pasos](assets/wizard-01.png)

   En cada página del Asistente para integración, proporcione la información requerida y haga clic en **[!UICONTROL Siguiente]**. La siguiente tabla explica la información necesaria para completar la integración mediante el asistente.

<table id="table_8F6F7F304C36431DA5FD6E5D54F60FC0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Número de página del asistente </th> 
   <th colname="col2" class="entry"> Campo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Nombre de la integración </td> 
   <td colname="col3"> El nombre de la integración que Genesis muestra en la Lista de integración activa en el grupo de informes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Integración de dirección de correo electrónico </td> 
   <td colname="col3"> La dirección de correo electrónico que recibe todas las notificaciones relacionadas con esta integración. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Nombre de usuario </td> 
   <td colname="col3"> El nombre de usuario de la API DFA para usar con esta integración. Para habilitar un usuario para el inicio de sesión de API, consulte el atributo API en la interfaz DFA. Después de habilitar el inicio de sesión de API, aparece un campo de contraseña para proporcionar una contraseña para el usuario. Esta contraseña se introduce junto con el nombre de usuario en el asistente para la autenticación. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Contraseña </td> 
   <td colname="col3"> La contraseña de la API DFA. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> ID del anunciante </td> 
   <td colname="col3"> <p>El ID del anunciante de DFA o el ID de configuración de Floodlight principal. Los Data Connectors usan este ID para identificar el anunciante DFA para rastrear (versión 1.5 de la integración). Este ID del anunciante no se utiliza en la versión 2.0 de la integración. Se buscará y usará el ID de configuración de Floodlight principal. Consulte las instrucciones en pantalla. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> Variable de anuncio DFA </td> 
   <td colname="col3"> La eVar de Analytics que recibe datos de atributo, impresiones y clics de campaña DFA. Generalmente, es la eVar de código de seguimiento ( <span class="varname"> s. campaign </span>), pero puede elegir cualquier evar disponible. Data Connectors también agrega las siguientes clasificaciones relacionadas con DFA a la eVar seleccionada: <p><b>Campañas</b>: una recopilación de anuncios publicados en varios sitios que transmiten mensajes en común. </p> <p><b>Nombre del sitio</b>: el sitio en el que se publicó el anuncio. </p> <p><b>Nombre del anuncio</b>: el nombre del anuncio, según se define en la cuenta DFA. </p> <p><b>Nombre de la ubicación del sitio</b>: el sitio y la página web donde se publicó el anuncio. </p> <p><b>Herramienta de entrega</b>: DoubleClick para Anunciantes. </p> <p><b>Canal</b>: anuncio de tipo titular. </p> <p><b>Estructura de costes</b>: CPM, CPC o Fijo en función de la estructura de costes del anuncio. </p> <p><b>Nombre creativo</b>: el nombre del creativo asociado con un ID de anuncio/ubicación/creativo. </p> <p><b>DFA &gt; Anulación de duplicación de SearchCenter</b>: especifica que el DFA debería colocar valores en variables de Searchcenter cuando se generan pulsaciones o visualizaciones de DFA. Para obtener más información, consulte <a href="../../dfa-data-connector-analytics/dfa-integration-features.md#concept-ff93289d1662410e98f62c200394b3e3" format="dita" scope="local">Anulación de duplicación de SearchCenter</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Impresiones </td> 
   <td colname="col3"> El evento personalizado que recibe datos de métricas de Impresiones de DFA. Las impresiones indican la cantidad de veces que se publicó el anuncio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Clics </td> 
   <td colname="col3"> Seleccione el evento personalizado que recibe datos de métricas de clics de DFA. Los clics indican la cantidad de veces que los visitantes hicieron clic en el anuncio según las mediciones del redireccionamiento de DFA. La métrica de clics se correlaciona con la métrica de pulsaciones de Analytics. <p>Nota: Los clics de DFA y las pulsaciones de Analytics podrían no coincidir exactamente debido a diferencias en la forma en que se recopilan los datos. For more information, see <a href="../../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-metric-definitions.md#concept-2d5cd5ddd2594bb386a16a2764f30982" format="dita" scope="local"> Metric Definitions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Variable de visualización </td> 
   <td colname="col3"> <p>La eVar de Analytics que recibe datos de visualización de DFA. La variable de visualización le ayuda a ver cómo las visualizaciones afectan a las tasas de conversión en su sitio. </p> <p>Data Connectors agrega las mismas clasificaciones relacionadas con DFA a esta eVar tal como a la variable de anuncio DFA (consulte más arriba). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Tiempo desde la última vista (variable de bloque de tiempo de visualización) </td> 
   <td colname="col3"> La eVar de Analytics que recibe datos de Tiempo desde la última vista DFA. El Tiempo desde la última vista indica la cantidad de tiempo que ha transcurrido desde la última visualización de visualización de anuncio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Visualizaciones </td> 
   <td colname="col3"> El evento personalizado que recibe datos de métricas de visualizaciones de DFA. Use el evento visualizaciones con la variable de visualización para ver qué campañas no influenciaron una pulsación directa, pero pueden haber participado en direccionar tráfico al sitio en algún momento posterior. <p>Data Connectors cambia el nombre del evento personalizado seleccionado a “Visualizaciones”. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Error en consulta DFA  </td> 
   <td colname="col3"> (Opcional) La eVar de Analytics que recibe códigos de mensajes de error de consultas DFA que se han notificado. Algunos códigos posibles de mensajes DFA son: 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>: sin cookie DoubleClick. </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b>: el usuario no ha optado. </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>: sin historial de campaña. </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>: error de consulta (tiempo de espera, servidor caído, etc.). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Evento de tiempo de espera </td> 
   <td colname="col3"> <p>El Evento de contador de Analytics que se incrementa cada vez que caduca el temporizador <span class="varname"> El </span> temporizador s. maxdelay caduca y no se recibió respuesta de los servidores DFA. Use this event to configure the <span class="varname"> s.maxDelay </span> variable (see <a href="../../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d" format="dita" scope="local"> Tuning s.maxDelay </a>.) </p> </td> 
  </tr> 
 </tbody> 
</table>

