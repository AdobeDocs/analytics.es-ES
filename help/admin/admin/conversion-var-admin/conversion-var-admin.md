---
description: La variable de conversión de perspectiva personalizada (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados. Una eVar puede basarse en visitas y funcionar de modo similar a las cookies. Los valores pasados a las variables eVar siguen al usuario durante un período de tiempo predeterminado.
keywords: eVar
title: Variables de conversión (eVar)
feature: Admin Tools
uuid: 1eed0cb1-0735-4142-be21-43f264216b50
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1582'
ht-degree: 100%

---

# Variables de conversión (eVars)

La variable de conversión de perspectiva personalizada (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados. Una eVar puede basarse en visitas y funcionar de modo similar a las cookies. Los valores pasados a las variables eVar siguen al usuario durante un período de tiempo predeterminado.

Cuando una eVar está establecida en un valor para un visitante, Adobe recuerda automáticamente ese valor hasta que caduque. Cualquier evento de éxito que encuentra el visitante mientras la eVar está activa se cuenta hacia el valor eVar.

El mejor uso de las eVars es para medir causa y efecto, como:

* Qué campañas internas influyeron en los ingresos
* Qué anuncios de banner tuvieron como resultado final un registro
* El número de veces que se usó una búsqueda interna antes de realizar un pedido

Si se desea realizar la medición de tráfico o las rutas, se recomienda utilizar variables de tráfico.

>[!NOTE]
>
>Se puede guardar un solo valor único en una eVar de una solicitud de imagen. Si quiere que haya varios valores en un valor eVar, le recomendamos que implemente [Variables de lista](https://docs.adobe.com/content/help/es-ES/analytics/implementation/vars/page-vars/page-variables.html).

## Variables de conversión - Descripciones {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Descripciones de los campos utilizados al [editar variables de conversión](/help/admin/admin/conversion-var-admin/t-conversion-variables-admin.md).

<table id="table_E48D50926E6B492183300CA58A886927"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Elemento </p> </th> 
   <th colname="col2" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Nombre </span> </p> </td> 
   <td colname="col2"> <p>Nombre descriptivo de la variable de conversión. Así se le llama a la eVar en los informes generales, y será el nombre del informe que aparecerá en el menú de la izquierda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Tipo</span> </p> <p>(solo eVar) </p> </td> 
   <td colname="col2"> <p>Tipo del valor de la variable: </p> <p> <b>Cadena de texto</b>:</span> Registra los valores de texto que se usan en el sitio. Este es el tipo más común de eVar y el valor predeterminado. Actúa de forma similar a otras variables, donde el valor incluido dentro es una cadena de texto estático. Si está realizando un seguimiento de elementos como campañas internas o palabras clave de búsqueda interna, esta es la configuración recomendada. </p> <p> <b>Contador</b>:</span> Cuenta la cantidad de veces que se produce una acción antes del evento de éxito. Por ejemplo, si utiliza una eVar para seguir una búsqueda interna en el sitio, configure este valor en <span class="uicontrol">Cadena de texto</span> para rastrear el uso de los términos de búsqueda. Defina este valor en <span class="uicontrol">Contador</span> para contar la cantidad de búsquedas hechas, independientemente de los términos de búsqueda utilizados. Por ejemplo, puede usar una eVar de contador para rastrear el número de veces que alguien usó su búsqueda interna antes de realizar una compra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol">Asignación</span> </p> </td> 
   <td colname="col2"> <p>Determina la forma en la que Analytics asigna crédito por un evento de éxito si una variable recibe varios valores antes del evento. Los valores admitidos son: </p> <p> <b>Más reciente</b>: El último valor de la eVar siempre recibe el crédito por los eventos de éxito hasta que la eVar caduque. </p> <p> <b>Valor original</b>: La primera eVar siempre recibe crédito por los eventos de éxito hasta que la eVar caduque. </p> <p> <b> Lineal</b>: Asigna eventos de éxito de forma equitativa a través de todos los valores de la eVar. Debido a que la asignación lineal distribuye los valores de forma precisa solamente dentro de una visita, debe utilizar dicha asignación con una caducidad de visita para eVar. </p> <p>Nota: Si se cambia la asignación a Lineal o de Lineal, los datos históricos no se mostrarán. La combinación de tipos de asignación en la interfaz de informes puede llevar a una exposición incorrecta de los datos en los informes. Por ejemplo, la asignación Lineal puede dividir los ingresos entre un número de distintos valores de eVar. Después de volver a cambiar a la asignación Más reciente, el 100 % de esos ingresos se asociarán con el valor único más reciente. Esta asociación puede llevar a conclusiones incorrectas por parte de los usuarios. </p> <p>Para evitar confusión en los informes, Analytics impide que la interfaz tenga acceso a los datos históricos. Esos datos se pueden ver si decide cambiar de nuevo la eVar a su valor de asignación inicial, pero no debería cambiar ese valor simplemente para acceder a los datos históricos. Adobe recomienda usar una eVar nueva cuando se desee otra configuración de asignación para los datos ya registrados, en lugar de cambiar la configuración de asignación en una eVar que ya dispone de una cantidad importante de datos históricos creados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Caduca después de</span> </p> </td> 
   <td colname="col2"> <p>Especifica un período de tiempo o un evento tras el cual caduca el valor de la eVar (ya no recibe crédito por los eventos de éxito). Si se da un evento de éxito después de que caduque la eVar, el valor Ninguno recibe crédito por el evento (no había ninguna eVar activa). </p> <p>Si selecciona un evento como valor de caducidad, la variable caducará solamente si ocurre el evento. Si no ocurre el evento, la variable no caducará nunca. </p> <p>Las opciones de caducidad disponibles se pueden clasificar en cuatro categorías principales: </p> 
    <ul id="ul_810A37C9B6624F429F2FB45C18F7B43F"> 
     <li id="li_654D9D9044EC4E61AA7ABA372DBF8A93"><b>A nivel de visita o vista de página:</b> los eventos de conversión más allá de la vista de página o la visita no se asocian a la eVar. </li> 
     <li id="li_689FBC8B4DAC41B3B0166E6586DD1990"><b>En función de un período de tiempo como día, semana, mes o año:</b> los eventos de conversión que no entren en el período de tiempo especificado no se asocian a la eVar. El período de caducidad se inicia al configurar la variable. Las eVar caducan según la hora en la que se establecieron, hasta el nivel de los segundos (minuto, hora, día, mes, etc.): 
      <ul id="ul_80C7E3182B6B4356B8A3CA920B81C6D5"> 
       <li id="li_F16F60319CCE406D9EDEFEC0A200BC4D">MINUTO=60 segundos </li> 
       <li id="li_45F47F3F5691415B84052B235DF3BB54">HORA=3600 segundos (60 minutos) </li> 
       <li id="li_5288CE7D168E4C85B3D9BB67A44D32EC">DÍA=86 400 segundos (24 horas) </li> 
       <li id="li_60FC8BCD657745EE87B4E458CBA69583">SEMANA=60 4800 segundos (7 días) </li> 
       <li id="li_7A05A66613C84F929F030310B9567CF5">MES=2 678 400 segundos (31 días) </li> 
       <li id="li_DCD3CABF59E34D5999B03E606B08AD85">TRIMESTRE=8 035 200 segundos (93 días, 3 meses de 31 días) </li> 
       <li id="li_54351D2899454D39A8BA205910D2CCB1">AÑO=31 536 000 segundos (365 días) </li> 
      </ul> <p> </p> <p>Si una visita se inicia a las 7:00 AM un lunes y la eVar se establece en esa visita a las 7:15 AM, la caducidad se mostrará de esta forma: </p> 
      <ul id="ul_72B311006BE6428698313D251C0940DB"> 
       <li id="li_50925D4A40AD4ACA88704A523138C5B9">Caducidad de día: eVar caduca a las 7:15 AM del martes. </li> 
       <li id="li_25846328766D4B4BAF407236C65C956C">Caducidad de semana: eVar caduca el lunes que viene a las 7:15 AM. </li> 
       <li id="li_82DB2D7F53304623A5E1241D75C7DF94">Caducidad de mes: eVar caduca dentro de 31 días desde el lunes a las 7:15 AM. </li> 
      </ul> </li> 
     <li id="li_C132C5C5A5344B91BDF5EB6A1C717C37"><b>Eventos de conversión específicos:</b> cualquier otro evento de conversión que se active después de que el evento específico designado se asocie a la eVar. </li> 
     <li id="li_5A782D743FB940649E6CB3E4BEA9B8B6"><b>Nunca.</b> Mientras la cookie La cookie<span class="varname"> visitorID</span> está intacta. Puede pasar cualquier cantidad de tiempo entre la eVar y el evento. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Estado</span> </p> <p>(solo eVar) </p> </td> 
   <td colname="col2"> <p>Define el estado de la eVar: </p> <p><b>Desactivado</b>:</span> Desactiva la eVar. Quita la eVar de la lista de variables de conversión. </p> <p> <b>Sin subrelaciones</b>:</span> Evita que desglose la eVar con una subrelación. </p> <p> <b>Subrelaciones básicas</b>: </span>Le permite desglosar una eVar en cualquier informe con subrelaciones completas (por ejemplo, Productos o Campaign). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Restablecer</span> </p> </td> 
   <td colname="col2"> <p>Restaura todos los valores existentes en la eVar. </p> <p>Utilice esta configuración al reutilizar una eVar, para no mezclar los valores antiguos con los informes nuevos. El restablecimiento no borra los datos históricos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Comercialización</span> </p> <p>(solo eVar) </p> </td> 
   <td colname="col2"> <p>Las variables de comercialización pueden seguir una de dos sintaxis: </p> <p> <b>Sintaxis de productos</b>:</span> Asocia el valor de la eVar a un producto. Nota: Si la sintaxis de los productos se selecciona, la sección de Evento de enlace de comercialización se desactiva y no se puede seleccionar para la edición. Para esta sintaxis, los eventos de enlace no son aplicables. </p> </p> <p> <b>Sintaxis de variables de conversión</b>:</span> Asocia la eVar a un producto solamente si ocurre un evento de enlace. En este caso, usted selecciona los eventos que actúan como eventos de enlace. </p> <p>Si cambia este valor sin actualizar adecuadamente el código JavaScript, se perderán datos. Consulte <a href="https://docs.adobe.com/content/help/es-ES/analytics/components/variables/merchandising-variables/var-merchandising.html">Variables de comercialización</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Evento de enlace de comercialización</span> </p> <p>(solo eVar) </p> </td> 
   <td colname="col2"> <p>Si la comercialización está configurada como <span class="uicontrol">Sintaxis de variables de conversión</span>, los eventos seleccionados relacionarán el valor eVar con un producto. </p> <p>Para utilizar un evento de enlace, establezca <span class="uicontrol">Asignación en Más reciente</span>. Si la <span class="uicontrol">Asignación es el Valor original</span>, el primer enlace de producto de la eVar se mantendrá hasta que caduque la eVar. Para seleccionar varios eventos, mantenga presionada la tecla <code>ctrl</code> (Windows) o <code>cmd</code> (Mac) y haga clic en los distintos elementos de la lista. Solo puede seleccionar eventos si también se selecciona la opción "Sintaxis de la variable de conversión".</p> </td> 
  </tr> 
 </tbody> 
</table>

**Caducidad**

Las `eVars` caducan después del período de tiempo que especifique. Cuando la eVar caduca, ya no recibe el crédito por los eventos de éxito. Las eVars también se pueden configurar para que caduquen cuando se produzcan eventos de éxito. Por ejemplo, si tiene una promoción interna que caduca el final de una visita, la promoción interna recibe el crédito solo por las compras o registros que se produzcan durante la visita en la que se activaron.

Hay dos maneras de que una eVar caduque:

* Puede configurar la eVar para que caduque después de un período de tiempo o evento especificados.
* Puede forzar la caducidad de una eVar al restablecerla, lo que resulta útil cuando se cambia el propósito de una variable.

Por ejemplo, si cambia la caducidad de una eVar de 30 a 90 días, los valores de la eVar recopilados persistirán durante el nuevo conjunto de caducidad (en este caso, 90 días). El sistema simplemente observa la configuración de caducidad actual y la última marca de tiempo establecida del valor de eVar obtenido para determinar la caducidad. Solo la opción **[!UICONTROL Restablecer]** caduca los valores y lo hace de inmediato.

Otro ejemplo: si se usa una eVar en mayo para reflejar promociones internas y caduca después de 21 días, y en junio se usa para capturar palabras clave de búsqueda interna, el 1 de junio, debe forzar la caducidad o restablecer la variable. Al hacerlo, no se incluyen los valores de la promoción interna en los informes de junio.

**Distinción entre mayúsculas y minúsculas**

Las eVars no distinguen entre mayúsculas y minúsculas, pero se muestran en la escritura en mayúsculas de la primera aparición. Por ejemplo, si la primera instancia de eVar1 es &quot;Sesión iniciada&quot; pero todas las demás instancias se pasan como &quot;sesión iniciada&quot;, los informes siempre mostrarán &quot;Sesión iniciada&quot; como valor de eVar.

**Contadores**

Aunque las eVars se usan habitualmente para guardar valores de cadena, también se pueden configurar para que actúen como contadores. Las eVars son útiles como contadores para contar el número de acciones que un usuario realiza antes de un evento. Por ejemplo, puede usar una eVar para capturar el número de búsquedas internas antes de la compra. Cada vez que un visitante realiza una búsqueda, la eVar debe contener un valor de &#39;+1&#39;. Si un visitante realiza cuatro búsquedas antes de una compra, verá una instancia con cada recuento total: 1.00, 2.00, 3.00 y 4.00. Sin embargo, solo el valor 4.00 recibe el crédito por el evento purchase (métricas de pedidos e ingresos). Solo se permiten números positivos como valores de un contador eVar.
