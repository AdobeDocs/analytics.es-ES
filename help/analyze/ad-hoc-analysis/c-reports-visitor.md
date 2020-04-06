---
description: Muestra información acerca de los visitantes, incluido el recuento de los mismos, la lealtad del cliente y las características del visitante.
title: Informes de visitante
topic: Ad hoc analysis
uuid: 3e9b41d1-d6ff-47a8-aa6b-829df1040c34
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Informes de visitante

Muestra información acerca de los visitantes, incluido el recuento de los mismos, la lealtad del cliente y las características del visitante.

## Frecuencia de retorno {#concept_447A99B71E484D27A7A02888CC51FD3D}

Muestra la cantidad de tiempo que transcurre entre las visitas desde los visitantes de retorno y la cantidad de visitas que entran dentro de cada categoría de duración. Use este informe para ver la cantidad de tiempo promedio que pasan los visitantes repetidos sin ir al sitio, y las tendencias de los clientes repetidos.

<!-- 

c_reports_return_freq.xml

 -->

Por ejemplo: mostrar la métrica Pedidos en este informe ayuda a un sitio minorista a comprender el tiempo más efectivo entre visitas para generar conversión. Utilice esta información para comercializar con eficacia a visitantes que han pasado un determinado período de tiempo sin visitar el sitio.

Puede:

* Identificar la cantidad de visitantes que regresan y la frecuencia con que lo hacen.
* Evalúe el atractivo y la relevancia de su sitio web para los visitantes con el paso del tiempo.
* Conocer en qué medida su sitio resulta atractivo para los visitantes y con qué frecuencia se sienten con deseos de regresar con el fin de interactuar o actualizarse.
* Identifique el impacto del contenido y las promociones del sitio web en sus visitantes.

De forma predeterminada, este informe tiene los siguientes períodos de tiempo:

* Menos de un día
* Uno a tres días
* De tres a siete días
* De siete a catorce días
* De 14 días a 1 mes
* Más de un mes

## Número de visita {#concept_BBB614072FD74379B1A8520ACB75AE9A}

Muestra los números de visitas de los clientes que influyeron más en las métricas de éxito. Un visitante que realiza una primera visita al sitio se cuenta en el elemento de línea Visita número 1. Los Visitantes que regresan al sitio para una segunda visita se cuentan en el elemento de línea Visita número 2, etc.

<!-- 

c_reports_visit_number.xml

 -->

Puede utilizar este informe como un informe de visitas en el orden previsto para ver si los visitantes están regresando. También puede agregar una métrica de ingresos para ver si genera más ingresos a partir de visitas iniciales o posteriores.

Por ejemplo: este informe puede responder preguntas como: ¿Generaron más ingresos los clientes que compraron en la cuarta visita que los que compraron en la primera visita?

Puede desglosar este informe por cualquier otro informe o variable para determinar:

* Cuántas visitas suele tomar un usuario que hizo clic en campaña XYZ para realizar una compra.
* Si los usuarios de Tokio, por ejemplo, realizan más visitas antes de generar un posible cliente que los usuarios de Londres.

>[!NOTE] Si el mismo visitante viene al sitio varias veces dentro de un mismo período, todos los números de visitas especificados se incrementan con cada visita.

Este informe se basa en los datos de ID de visitante que se pasan a Adobe en cada visita realizada por visitantes. A medida que se reciben estos datos, Adobe los compara con los datos históricos del ID de visitante para determinar si la visita es:

* Un nuevo visitante (Número de visita es igual a 1).
* Un visitante anterior que continúa una visita (el número de visita no se incrementa).
* Un visitante anterior que realiza una nueva visita (el número de visita se incrementa en uno).

>[!NOTE] Cada ID de visitante de Analytics está asociado con un perfil del visitante en los servidores de Adobe. Los perfiles de visitante se borran tras 13 meses de inactividad, independientemente de la caducidad de cualquier cookie del ID del visitante.

## Lealtad del cliente {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

Use este informe para ver si los ingresos dependen más de los clientes nuevos o de los clientes fieles.

<!-- 

c_reports_customerloyalty.xml

 -->

El [!UICONTROL Customer Loyalty] informe muestra los patrones de compra de los clientes en base a cuatro categorías de lealtad:

* **No es cliente**: Visitantes que nunca han comprado
* **Cliente** nuevo: Visitantes que realizaron una sola compra
* **Cliente** de retorno: Visitantes que han realizado dos compras
* **Cliente** fiel:Visitantes que han realizado más de tres compras

>[!NOTE] Cuando se usan estas métricas, todas las visitas (o todos los visitantes) del usuario aparecen en el informe, independientemente de si la visita (o el visitante) incluyó una compra.

El estado de lealtad cambia después del final de la visita donde se produce un evento de compra. Por ejemplo: un cliente nuevo (1 compra) realiza una compra y luego se registra para recibir un boletín después de esa compra en la misma visita. El evento de registro de la newsletter se sigue considerando una interacción con un cliente nuevo, ya que el estado de lealtad del cliente del visitante no cambiará hasta la próxima visita.

## Perfil del visitante {#concept_4D829198CD144DCDA667E0651F93AFC7}

Muestra información sobre el tipo de visitante que llega al sitio. Puede ver la ubicación del visitante, el tipo de exploradores y hardware de equipo utilizado, los idiomas utilizados y los datos del proveedor de servicio de Internet para sus visitantes.

<!-- 

c_reports_visitor_profile.xml

 -->

**[!UICONTROL Languages]**: Muestra los idiomas preferidos por los visitantes, registra el idioma del explorador predeterminado y muestra los idiomas que los visitantes usan con más frecuencia en el sitio.

**[!UICONTROL Domains]**:: Listas que utilizan las organizaciones y los ISP que sus visitantes para acceder al sitio. This report differs from the [!UICONTROL Full Domains] report in that the Full Domains report registers the full ISP domain, whereas this report lists the secondary domain.

**[!UICONTROL Top Level Domains]**:: Identifica las regiones del mundo de donde provienen los visitantes en base a la extensión de su dominio de origen y muestra cuántos visitantes provienen de estos países. Los dominios que terminan en Comercial (.com), Red (.net), Educación (.edu), Gobierno (.gov) y Organización (.org) suelen estar ubicados en Estados Unidos y están separados del resto de los dominios.

**[!UICONTROL Visitor ZIP/Postal Code]**:: Muestra el código postal de los clientes que tuvieron el efecto bueno en las métricas de éxito de compra.

## Segmentación geográfica {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

Muestra la dinámica geográfica de sus visitantes en tiempo real, incluyendo los países, estados y ciudades desde donde navegan. También puede obtener información importante sobre la tecnología y las preferencias de la audiencia de su sitio web.
