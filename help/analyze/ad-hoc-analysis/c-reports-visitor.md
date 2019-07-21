---
description: Muestra información acerca de los visitantes, incluso el recuento de visitantes, la lealtad del cliente y las características del visitante.
seo-description: Muestra información acerca de los visitantes, incluso el recuento de visitantes, la lealtad del cliente y las características del visitante.
seo-title: Informes de visitante
solution: Analytics
title: Informes de visitante
topic: Ad Hoc Analysis
uuid: 3 e 9 b 41 d 1-d 6 ff -47 a 8-aa 6 b -829 df 1040 c 34
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Informes de visitante

Muestra información acerca de los visitantes, incluso el recuento de visitantes, la lealtad del cliente y las características del visitante.

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

## Número de visitas {#concept_BBB614072FD74379B1A8520ACB75AE9A}

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
>Si el mismo visitante visita el sitio varias veces en el mismo período, cada número de visita especificado se incrementa en cada visita.

Este informe se basa en los datos de identificación del visitante que recibe Adobe cada vez que los visitantes abren una página en sus navegadores. Adobe compara los datos que recibe con los datos históricos de identificación de los visitantes para determinar si la descarga de página es:

* Un visitante nuevo (el número de visita es igual a 1).
* Un visitante anterior que continúa una visita (el número de visita no se incrementa).
* Un visitante anterior que inicia una visita nueva (el número de visita se incrementa en uno).

>[!NOTE]
>
>Cada ID de visitante de Analytics está asociado con un perfil de visitante en servidores de Adobe. Los perfiles de visitante se borran tras 13 meses de inactividad, independientemente de la caducidad de cualquier cookie del ID del visitante.

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
>Al utilizar estas métricas, todas las visitas del usuario (o todos los visitantes) se representan en este informe, independientemente de si la visita (o el visitante) incluye una compra.

El estado de lealtad cambia después de que termine la visita en la que se produce un evento de compra. Por ejemplo, un cliente nuevo (una compra) hace una compra y, a continuación, en la misma visita, se inscribe para recibir un boletín de noticias. El evento de inscripción para el boletín todavía se considera una interacción con un cliente nuevo, porque el estado de lealtad del cliente no cambiará sino hasta la próxima visita.

## Perfil del visitante {#concept_4D829198CD144DCDA667E0651F93AFC7}

Muestra información sobre el tipo de visitante que llega a su sitio. Puede ver la ubicación del visitante, el tipo de explorador y hardware del equipo utilizado, los idiomas utilizados y los datos del proveedor de servicios de Internet de los visitantes.

<!-- 

c_reports_visitor_profile.xml

 -->

** [!UICONTROL Languages] **: Displays your visitors’ preferred languages, captures the default browser language, and displays the languages that visitors use most often on your site.

** [!UICONTROL Domains] **: Lists the organizations and ISPs your visitors use to access your site. Este informe difiere del informe de [!UICONTROL dominios completos] en que el informe de dominios completos registra el dominio completo del proveedor, mientras que el primero indica el dominio secundario.

** [!UICONTROL Top Level Domains] **: Identifies world regions that visitors come from based on their originating domain extension, and shows how many visitors come from these countries. Los dominios con terminaciones comerciales (.com), de red (.net), de educación (.edu), de gobierno (.gov) y de organización (.org), generalmente, provienen de Estados Unidos y están separados de los demás dominios.

** [!UICONTROL Visitor ZIP/Postal Code] **: Displays the zip and postal codes that produced the customers that had the greatest effect on purchase success metrics.

## Segmentación geográfica {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

Muestra en tiempo real la dinámica geográfica de los visitantes, lo cual incluye datos sobre los países, estados y ciudades desde los cuales navegan. También permite obtener una importante cuota de comprensión de la tecnología y las preferencias de audiencia del sitio web.
