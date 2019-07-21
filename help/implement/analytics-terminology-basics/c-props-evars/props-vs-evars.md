---
description: En Experience Cloud hay varios tipos de variables disponibles. Los dos tipos más populares, props y eVars, permiten a la organización obtener informes sobre dimensiones personalizadas del sitio que los informes predeterminados estándar no ofrecen.
keywords: Implementación de Analytics; prop; evar; props vs evars; convención de nombre; variables de tráfico; persistencia; evento de éxito; rutas
seo-description: En Experience Cloud hay varios tipos de variables disponibles. Los dos tipos más populares, props y eVars, permiten a la organización obtener informes sobre dimensiones personalizadas del sitio que los informes predeterminados estándar no ofrecen.
seo-title: Comparación de props y eVars
solution: Analytics
title: Comparación de props y eVars
topic: Desarrollador e implementación
uuid: 0 f 02760 f-ff 69-481 c-a 817-799 f 02 dafe 8 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Comparación de props y eVars

En Experience Cloud hay varios tipos de variables disponibles. Los dos tipos más populares, props y eVars, permiten a la organización obtener informes sobre dimensiones personalizadas del sitio que los informes predeterminados estándar no ofrecen.

Para determinar qué variables se asignan y dónde, es importante conocer las diferencias entre la funcionalidad prop y eVar. Entender estas diferencias permite a la organización decidir qué tipo de variable es mejor utilizar. 

**Props vs. eVars**

A continuación se indican las principales diferencias entre props y eVars:

* **Nomenclatura de nombres**: las props se consideran variables de tráfico, lo que significa que se utilizan para informar de la popularidad de varias dimensiones del sitio. Las eVars se consideran variables de conversión. Se utilizan para determinar las dimensiones del sitio que contribuyen a lograr un mayor número de eventos de éxito.
* **Persistencia**: las props no persisten más allá de la solicitud de imagen en la que se activaron. No se pueden asociar a otras variables que no estén en la misma solicitud de imagen. Las eVars, por el contrario, son persistentes. Una variable de back-end se usa para conservar el valor originalmente activado para que así se pueda asociar posteriormente a eventos de éxito.
* **Eventos de éxito**: los eventos de éxito, también conocidos como eventos de conversión, son métricas que miden el número de veces que un visitante alcanza un objetivo. Este evento puede ser cualquier cosa, desde la compra de algún artículo en el sitio hasta la suscripción a un boletín. Las eVars están diseñadas para informar sobre eventos de conversión y mostrar qué valores tienen más éxito en cuanto a la influencia que ejercen sobre los visitantes para alcanzar los objetivos. Las variables de tráfico no tienen esta misma funcionalidad. No obstante, podrá ver las métricas de participación si configura correctamente su grupo de informes.
* **Rutas**: las props pueden usar rutas, lo que permite a su organización ver la ruta que un usuario toma dentro del contexto de la variable que se está visualizando. Si se solicita, los representantes de Adobe pueden activar las rutas. Las eVars no pueden usar las rutas.
* **Métricas disponibles potencialmente**: las métricas disponibles entre props y eVars varían ampliamente en función de la configuración de la variable y la versión o plataforma de los datos. La siguiente lista ilustra lo que se puede activar, no lo que está activado de forma predeterminada. Si no se encuentra una métrica determinada que debe aparecer en los informes, un usuario de asistencia técnica de la organización debe ponerse en contacto con el Servicio de atención al cliente.

<table id="table_FB963F60857A4AD79562324FB6F4B6A9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Métrica </p> </th> 
   <th colname="col2" class="entry"> <p>Props </p> <p>(Variables de tráfico) </p> </th> 
   <th colname="col3" class="entry"> <p>eVars </p> <p>(Variables de conversión) </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Profundidad promedio de la página </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_165C1BF1574247CEA9190ADCABF79D69" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tiempo promedio empleado </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_9F0F396E11B442959EC3E5D4D508496D" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tasa de salida hacia otro sitio </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_A268EAF747EA45F8A6A93A1B66667A06" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_09D486144CEA4293A505DCA3F90B82EC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Devoluciones </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_471A02B78FD842BB97ED3FF4A5908B03" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D2F11B5687484D9EBF6D1DEB3F303A20" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métricas calculadas </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_7FAB1CF2ACC44D9198C648D3FC9E52D9" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8BCC2EE92CC04778809D1BD48D2623D7" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eventos de conversión personalizados </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D75C764B83AE4491A7E68C459FED1300" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Entradas </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E9A1FCDFCB924D75ABFAEBD5570D4EE0" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5E57974B5A64F3FA3A145428420EB23" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salidas </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_BE343F94EAD74D54B6ABC80E8A76A9BD" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_3183B2BB62C24B048EDED3295F2BEC85" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Instancias </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8733F5AC189E43DAA8D1847416EA68C8" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_B10AB2898F3D4EBA947FADB27B118143" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vistas de páginas </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8BD2B23FBDA64A648BED40A2993F7C1C" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_CBDFD74340FA4973847033C1F956F0AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métricas de participación </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E63F978830FB46809E62654F37C4C182" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_6AB756A4598F4452887D29AD4971985A" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métricas de compra </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8F8AB7CD02764245BA73CA1E6B69BAE1" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recargas </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_FBE0C84E01004937B7B408198A33A9E7" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métricas de carrito de la compra </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_123993465D734EABB311730ED03263F6" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Acceso único </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_038C6991E3F341B18E7A355D17C88895" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tiempo total empleado </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_090587D29F1649319033D5A15B34B138" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_841DF09FD32A44B1B1B876F4E0CE29AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visitantes únicos </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_38556E6A43B04E2E8A01855452D30A83" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5D4BDE1AA9C4C58A6402418390EEC52" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visitas </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_017BB279C5824028870360A5D4D27556" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

* **Desgloses**: las props utilizan correlaciones, que muestran las vistas de páginas de otras variables de tráfico activadas en la misma solicitud de imagen. Las eVars utilizan subrelaciones, que proporcionan un desglose en otras variables de conversión en relación a eventos de éxito.

## Ventajas exclusivas para Props o eVars {#section_B384031AB8674065BA5187B0A3A3DAB9}

Con el lanzamiento de la versión 15, las funciones de Props y eVars han reducido sus diferencias. Las eVars recientemente han sido actualizadas para incluir funciones como visitas/visitantes únicos con una carga de procesamiento mínima, así como métricas de ruta.

Las Props tienen un par de ventajas con respecto a las eVars, algunas de las cuales pueden eludirse:

* Los datos de Prop se recopilan y están disponibles para los informes de forma casi instantánea. Las eVars pueden necesitar hasta más de 30 minutos para aparecer en los datos de un grupo de informes.
* Todas las Props pueden tener informes como diagramas de flujo activados, lo cual le permite ver la ruta que toman los visitantes en su sitio. These pathing flow reports are available for both Props and eVars in [!UICONTROL Ad Hoc Analysis].
* Las Props pueden correlacionarse en varios niveles, mientras que las eVars solo pueden subrelacionarse una vez. Esta limitación puede mitigarse mediante el uso de la segmentación, que proporciona los mismos datos que las correlaciones.
* Las métricas de participación le permiten ver qué valores de propiedad han participado antes del evento de éxito.

Las eVars, por otro lado, pueden tener distintas ventajas con respecto a la naturaleza limitada de las Props:

* Las eVars pueden utilizar eventos de éxito como métricas. Las Props no pueden.
* La caducidad de las eVars puede personalizarse, incluido tener una caducidad por cada visita (sin valores persistentes en absoluto). Las Props no son persistentes de ningún modo.

Las métricas de ruta, como el tiempo total empleado, las entradas y las salidas, originalmente no estaban disponibles para las eVars. Sin embargo, actualizaciones recientes han hecho que estas métricas estén disponibles, lo cual aumenta el valor de las eVars.

## Qué utilizar {#section_022D016A4EEB45179A15BFF044A261A4}

**Props:** si la latencia es la principal preocupación y solo tiene intención de medir el tráfico (no los eventos de éxito) con esta dimensión.

**eVars:** si el desglose y las relaciones de los datos son las principales preocupaciones.

>[!TIP]
>
>Si no desea que se mantenga una evar, puede cambiar su caducidad a'visita'para que no mantenga ningún dato más allá de la visita.

