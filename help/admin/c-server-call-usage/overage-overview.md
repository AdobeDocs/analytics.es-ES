---
description: Información general sobre la funcionalidad de uso de llamadas al servidor de Adobe Analytics.
title: Información general sobre Uso de llamadas al servidor
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
translation-type: tm+mt
source-git-commit: b3ea538d0d6e6ebbbbd17871aacaed7527cf3976
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 99%

---


# Información general sobre Uso de llamadas al servidor

## ¿Por qué el control y las alertas de Uso de llamadas al servidor? {#section_060C29BF1D00444B85892AD1FCF55290}

Uso de llamadas al servidor de Adobe Analytics trata sus solicitudes de transparencia tanto en los datos de uso de llamadas al explorador como al servidor móvil. Permite acceder a:

* Un tablero de Uso de llamadas al servidor que registra sus datos de consumo de llamadas al servidor y lo compara con su límite contractual. (**[!UICONTROL Analytics > Admin > Uso de llamadas al servidor]**)
* Un tipo de alerta Uso de llamadas al servidor en el Generador de alertas que le permite configurar alertas para evitar sobrecargas (**[!UICONTROL Analytics > Componentes > Alertas]**)

Las principales ventajas de Uso de llamadas al servidor son las siguientes:

* **Visibilidad** del consumo de llamadas al servidor y los datos de asignación, incluyendo consumo móvil con respecto al límite contractual de uso de llamadas al servidor.
* **Alertas** para avisarle del riesgo o de la presencia de un cargo adicional para que pueda tomar las medidas oportunas.

Anteriormente, aunque podía acceder a los datos mensuales de consumo de llamadas al servidor en **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Facturación]**, estos solo se actualizaban 6 días después del cierre de la facturación para ese mes. Además, los datos no incluían el consumo móvil. Esta función también sustituirá el actual informe **[!UICONTROL Información de facturación]** en **[!UICONTROL Analytics]** > **[!UICONTROL Informes]**.

## Requisitos previos {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Permisos:** Para acceder al tablero de Uso de llamadas al servidor y al Generador/Administrador de alertas, debe ser administrador de Adobe Analytics.
* **Permisos:** Los administradores pueden conceder acceso a los no administradores. El permiso se llama **[!UICONTROL Uso de llamadas al servidor]**. Consulte [Permiso de Uso de llamadas al servidor](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369).

## Terminología importante {#section_CBA348A039F34563B097CD8890AB358D}

Este es un breve manual sobre terminología esencial para Uso de llamadas al servidor:

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Término </th> 
   <th colname="col2" class="entry"> Definición </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Llamada al servidor </p> </td> 
   <td colname="col2"> <p>Una llamada al servidor, también conocida como “visita individual” o “solicitud de imagen” es una instancia en la que se envían datos a servidores de Adobe para su procesamiento. El tipo más común de llamada al servidor es una vista de página. Se produce una vista de página cuando un visitante visualiza una página del sitio web y se genera una llamada al servidor para Adobe, que recopila la información, la procesa y luego la incluye en las métricas de informes. </p> <p>Existen otros tipos de llamadas al servidor, como vínculos de salida y descargas de archivos, en las que los datos se envían a Adobe para su procesamiento, pero no se registran como una nueva vista de página. Incluso las vistas de página “excluidas” (por ejemplo, excluidas de los informes mediante la configuración de un intervalo de direcciones IP) son llamadas al servidor, ya que Adobe las recibe y las procesa pero nunca las muestra en los informes. </p> <p><b>Llamada al servidor primaria</b>: solicitudes recibidas directamente desde los exploradores de los visitantes del sitio web o la API de inserción de datos. Incluye Visitas individuales primarias (Vistas de página), Eventos personalizados primarios, Eventos de descarga primarios y Eventos de salida primarios. </p> <p><b>Llamada al servidor secundaria</b>: copias de las llamadas al servidor primarias creadas mediante etiquetas de conjuntos múltiples, o copiadas o movidas a través de una regla de VISTA. Si se ha movido (no copiado) una llamada al servidor secundaria a un grupo de informes diferente a través de una regla de VISTA, las llamadas al servidor secundarias acumuladas se deducen de las llamadas al servidor primarias. </p> <p><b>Llamada al servidor primaria móvil</b> </p> <p>Solicitudes recibidas directamente de uno de los SDK para móviles. Incluya trackAction, trackState, trackApp Crashes, trackActionFromBackground, trackLocation, trackBeacon, trackPushMessageClickThrough, trackTimedActionBacklog, trackLifetimeValueIncrease.</p> <p><b>Llamada al servidor secundaria móvil</b> </p> <p>Copias de las llamadas al servidor primarias creadas mediante etiquetas de conjuntos múltiples, o copiadas o movidas a través de una regla de VISTA. Si se ha movido (no copiado) una llamada al servidor secundaria a un grupo de informes diferente a través de una regla de VISTA, las llamadas al servidor secundarias acumuladas se deducen de las llamadas al servidor primarias. </p> <p>Nota: Si su empresa está autorizada, de forma contractual, a realizar llamadas de Mobile Server (primarias o secundarias) únicamente, tanto el uso web como el específico de móvil contarán en su asignación específica de móvil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Empresa de facturación (ID de facturación) </p> </td> 
   <td colname="col2"> <p>La entidad legal a la que se facturan las llamadas al servidor. Por ejemplo, adobe.com. Cada empresa de facturación tiene un ID de facturación que se utiliza para identificar de forma exclusiva al cliente de facturación. Se puede asociar un ID de facturación a varias organizaciones de Experience Cloud; no siempre hay una relación 1:1 entre una organización y un ID de facturación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Empresa de inicio de sesión </p> </td> 
   <td colname="col2"> <p>Una empresa de facturación puede tener <a href="https://helpx.adobe.com/es/analytics/kb/multiple-login-companies.html">varias empresas de inicio de sesión </a>. Una empresa de inicio de sesión es una recopilación de grupos de informes que su organización utiliza. Algunas organizaciones tienen varias empresas de inicio de sesión que aplican a diferentes partes de la organización. Esto es especialmente útil en organizaciones grandes que trabajan con diferentes unidades de negocio y en las que muchos grupos de informes no sirven para otras personas de la empresa. </p> <p>A menudo, son subsidiarias regionales de una empresa. Este ejemplo muestra empresas de inicio de sesión y sus grupos de informes asociados: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide: RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>Nota: Los datos del uso de llamadas al servidor para <u>todos</u> los grupos de informes de una empresa de facturación son visibles para todos los usuarios con el <a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369">permiso</a> adecuado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organización de Experience Cloud </p> </td> 
   <td colname="col2"> <p>Una organización de es la entidad que permite a un administrador configurar grupos y usuarios, así como para controlar el inicio de sesión único en Experience Cloud. La organización funciona como una empresa de inicio de sesión que abarca todos los productos y soluciones de Experience Cloud. </p> <p>La mayoría de las veces, la organización es el nombre de empresa. Sin embargo, una empresa puede tener muchas organizaciones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Asignación de llamada al servidor </p> </td> 
   <td colname="col2"> <p>Cuando su empresa firma un contrato con Adobe, el equipo de ventas de Adobe identifica con usted, el cliente, los tipos (primaria, secundaria, primaria móvil, secundaria móvil) y el número aproximado de llamadas al servidor en las que espera incurrir durante el periodo contractual. Esta es su asignación de llamadas al servidor total. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Periodo de uso </p> </td> 
   <td colname="col2"> <p>Con fines de supervisión del uso de llamadas al servidor, esta asignación de llamadas al servidor total se desglosa en periodos de uso menores (como 3 meses) para facilitar las comparaciones anuales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Periodo contractual </p> </td> 
   <td colname="col2"> <p>Los periodos contractuales pueden ser de varios años. Digamos que su empresa tiene una asignación de llamadas al servidor de 6 millones de llamadas para un periodo contractual de 3 años. Con fines de supervisión del uso de llamadas al servidor, este periodo de 3 años se puede desglosar en periodos de uso menores para facilitar las comparaciones anuales. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Permiso de Uso de llamadas al servidor {#section_FCC58EB635954A32990D4E67B52B4369}

El permiso de Uso de llamadas al servidor se concede, de forma automática, a los administradores de Analytics. Permite a los usuarios ver el tablero y crear alertas de llamadas al servidor. Los administradores pueden elegir conceder este permiso a los no administradores.

>[!NOTE]
>
>Su empresa puede elegir qué empresas de inicio de sesión tienen acceso a Uso de llamadas al servidor.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre del permiso </th> 
   <th colname="col3" class="entry"> Conceder permiso si ha iniciado sesión en Adobe Analytics (inicio de sesión heredado) </th> 
   <th colname="col4" class="entry"> Conceder permiso si ha iniciado sesión en Adobe Experience Cloud </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Uso de llamadas al servidor </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">Inicie sesión en Analytics a través de sc.omniture.com. </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">Vaya a <span class="ignoretag"><span class="uicontrol">Admin</span> &gt; <span class="uicontrol">Administración de usuarios</span> &gt; <span class="uicontrol">Grupos</span> &gt; <span class="uicontrol">Editar todo el acceso a informes</span> &gt; <span class="uicontrol">Herramientas Analytics</span> &gt; <span class="uicontrol">Personalizar</span> &gt; <span class="uicontrol">Uso de llamadas al servidor</span></span>. </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">Inicie sesión en login.experiencecloud.adobe.com.</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">Haga clic en <span class="uicontrol">Analytics</span>. </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">Vaya a <span class="ignoretag"><span class="uicontrol">Productos</span> &gt; <span class="uicontrol">Product Profile</span> &gt; <span class="uicontrol">Permisos</span> &gt; <span class="uicontrol">Herramientas Analytics</span> &gt; <span class="uicontrol">Uso de llamadas al servidor</span></span>. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

