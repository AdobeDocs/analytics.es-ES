---
description: Lista de las métricas estándar de Adobe Analytics.
seo-description: Lista de las métricas estándar de Adobe Analytics.
seo-title: Métricas referencia rápida
solution: Analytics
title: Referencia rápida de métricas
topic: Métricas
uuid: 34160 c 96-7 cb 3-4 e 2 f -9956-9 ffa 9 d 9 a 359 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Referencia rápida de métricas

Lista de las métricas estándar de Adobe Analytics.

>[!NOTE]
>
>Any metric (event) not listed below is a [custom metric](../../../components/c-variables/c-metrics/metrics-custom.md#concept_F44638FC95A44B06AEBA3A6F9D008D27) (event).

<table id="table_CF4480B640BD4C81B4B32121FED5C96A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre de la medida </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Profundidad promedio de la página </td> 
   <td colname="col2"> Muestra un promedio de la distancia recorrida en una visita para que se active cada valor. Esta métrica es muy valiosa a la hora de determinar hasta qué punto de una página determinada o valor de prop llegan los usuarios durante una visita. Profundidad promedio de la página está disponible en cualquier variable que tenga las rutas activadas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiempo promedio empleado en la página </td> 
   <td colname="col2"> Representa el tiempo promedio empleado en una página durante una visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiempo promedio empleado en el sitio </td> 
   <td colname="col2"> Representa el tiempo promedio empleado en un sitio durante una visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tasa de devoluciones </td> 
   <td colname="col2"> Muestra el porcentaje de visitas que contiene una sola visita. La tasa de devoluciones utiliza la métrica Devoluciones y se calcula de esta forma: devoluciones divididas entre entradas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Devoluciones </td> 
   <td colname="col2"> Una vista que consta de una sola llamada al servidor. Por ejemplo, una visita a una sola página se considera una salida hacia otro sitio si el visitante no interactúa con la página de manera que envíe datos a Adobe (como ocurre al hacer clic en un vínculo o en un inicio de vídeo). Si se recibe más de una sola visita, no se cuenta una devolución. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campaña de pulsación </td> 
   <td colname="col2"> Las pulsaciones representan el número de veces que se pasó el código de seguimiento de una determinada campaña a los informes. Cuando un usuario haga clic en un vínculo afiliado que se haya etiquetado con uno de estos códigos de seguimiento, se dirigirá al visitante a la página de destino y el código de seguimiento se capturará en s.campaign. Esos datos se envían a los informes y se registra una pulsación. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adiciones al carro de compras </td> 
   <td colname="col2"> Número de veces que un artículo se agregó a un carro de compras. Este valor se obtiene a partir del evento scAdd. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Apertura de la compra </td> 
   <td colname="col2"> Número de veces que un cliente abrió un carro de compras agregando el primer artículo. Sucede la primera vez que se agrega un artículo al carro de compras. Este valor se obtiene a partir del evento scOpen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eliminaciones del carro de compras </td> 
   <td colname="col2"> Número de veces que se ha retirado un artículo de un carro de compras. Este valor se obtiene a partir del evento scRemove. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Carros de compras </td> 
   <td colname="col2"> Número de veces que se ha abierto o iniciado un nuevo carro de compras. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas de carro de compras </td> 
   <td colname="col2"> Número de veces que el cliente ve el contenido del carro de compras. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cierres de compra </td> 
   <td colname="col2"> Evento que sucede cuando los clientes llegan a la etapa de cierre de compra. La etapa de cierre de compra se produce generalmente justo antes de que finalice la compra, y habitualmente comprende la introducción de información personal por parte del cliente (por ejemplo: información de facturación y envío). Usted dispone de control sobre los eventos del sitio que se califican como cierres de compra. Este valor se obtiene a partir del evento scCheckout. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pulsaciones </td> 
   <td colname="col2">Las pulsaciones representan el número de veces que se pasó el código de seguimiento de una determinada campaña a los informes. Cuando un usuario haga clic en un vínculo afiliado que se ha etiquetado con uno de estos códigos de seguimiento, el visitante será dirigido a la página de aterrizaje y el código de seguimiento se capturará en <span class="varname"> s.campaign</span>. Esos datos se envían a los informes y se registra una pulsación. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cliente (nuevo, de retorno, fiel) </td> 
   <td colname="col2">Categorías del informe Lealtad del cliente: <p>Cliente nuevo: cliente con cero compras. </p> <p>Cliente que retorna: cliente con una compra. </p> <p>Cliente fiel: cliente con más de una compra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de retorno diario </td> 
   <td colname="col2"> Muestra el número de visitantes que se acercan a su sitio web más de una vez durante un día determinado. Un día se define como el último período de 24 horas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entradas </td> 
   <td colname="col2"> Entradas representa el número de veces que un valor determinado se captura como el primero de una visita. Entradas solo tiene lugar una vez por visita. No obstante, no tiene por qué ser necesariamente la primera visita si no se ha definido la variable. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salidas </td> 
   <td colname="col2"> El número de veces que un valor determinado se captura como el último de una visita. Las salidas solo tienen lugar una vez por visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instancias </td> 
   <td colname="col2"> Número de veces que se ha establecido un valor para una variable. Las instancias se cuentan para todos los tipos de visitas, pero no se cuentan si se registra un valor para una variable en una visita subsiguiente debido a una persistencia. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duración </td> 
   <td colname="col2"> Cantidad total de una métrica de éxito determinada para un único usuario, por ejemplo, el número total de visitas para un usuario. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas con dispositivos móviles </td> 
   <td colname="col2"> El número de veces que una página se visualiza o que una dimensión se establece al acceder a la misma mediante un dispositivo móvil. Solo Ad Hoc Analysis. En lugar de usar la métrica de vistas con dispositivos móviles, se recomienda aplicar el segmento "Visitas de dispositivos móviles". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nuevos compromisos </td> 
   <td colname="col2"> Nuevos compromisos es una métrica de creación de informes de canal de marketing que cuenta los visitantes conseguidos a través de un canal. Esta métrica cuenta también los visitantes que no han entrado en su sitio web durante los últimos 30 días. Nuevos compromisos es una eVar que se establece al principio de cada visita (asignación original). Los canales de primer toque también pueden ser Nuevos compromisos, según la configuración de caducidad del compromiso de los visitantes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ocurrencias </td> 
   <td colname="col2"> Número de veces que se captura un valor específico más el número de vistas de página para el que persistió el valor dado. En otras palabras, las ocurrencias son la suma de vistas de página y eventos de página. Las ocurrencias están disponibles solo en Ad Hoc Analysis. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pedidos </td> 
   <td colname="col2"> Número de pedidos realizados en el sitio web durante el período de tiempo especificado. Se pueden desglosar los períodos de tiempo individuales utilizando otras métricas para mostrar los elementos (tales como productos o campañas) que contribuyeron a la mayoría de los pedidos durante ese período. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profundidad de página </td> 
   <td colname="col2"> Número promedio de clics que hacen los usuarios para llegar a una determinada página del sitio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eventos de página </td> 
   <td colname="col2"> Estos eventos se componen de datos de solicitud de imagen de solicitudes de imagen que no son estándar. Las fuentes de estas solicitudes proceden del seguimiento de vínculos personalizados, de salida y de descarga. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas de páginas </td> 
   <td colname="col2"> Por cada llamada al servidor que se envía, se cuenta una vista de página. Esta métrica representa el total de instancias de vistas de página. Las llamadas tracklink no se cuentan como vistas de página y no contribuyen a incrementar la métrica de vistas de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas de rutas </td> 
   <td colname="col2"> <p>La métrica Vistas de rutas se basa en los datos de rutas, que se rastrean en todos los usuarios que aceptan cookies persistentes. </p> <p>El término "vista de ruta" se utiliza para indicar la cantidad de veces que se visualizó una página teniendo en cuenta las restricciones de las rutas mostradas. En otras palabras, esta métrica informa sobre la cantidad de vistas de dicha página que se hayan producido dentro de la ruta seleccionada. Esta métrica está disponible en el informe de rutas. Las vistas de ruta le muestran el número de veces que se ha visto una secuencia determinada de páginas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas del producto </td> 
   <td colname="col2"> Instancia de la vista del producto que se está configurando. Se produce cuando se ve una página con detalles de un producto. Este valor se obtiene a partir del evento prodView. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recargas </td> 
   <td colname="col2"> Se cuenta cuando el mismo nombre de página se carga dos veces en una fila. Indica normalmente que la página se ha actualizado. Tenga en cuenta que visitar la misma página dos veces durante la misma visita no cuenta como nueva carga a menos que las dos visitas ocurran de forma consecutiva. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de retorno </td> 
   <td colname="col2"> Muestra el número de visitas en las que el número de visitas es mayor que 1. Informe de visitas incluye a los visitantes sin cookies. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresos </td> 
   <td colname="col2"> Los ingresos se capturan en el evento de compra y se definen como el total de dólares para la suma del pedido de cada producto. Este valor se obtiene a partir del evento de compra. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Búsquedas </td> 
   <td colname="col2"> <p>Búsquedas no es una métrica predeterminada: siempre es una métrica personalizada. </p> <p>Es la métrica predeterminada recomendada para los motores de búsqueda y palabras clave. Esta métrica representa las instancias de pulsación y muestra la página que está asociada a un motor o a una palabra clave específica. Los datos de la métrica Búsquedas pueden informarse en forma retroactiva al comienzo del conjunto de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Acceso único </td> 
   <td colname="col2"> Acceso único se define como el número de visitas al sitio que contenían un solo valor Nombre de página único. Si un usuario entra en el sitio y hace clic en un vínculo, activa un evento (por ejemplo, una vista de vídeo) o vuelve a cargar la página, la visita seguirá considerándose una visita de acceso único. Mientras el valor de la variable pageName no cambie, la visita seguirá considerándose como un acceso único independientemente del número de solicitudes enviadas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiempo empleado </td> 
   <td colname="col2"> Métricas que informan de la cantidad de tiempo que los visitantes invierten en una página, en un sitio o por visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total </td> 
   <td colname="col2"> Medidas totales indica el valor de todos los elementos de línea del informe para un período del informe. Si tiene seleccionado actualmente un filtro, el total podría representar el total filtrado en vez del total del grupo de informes. Si no hay ningún filtro seleccionado, el total representa el total del grupo de informes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cliente único </td> 
   <td colname="col2"> <p>(por hora, diario, semanal, mensual, trimestral, anual) </p> <p>Un cliente único se contabiliza una vez en el marco temporal pero no se contabilizará de nuevo, independientemente de las veces que el visitante regrese para realizar una compra. Un visitante único se contabiliza una vez la primera visita que realiza en un período especificado y no se contabilizará de nuevo hasta que el período expire. Una vez que el período expire, el visitante único se contabilizará de nuevo. Los clientes únicos siempre se cuentan como visitantes únicos porque deben visitar el sitio para realizar una compra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes únicos </td> 
   <td colname="col2"> Muestra el número total de visitantes únicos para el período del informe (se puede configurar como diario, semanal, mensual, trimestral y anual). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unidades </td> 
   <td colname="col2"> Unidades totales que se pidieron durante el período de tiempo seleccionado. Como pueden comprarse varias unidades por pedido, las unidades representan una métrica fundamental que revela el movimiento general del inventario. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes </td> 
   <td colname="col2"> Número de visitantes únicos del sitio durante la hora, el día, la semana, el mes, el trimestre o el año que se haya seleccionado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas </td> 
   <td colname="col2"> <p>Secuencia de visitas de la página efectuadas en una sesión. La métrica de visitas se utiliza comúnmente en informes que muestran el número de sesiones de usuario que se producen en el período de tiempo seleccionado. </p> <p>La métrica de visitas siempre se asocia con un período de tiempo, por lo que sabe si contar una visita nueva si el mismo visitante vuelve a su sitio. </p> </td> 
  </tr> 
 </tbody> 
</table>

