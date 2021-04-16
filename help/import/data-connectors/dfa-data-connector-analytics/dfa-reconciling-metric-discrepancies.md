---
description: Puede que en ciertas ocasiones algunas métricas no presenten una diferencia aceptable al comparar métricas de Adobe Analytics con métricas de DFA. A continuación, se encuentra una lista de definiciones de métricas y motivos posibles de las variaciones.
keywords: DFA
title: Reconciliación de discrepancias de métricas
feature: Data Connectors
uuid: aa3ca006-d3cf-410e-a000-781ab17fb9e3
exl-id: bfe0f9cb-1bbc-40f9-b996-0002d5143889
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1270'
ht-degree: 100%

---

# Reconciliación de discrepancias de métricas {#reconciling-metric-discrepancies}

Puede que en ciertas ocasiones algunas métricas no presenten una diferencia aceptable al comparar métricas de Adobe Analytics con métricas de DFA. A continuación, se encuentra una lista de definiciones de métricas y motivos posibles de las variaciones.

Esta sección comprende los siguientes temas:

## Definiciones de métricas {#metric-definitions}

Adobe usa los siguientes términos al hablar de métricas relacionadas con la integración de DFA:

**Impresiones**: las impresiones hacen referencia a la cantidad de veces que se vio un anuncio. Las impresiones se informan por anuncio, pero también se pueden agregar en grupos de anuncios u otras agrupaciones de varios anuncios. La métrica de impresiones en Analytics se importa desde DFA mediante una importación de fuentes de datos por la noche.

**Clics**: los clics hacen referencia a la cantidad de veces que se hizo clic en un anuncio, según lo que DFA informa. Los clics se registran en la página de redireccionamiento de DFA antes de que el visitante aterrice en el sitio web del cliente. Al igual que las impresiones, la métrica de clics en Analytics se importa desde DFA mediante una importación de fuentes de datos por la noche.

**Proporción de clics**: la proporción de clics hace referencia a la cantidad de veces que el usuario llegó a la página de aterrizaje, después de hacer clic en un anuncio. Esta métrica puede diferir levemente con respecto a los clics.

**Visualizaciones**: Las visualizaciones hacen referencia a la cantidad de veces que un visitante llegó al sitio web del cliente después de ver un anuncio, pero SIN haber hecho clic en el anuncio. El visitante debe llegar al sitio dentro de la ventana de visualización que, de forma predeterminada, está configurada en 30 días. La impresión debe haber ocurrido posteriormente al último clic. Las visualizaciones se registran una vez por campaña, por visita y se cuentan cuando la integración rellena la eVar de visualización con el ID de campaña de DFA, y se establece el evento de visualización.

## Motivos posibles de las discrepancias {#possible-reasons-for-discrepancies}

Muestra una lista de motivos por los cuales cualquier discrepancia puede ocurrir entre informes de Adobe Analytics y DFA.

### Los usuarios en el explorador Safari y otros exploradores que bloquean cookies de terceros {#section-4b0dc429a54a4744a33976b0bb2d1b2a}

La aceptación de cookies de terceros generalmente es la causa principal de discrepancia entre Adobe Analytics y DFA. Safari y algunos otros exploradores bloquean las cookies de terceros de forma predeterminada. Esto significa que, de forma predeterminada, Safari acepta la cookie propia utilizada por la mayoría de las implementaciones de Analytics, pero rechaza la cookie de terceros utilizada por DFA.

Una muestra de datos de nuestros clientes de Analytics 15 beta mostró que menos del 0,5 % de usuarios generalmente rechazan las cookies propias, mientras que entre un 5 y un 12 % rechazan las cookies de terceros (muchos de estos rechazos se deben probablemente a la configuración predeterminada del explorador).

Esta discrepancia puede dar como resultado una gran diferencia en los datos recopilados por Analytics y DFA.

### ¿Por qué las impresiones notificadas en DFA podrían ser más altas que las impresiones notificadas en Adobe Analytics?  {#section-db0ad070a65a4985bcc589b2d0d30b90}

* DFA envía datos a los servidores de recopilación de datos de Adobe en un lote por la noche, de modo que los datos de impresión en Analytics pueden estar hasta 2 días atrasados con respecto a los informes de DFA.
* Adobe usa clasificaciones de SAINT para clasificar códigos de seguimiento de DFA importados en varios niveles de agregaciones (nombre de la campaña, nombre de la ubicación, nombre del anuncio, etc.). Si aparece alguna discrepancia al ejecutar un informe de clasificación, realice una sola prueba para ver si las clasificaciones aún no están a la par de las métricas importadas:

   * En el informe de clasificación, busque un elemento de línea denominado “Ninguno”.
   * Realice un desglose de este elemento de línea por la misma variable, utilizando el informe de ID de DFA sin procesar (como ID de campaña).
   * En este informe, tome nota de todo código de seguimiento de DFA sin clasificar con el formato `DFA:XXXXX:XXXXX`.
   * Si existen muchos de estos códigos de seguimiento, investigue el proceso de clasificación de SAINT por la noche.

### ¿Por qué podrían los clics de DFA ser superiores a la proporción de clics de Adobe Analytics?  {#section-2fce4608ed044bdc9cf812cb719d5d35}

* DFA registra un clic antes de que el visitante aterrice en el sitio web del cliente. Analytics registra la proporción de clics después de que la página de aterrizaje cargue y ejecute la señalización JavaScript de Adobe. Habitualmente, las discrepancias ocurren porque el visitante no está llegando a la página de aterrizaje después de que DFA registre un clic o se esté visitando el temporizador `s.maxDelay`.
* Asegúrese de que todas las ubicaciones y todos los creativos en la Configuración de Floodlight incluyan clickThroughParam en la dirección URL de la página de aterrizaje (por ejemplo, “`?CID=1`”). Al no establecer este parámetro, JavaScript de Adobe Analytics no detectará la proporción de clics que ocurren después de la primera visita.
* Asegúrese de que todas las ubicaciones y todos los creativos tengan una página de aterrizaje que esté etiquetada con el JavaScript y que tenga el módulo Integrate de DFA, y de que el ID de Configuración de Floodlight en esa página de aterrizaje coincida con el ID de configuración de Floodlight de los anuncios publicados. A menudo, las discrepancias surgen porque la página de aterrizaje para anuncios están establecidas en el sitio de terceros o los anuncios publicados.
* Si usa anuncios Rich Media o anuncios Flash (swf), asegúrese de que, cada vez que se visite el rastreador de clics de DFA, el explorador del visitante también se esté redireccionando a la página de Aterrizaje con el `clickThroughParam` incluido en la cadena de consulta. Al no redireccionar el explorador, no se registrará ningún clic.
* Los tiempos de espera representan instancias donde los datos DFA podrían haber estado disponibles pero el JavaScript no recibió una respuesta a tiempo. Cuando un visitante llega en la página de aterrizaje, JavaScript de Adobe solicita la información del visitante desde el servicio fls.doubleclick.net de DFA. El parámetro `s.maxDelay`determina cuánto tiempo el JavaScript espera los datos de Servicio de Floodlight (FLS). Si `s.maxDelay` es demasiado elevado, los visitantes pueden dejar el sitio antes de que Adobe recopile datos de visitas, lo que significa que no se registran datos de clics. Si `s.maxDelay` se establece demasiado bajo, la conexión a Internet del visitante no puede recuperar los datos de FLS a tiempo, lo que significa que la visita se envía a Adobe sin información de clics de DFA.
* El tráfico de bots podría inflar los números de clics de DFA. Los bots pueden tener funcionalidad para hacer clic en un anuncio pero no pueden tener la complejidad de ejecutar una señalización de Analytics o activar la etiqueta de script sincrónico para cargar los datos de solicitud de servidores de Floodlight. Si estos bots no se eliminan de la figura de Clics, puede generarse una discrepancia.
* Se perderán los visitantes que dejen la página antes de que `s.maxDelay` caduque y que los datos de DFA regresen. Tampoco se recopilarán datos de visitantes o DFA para ellos.
* Analytics intenta identificar y eliminar los clics duplicados de modo que se cuentan una sola vez por campaña por visita. DFA cuenta visitantes que hacen clic en “Atrás” y pasan por el redireccionamiento de publicidad varias veces como clics de ACM adicionales, mientras que Analytics no los cuenta como clics.
* Las etiquetas Floodlight de DFA no dependen de que JavaScript esté habilitado, mientras que Analytics sí lo hace. Debido a esto, podrían existir algunos casos en los que DFA registre una visita cuando Analytics no lo hace. Para identificar si esto podría ser un problema, use el informe de JavaScript de Analytics en el menú Perfil del visitante.

### ¿Por qué podrían las actividades posteriores a la impresión de DFA ser más altas que las visualizaciones de Adobe Analytics?  {#section-5daa91039c404df48b6a3447c20406f7}

* Analytics intenta identificar y eliminar los clics duplicados de modo que se cuentan una sola vez por campaña por visita. DFA cuenta visitantes que hacen clic en “Atrás” y pasan por el redireccionamiento de publicidad varias veces como clics de ACM adicionales, mientras que Analytics no los cuenta como clics.
* Las etiquetas Floodlight de DFA no dependen de que JavaScript esté deshabilitado, mientras que Analytics sí lo hace. Debido a esto, podrían existir algunos casos en los que DFA registre una visita cuando Analytics no lo hace.
* DFA cuenta las actividades posteriores a la impresión al usar etiquetas de Floodlight, que se pueden colocar en el sitio web del cliente. Analytics cuenta las visualizaciones después de que se ejecuta la señalización JavaScript (solicitud de imagen). La ubicación de código en la página web puede determinar si una carga de página anulada se cuenta como actividad posterior a la impresión o una visualización.

### ¿Qué sucede si las discrepancias están muy lejos del rango aceptable y los posibles motivos anteriores no son pertinentes?  {#section-ca50eb75dd5d4d0396f4668b44d7547c}

Consulte con su Consultor de integración o Adobe Client Care, para documentar las discrepancias e informar de ellas al equipo de ingeniería de Data Connectors. Para acelerar su solicitud, tenga entre 2 y 3 días de datos comparando las métricas en cuestión (en un nivel de código de campaña). En su solicitud, identifique todas las acciones que ya ha realizado para reconciliar la discrepancia.
