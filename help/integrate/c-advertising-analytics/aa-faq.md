---
description: Preguntas frecuentes sobre Advertising Analytics.
title: Preguntas más frecuentes sobre análisis de publicidad
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
source-git-commit: 591b82e271cc7474e9b413015804d4fe37d9050c
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 50%

---

# Preguntas frecuentes 

## Acceso y derechos {#access}

+++ ¿Debo ser cliente de Adobe Advertising Cloud o Adobe Advertising Cloud (AMO) para acceder a esta funcionalidad?

No, esta funcionalidad está disponible para clientes que no son de Advertising Cloud ni de AMO. </p> <p>Los clientes de AMO pueden aprovechar la integración Analytics-AMO existente; no podrán utilizar Ad Analytics.

+++

+++ ¿Qué SKU de Adobe Analytics dan derecho a utilizar Advertising Analytics?

Advertising Analytics está disponible para Adobe Analytics

* [Seleccionar](https://www.adobe.com/es/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/es/data-analytics-cloud/analytics/prime.html)

* [Ultimate](https://www.adobe.com/es/data-analytics-cloud/analytics/ultimate.html)

+++

+++ ¿Tengo que pagar un extra para usar Advertising Analytics?

No, Advertising Analytics no incurre en ningún coste adicional si no está aprovisionado correctamente.

+++

+++ ¿Advertising Analytics cuenta para mi uso de llamadas al servidor?

No, Advertising Analytics utiliza un tipo de fuente de datos especial que no incurre en costes de llamadas al servidor.

+++

+++ Si ya utilizo Advertising Cloud/AMO, ¿puedo seguir utilizando la funcionalidad de Advertising Analytics?

Cualquier cuenta de motor de búsqueda compatible pasará a Advertising Analytics y se mostrará como de solo lectura. Todas las modificaciones o actualizaciones deben controlarse en Advertising Cloud/AMO.

+++

+++ Tengo el SKU correcto, pero no puedo acceder a Advertising Analytics, ¿por qué?

Advertising Analytics solo está disponible para administradores de Adobe Analytics; sin embargo, los administradores pueden otorgar acceso a los usuarios que no sean administradores. Póngase en contacto con su administrador para obtener información sobre los derechos de acceso.

+++

## Uso de Advertising Analytics {#using}

+++ ¿Qué cuentas de motor de búsqueda se incluyen en Advertising Analytics?

Las cuentas de motor de búsqueda incluyen Google AdWords y Microsoft Bing.

+++

+++ ¿Dónde debo ir para acceder a Advertising Analytics?

Después de iniciar sesión en Adobe Analytics, vaya a [!UICONTROL Administrador]. A continuación seleccione [!UICONTROL Advertising Analytics] para agregar las cuentas de motor de búsqueda.

+++

+++ ¿Cómo se recopilan y pasan los datos a Analytics?

Advertising Analytics utiliza una serie de API personalizadas para pasar datos de los motores de búsqueda a Analytics a través de Adobe Advertising Cloud.

+++

+++ ¿Qué datos de búsqueda obtengo con esta integración?

Obtendrá lo siguiente

* Impresiones
* Clics
* Costos
* Puntuación de calidad
* Posición promedio directamente de los motores de búsqueda, así como
* Instancias de ID de AMO (instancias de clic).

+++

+++ ¿Puedo desglosar mis datos de Advertising Analytics con otros datos de Analytics (métricas/dimensiones)?

No, los datos de búsqueda sin procesar se incluirán como un conjunto de datos independiente. Sin embargo, hay una versión de Instancias de los datos de clics que se puede desglosar en otros datos de Analytics.

+++ ¿Cuál es la definición de los distintos indicadores de estado de mis cuentas (pendiente, activo, en pausa, etc.)? Cada uno de estos indicadores de estado identifica la fase del ciclo vital de la cuenta de cada motor de búsqueda.

* [!UICONTROL Pendiente]
* [!UICONTROL En pausa] significa que la cuenta se ha configurado anteriormente, pero se ha puesto en un estado inactivo.
* [!UICONTROL Activa] significa que la cuenta se ha configurado completamente y se utiliza para obtener datos de búsqueda.

+++

+++ Estoy intentando asignar mis cuentas de Advertising Analytics a un grupo de informes específico, pero no está disponible en el modal del grupo de informes. ¿Por qué?

Antes de poder asignar un grupo de informes a una cuenta de Advertising Analytics, el grupo de informes en cuestión debe estar [aprovisionado para informes de Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)
Esto se realiza a través de una página de Administración independiente a la que se puede acceder desde: Administración > Grupos de informes > [seleccionar grupo de informes] > Editar configuración > Configuración de Advertising Analytics.

+++

+++ ¿Es posible asignar un grupo de informes virtuales a una cuenta de Advertising Analytics?

Los grupos de informes virtuales no recopilan datos, por lo que no puede asignar directamente una cuenta de Advertising Analytics a un grupo de informes virtuales. Sin embargo, puede asignar la cuenta de Advertising Analytics al grupo de informes principal del grupo de informes virtuales en el que desea ver los datos. Es posible que las métricas del motor de búsqueda (clic/coste/impresiones) no se muestren en el grupo de informes virtual a menos que incluya una condición &quot;o&quot; en la lógica del segmento basada en el ID de AMO (o en su clasificación). Ejemplo: Agregar “todas las visitas donde exista un ID de AMO” incluiría en el segmento las métricas del motor de búsqueda.

+++

+++ ¿Se pueden registrar las métricas de Advertising Analytics en la <b>Canales de marketing</b> ¿reportar?

No, no se incluyen en el informe Canales de marketing.

+++

+++ ¿Cuándo obtiene Analytics los datos de búsqueda?

Los datos de búsqueda se obtienen de los motores de búsqueda alrededor de las 6:00 en la zona horaria de su centro de datos de Analytics. Este es el momento en que los datos de AMO se recopilan y se insertan en el grupo de informes. A continuación, se convierten a la zona horaria del grupo de informes como parte del proceso de inserción de los datos en Analytics.

+++

+++ Qué puede ser <b>capturado antes del clic</b>? ¿Obtenemos impresiones, costes, posiciones medias, etc. incluso sin el clic? </p> </td>

El ID de AMO registrará las métricas del motor de búsqueda: impresiones, costes, clics, posición media y puntuación de calidad media. Si no hay clics, pero hay impresiones, los datos de impresión, posición y calidad se enviarán a Analytics. Normalmente, si no hay clics, tampoco hay costes.

+++

+++ ¿A qué nivel se capturan estos datos? <b>¿Una visita? Visita individual?</b>

Las métricas del motor de búsqueda se capturan en el nivel de la visita y se conectan al ID de AMO (y a sus clasificaciones). Son datos del nivel de resumen, y no están relacionados con los visitantes ni sus sesiones. Por este motivo, las métricas del motor de búsqueda solo se pueden usar en segmentos que estén dentro del ámbito del nivel de visita y se basan en el ID de AMO, o sus clasificaciones.

El ID de AMO también se captura en la página de aterrizaje, en la visita de la página (que lo conecta al visitante y a su sesión), y se conserva en el sitio web para obtener crédito para otras métricas de Analytics hasta que caduque o un nuevo ID de AMO lo sobrescriba. Está totalmente incorporado al conjunto de datos como cualquier otro elemento eVar.

+++

+++ ¿Solo capturamos google.com o <b>versiones de países</b> (como google.co.uk, google.it, google.fr o google.de) también?

La clasificación de la Plataforma de publicidad registra estos valores: &quot;Google AdWords&quot; y &quot;Bing Ads&quot;. Una recomendación habitual es incluir el código de país como parte del nombre de las campañas. A continuación, puede filtrarlas o segmentarlas (por ejemplo, si todas las campañas empiezan por códigodepaís_, el hecho de crear un segmento en el que las campañas (ID de AMO) empiecen por “UK_” solo le proporcionaría datos para el Reino Unido).

+++

+++ La métrica &quot;Coste de AMO&quot; es el coste pagado por cada palabra clave o anuncio según la información del motor de búsqueda. ¿Es el coste neto o el bruto?

&quot;Coste de AMO&quot; es solo el coste pagado a los motores de búsqueda. No incluye ninguna tasa de agencia, optimización de búsqueda ni plataforma de gestión.

+++

+++ ¿Hay planes para incluir otros canales publicitarios como <b>Mostrar</b> o <b>Social</b>?

No, actualmente no tenemos planes para estos otros canales en la hoja de ruta.

+++


## Seguimiento automático frente al manual {#section_7437C4698A6D482EB7ED94A948390119}

<table id="table_9738FF8459574ED2937A860A665BE739"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta </th> 
   <th colname="col2" class="entry"> Respuesta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>P: Al configurar la cuenta de Advertising, se indica que el uso de <b>Seguimiento automático</b> puede tener consecuencias imprevistas. ¿Qué tipos de consecuencias se pueden producir? </p> </td> 
   <td colname="col2"> <p>R: 
     <ul id="ul_59EFF4A2ECE947EBBDB6A9FF6D072FE0"> 
      <li id="li_8731E4B7D6ED4F0996B3630A35D5BAC4">El modo automático intentará añadir los parámetros de la dirección URL al final de las plantillas de seguimiento o de las direcciones URL de destino en el formato correcto. <b>Sin embargo, usted es responsable de garantizar que los parámetros de la dirección URL añadidos se conserven correctamente en la página de aterrizaje final. </b> </li> 
      <li id="li_1202FE1FC88342378A60E8FE65E5426B">El modo automático puede insertar palabras clave en la dirección URL de aterrizaje, pero es posible que el servidor web no admita palabras clave con caracteres especiales. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>P: Si configuro en un primer momento el seguimiento automático o manual, <b>¿puedo cambiar</b> al otro modo más adelante? ¿Qué implicaciones hay? </p> </td> 
   <td colname="col2"> <p>R: Sí, puede cambiar, pero antes deberá eliminar la antigua lógica de seguimiento. El resultado puede ser que se ralentice el seguimiento el día en que se realice el cambio (especialmente si se pasa de manual a automático). Por todo ello, se recomienda no hacer este cambio salvo que sea absolutamente necesario. </p> 
    <ul id="ul_3F3CADD1C97B4947A13837CEE63A599D"> 
     <li id="li_CB9265951FD040388AEAB9EAD790A36E"><b>Cambio de Manual a Automático</b>: quite las adiciones manuales hechas en las plantillas de seguimiento y, a continuación, en la interfaz de usuario de Advertising Analytics, cambie el conmutador de Manual a Automático. Después, guarde la configuración. Tenga en cuenta que el sistema puede tardar hasta x horas en rellenar los códigos de seguimiento automático. </li> 
     <li id="li_2B6ED1342E2D443B8AF26D03532AB8E4"><b>Cambio de Automático a Manual</b>: en la interfaz de usuario de Advertising Analytics, cambie el conmutador de Automático a Manual y después implemente lo más rápido posible los códigos de seguimiento manual. Si mientras implementa los códigos de seguimiento manual ve los códigos de seguimiento automático en las plantillas de seguimiento del motor de búsqueda, elimínelos. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
