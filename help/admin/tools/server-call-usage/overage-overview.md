---
description: Información general sobre la funcionalidad de uso de llamadas al servidor de Adobe Analytics.
title: Información general sobre Uso de llamadas al servidor
feature: Server Call Usage
exl-id: d3d64f1e-f01b-4b9e-9aee-c14e574fc40b
role: Admin
TQID: https://experienceleague.adobe.com/-IIz9r-K-flZq85Dz3lhYuo9-Ko0zt0KoJJ7DtI5Mz4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 93678f75cac9b513282a1e4d61276d7617fc933e
workflow-type: tm+mt
source-wordcount: 887
ht-degree: 77%

---

# Uso de llamadas al servidor

El uso de llamadas al servidor de Adobe Analytics responde a sus solicitudes de transparencia tanto en los datos de uso de llamadas al explorador como al servidor móvil. Permite acceder a:

* Un tablero de uso de llamadas al servidor que registra sus datos de consumo de llamadas al servidor y lo compara con su límite contractual. (En Adobe Analytics, seleccione > [!UICONTROL **Admin**] > [!UICONTROL **Uso de llamadas al servidor**])
* Tipo de alerta de uso de llamadas al servidor en el generador de alertas que le permite configurar alertas para evitar sobrecargas (en Adobe Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Alertas**])

Las principales ventajas del uso de llamadas al servidor son las siguientes:

* **Visibilidad** del consumo de llamadas al servidor y los datos de asignación, incluyendo consumo móvil con respecto al límite contractual de uso de llamadas al servidor.
* **Alertas** para avisarle del riesgo o de la presencia de un cargo adicional para que pueda tomar las medidas oportunas.

## Requisitos previos {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Permisos:** Debe tener acceso de administrador de Adobe Analytics o el elemento de permiso [Uso de llamadas al servidor](/help/admin/admin-console/permissions/analytics-tools.md) en Adobe Admin Console. Los administradores pueden asignar este elemento de permiso a los no administradores a través de un perfil de producto.

## Terminología importante {#terminology}

Los siguientes términos son importantes para comprender el uso de llamadas al servidor:

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
   <td colname="col2"> <p>La entidad legal a la que se facturan las llamadas al servidor. Por ejemplo, adobe.com. Cada empresa de facturación tiene un ID de facturación que se utiliza para identificar de forma exclusiva al cliente de facturación. Se puede asociar un ID de facturación a varias organizaciones empresariales de CX; no siempre hay una relación 1:1 entre una organización y un ID de facturación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inicio de sesión de la empresa </p> </td> 
   <td colname="col2"> <p>Una empresa de facturación puede tener <a href="https://helpx.adobe.com/es/analytics/kb/multiple-login-companies.html">varias empresas de inicio de sesión </a>. Una empresa de inicio de sesión es una recopilación de grupos de informes que su organización utiliza. Algunas organizaciones tienen varias empresas de inicio de sesión que aplican a diferentes partes de la organización. Esto es especialmente útil en organizaciones grandes que trabajan con diferentes unidades de negocio y en las que muchos grupos de informes no sirven para otras personas de la empresa. </p> <p>A menudo, son subsidiarias regionales de una empresa. Este ejemplo muestra empresas de inicio de sesión y sus grupos de informes asociados: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide: RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>Nota: Los datos del uso de llamadas al servidor para <u>todos</u> los grupos de informes de una empresa de facturación son visibles para todos los usuarios con el <a href="/help/admin/admin-console/permissions/analytics-tools.md">permiso</a> adecuado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CX Organización empresarial </p> </td> 
   <td colname="col2"> <p>Una organización es la entidad que permite a un administrador configurar grupos y usuarios, así como controlar el inicio de sesión único en CX Enterprise. La organización funciona como una empresa de inicio de sesión que abarca todos los productos y soluciones de CX Enterprise. </p> <p>La mayoría de las veces, la organización es el nombre de empresa. Sin embargo, una empresa puede tener muchas organizaciones. </p> </td> 
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
