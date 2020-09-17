---
description: Muestra información acerca de los visitantes, incluido el recuento de los mismos, la lealtad del cliente y las características del visitante.
title: Informes de visitante
topic: Ad hoc analysis
uuid: 3e9b41d1-d6ff-47a8-aa6b-829df1040c34
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 98%

---


# Informes de visitante

>[!IMPORTANT]
>
>Adobe está moviendo Ad Hoc Analysis al estado de fin de vida el 1 de marzo de 2021. [Más información...](https://adobe.ly/discoverworkspace).

Muestra información acerca de los visitantes, incluido el recuento de los mismos, la lealtad del cliente y las características del visitante.

## Frecuencia de retorno {#concept_447A99B71E484D27A7A02888CC51FD3D}

Este informe muestra el tiempo que transcurre entre las visitas de los visitantes que retornan y la cantidad de visitas que entran dentro de cada categoría de longitud de tiempo. Use este informe para ver la cantidad de tiempo promedio que pasan los visitantes repetidos sin ir al sitio, y las tendencias de los clientes repetidos.

<!-- 

c_reports_return_freq.xml

 -->

Por ejemplo, al agregar a este informe la métrica Pedidos, un sitio de venta minorista puede hacerse una idea de la cantidad de tiempo entre visitas que es más eficaz para generar conversiones. Use esta información para dirigir campañas de promoción eficaces a aquellos visitantes que han pasado cierta cantidad de tiempo sin visitar el sitio.

Puede:

* Identificar la cantidad de visitantes de retorno y la frecuencia con que lo hacen.
* Evaluar el atractivo y la importancia que tiene el sitio web para los visitantes a lo largo del tiempo.
* Conocer en qué medida el sitio resulta atractivo para los visitantes y cuán a menudo sienten deseos de regresar para interactuar o buscar información actualizada.
* Identificar cómo influye sobre los visitantes el contenido del sitio web y las promociones.

De manera predeterminada, este informe incluye los siguientes períodos:

* Menos de un día
* De uno a tres días
* De tres a siete días
* De siete a catorce días
* De quince días a un mes
* Más de un mes

## Número de visita {#concept_BBB614072FD74379B1A8520ACB75AE9A}

Muestra los números de orden de las visitas de los clientes que influyeron más sobre las métricas de éxito. Cuando un visitante entra por primera vez al sitio, se cuenta dentro del artículo de línea de la visita número 1. Los visitantes que vuelvan al sitio para una segunda visita se contarán en el artículo de línea de la visita número 2 y así sucesivamente.

<!-- 

c_reports_visit_number.xml

 -->

Este informe se puede usar como un informe de tasas de abandono de la secuencia prevista, para ver si los visitantes regresan al sitio. También se puede agregar una métrica de ingresos para ver si se generan más ingresos en la primera visita o en las posteriores.

Por ejemplo, este informe puede responder preguntas como: ¿los clientes que compraron algo en la cuarta visita generaron más ingresos que los que compraron en la primera visita?

Este informe se puede desglosar según cualquier otro informe o variable, para determinar:

* Cuántas visitas hizo un usuario que entró al sitio desde un vínculo enviado por la campaña XYZ hasta que hizo una compra.
* Si, por ejemplo, los usuarios de Tokio hacen más visitas antes de generar una posible venta que los usuarios de Londres.

>[!NOTE]
>
>Si el mismo visitante viene al sitio varias veces dentro de un mismo período, todos los números de visitas especificados se incrementan con cada visita.

Este informe se basa en los datos de identificación del visitante que recibe Adobe cada vez que los visitantes abren una página en sus navegadores. Adobe compara los datos que recibe con los datos históricos de identificación de los visitantes para determinar si la descarga de página es:

* Un visitante nuevo (el número de visita es igual a 1).
* Un visitante anterior que continúa una visita (el número de visita no se incrementa).
* Un visitante anterior que inicia una visita nueva (el número de visita se incrementa en uno).

>[!NOTE]
>
>Cada ID de visitante de Analytics está asociado con un perfil del visitante en los servidores de Adobe. Los perfiles de visitante se borran tras 13 meses de inactividad, independientemente de la caducidad de cualquier cookie del ID del visitante.

## Lealtad del cliente {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

Use este informe para ver si los ingresos dependen más de los clientes nuevos o de los clientes fieles.

<!-- 

c_reports_customerloyalty.xml

 -->

El informe [!UICONTROL Lealtad del cliente] revela los patrones de compra de los clientes en función de tres categorías de fidelidad:

* **No cliente**: visitantes que nunca han realizado ninguna compra
* **Cliente nuevo**: visitantes que solo han realizado una compra
* **Cliente que vuelve**: visitantes que han realizado dos compras
* **Cliente fiel**: visitantes que han realizado más de tres compras

>[!NOTE]
>
>Cuando se usan estas métricas, todas las visitas (o todos los visitantes) del usuario aparecen en el informe, independientemente de si la visita (o el visitante) incluyó una compra.

El estado de lealtad cambia después de que termine la visita en la que se produce un evento de compra. Por ejemplo, un cliente nuevo (una compra) hace una compra y, a continuación, en la misma visita, se inscribe para recibir un boletín de noticias. El evento de inscripción en el boletín todavía se considera una interacción con un cliente nuevo, porque el estado de lealtad del cliente no cambia hasta la siguiente visita.

## Perfil del visitante {#concept_4D829198CD144DCDA667E0651F93AFC7}

Muestra información sobre el tipo de visitante que llega a su sitio. Puede ver la ubicación del visitante, el tipo de explorador y hardware del equipo utilizado, los idiomas utilizados y los datos del proveedor de servicios de Internet de los visitantes.

<!-- 

c_reports_visitor_profile.xml

 -->

**[!UICONTROL Idiomas]**: muestra los idiomas preferidos por los visitantes, captura el idioma del navegador predeterminado y muestra los idiomas que los visitantes usan con más frecuencia en su sitio.

**[!UICONTROL Dominios]**: enumera las organizaciones y los ISP que los visitantes utilizan para acceder al sitio. Este informe difiere del informe de [!UICONTROL dominios completos] en que el informe de dominios completos registra el dominio completo del proveedor, mientras que el primero indica el dominio secundario.

**[!UICONTROL Dominios de nivel superior]**: identifica las regiones del mundo de donde provienen los visitantes, basándose en la extensión del dominio de origen, y muestra la cantidad de visitantes que vienen de estos países. Los dominios con las terminaciones comerciales (.com), red (.net), educación (.edu), gobierno (.gov) y organización (.org), generalmente provienen de Estados Unidos y se los separa de los demás dominios.

**[!UICONTROL Códigos postales de visitantes]**: muestra el código postal de los clientes que tuvieron el mayor efecto en las métricas de éxito de compra.

## Segmentación geográfica {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

Muestra en tiempo real la dinámica geográfica de los visitantes, lo cual incluye datos sobre los países, estados y ciudades desde los cuales navegan. También permite obtener una importante cuota de comprensión de la tecnología y las preferencias de audiencia del sitio web.
