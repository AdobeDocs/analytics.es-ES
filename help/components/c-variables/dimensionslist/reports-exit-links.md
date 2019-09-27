---
description: Muestra los vínculos más comunes en los que los usuarios hacen clic y conducen a ubicaciones externas al sitio. Por lo general, estos vínculos señalan a sitios de afiliados o socios. No obstante, pueden llevar a cualquier ubicación donde se haya implementado un vínculo externo. Este informe permite ver los vínculos de afiliados más populares y ayuda a validar el número de referentes que se ha proporcionado conforme al estado de los socios.
seo-description: Muestra los vínculos más comunes en los que los usuarios hacen clic y conducen a ubicaciones externas al sitio. Por lo general, estos vínculos señalan a sitios de afiliados o socios. No obstante, pueden llevar a cualquier ubicación donde se haya implementado un vínculo externo. Este informe permite ver los vínculos de afiliados más populares y ayuda a validar el número de referentes que se ha proporcionado conforme al estado de los socios.
seo-title: 'Vínculos de salida '
solution: Analytics
title: 'Vínculos de salida '
topic: Informes
uuid: e1452f04-389d-4aa3-8763-73280284302
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Vínculos de salida 

Muestra los vínculos más comunes en los que los usuarios hacen clic y conducen a ubicaciones externas al sitio. Por lo general, estos vínculos señalan a sitios de afiliados o socios. No obstante, pueden llevar a cualquier ubicación donde se haya implementado un vínculo externo. Este informe permite ver los vínculos de afiliados más populares y ayuda a validar el número de referentes que se ha proporcionado conforme al estado de los socios.

Para que esta página se rellene correctamente deben cumplirse varios requisitos:

* Si se realiza un seguimiento manual de los vínculos personalizados, debe activarse una solicitud *`s.tl()`* con el parámetro central definido en *e*.

* Si se realiza un seguimiento automático de los vínculos personalizados, deben cumplirse todos los requisitos siguientes:
* 

   * [s.trackExternalLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_trackexlinks.html) debe definirse en *true*.

   * El vínculo en el que el usuario ha hecho clic no debe coincidir con ningún valor de la variable [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkinfilters.html).
   * Si se implementa [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkinfilters.html), el vínculo externo debe coincidir con al menos uno de los valores definidos en esta variable.

* Si no se cumplen todos los requisitos anteriores, la visita no se registrará en este informe.

* 
* Al igual que ocurre con todas las visitas de seguimiento de vínculos personalizados, la variable [s.pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_pagename.html) se elimina de la solicitud de imagen para evitar la inflación de la vista de página.
* Este informe puede verse en los formatos de tendencias y clasificación.
* Este informe puede utilizar un filtro de búsqueda para localizar artículos de línea específicos.
* Pueden crearse [breakdowns](/help/analyze/reports-analytics/reports-customize/breakdowns.md) with any other variable via Admin Tools.
* [Instancias](../../../components/c-variables/c-metrics/metrics-instance.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) son las únicas métricas disponibles de forma predeterminada en este informe y cuentan el número de veces que se ha activado un vínculo de salida.
* En este informe pueden habilitarse los visitantes diarios, semanales, mensuales y trimestrales. No obstante, solo puede hacerlo un representante de Adobe con un costo adicional. Cuando se habilitan los visitantes únicos para cualquier variable de seguimiento de vínculos personalizados, aumenta considerablemente la latencia del grupo de informes.

