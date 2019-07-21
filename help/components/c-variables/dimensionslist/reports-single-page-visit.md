---
description: No se debe confundir con la métrica Visitas a una sola página de los Ad Hoc Analysis. El informe Visitas a una sola página muestra las páginas en las que entran y de las que salen los visitantes de un sitio web sin realizar pasos para ver ninguna otra página.
seo-description: No se debe confundir con la métrica Visitas a una sola página de los Ad Hoc Analysis. El informe Visitas a una sola página muestra las páginas en las que entran y de las que salen los visitantes de un sitio web sin realizar pasos para ver ninguna otra página.
seo-title: Visita a una sola página
solution: Analytics
title: Visita a una sola página
topic: 'Informes '
uuid: 5 ca 52 be 8-c 7 f 5-464 a -8 a 06-55 e 8271760 b 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Visita a una sola página

No se debe confundir con la métrica Visitas a una sola página de los Ad Hoc Analysis. El informe Visitas a una sola página muestra las páginas en las que entran y de las que salen los visitantes de un sitio web sin realizar pasos para ver ninguna otra página.

Este informe se utiliza por lo general en el contexto del informe [!UICONTROL Páginas], aunque también se puede ver en todas las variables de tráfico que tengan las [!UICONTROL rutas] habilitadas. Puede utilizar el informe para identificar las páginas de entrada que tengan menos probabilidades de “invitar” a seguir explorando el sitio, o para determinar cuántas visitas constan de una sola página. Esta información le permite optimizar el contenido para reducir las salidas en esas páginas.

## Propiedades del informe {#section_2D30F939FE0648EF983DD7C1BAB1181B}

* Es posible recuperar un informe idéntico si se extrae un informe [!UICONTROL Páginas] utilizando [!UICONTROL Acceso único] como métrica.

* Una visita a una sola página se considera una visita que contiene un único valor, no una sola solicitud de imagen.

   * En el contexto de un [informe de páginas](../../../components/c-variables/dimensionslist/reports-pages.md#concept_0219136EA25745B58434D0C7E751D7D5), solamente puede activarse una única página en la visita.
   * In the context of a [site sections report](../../../components/c-variables/dimensionslist/reports-site-sections.md#concept_39E550D7A9E34C9580E81F5F9E12BDDD), a single unique site section fires within the visit.
   * In the context of a [traffic variable](/help/admin/admin/c-traffic-variables/traffic-var.md), a visit populates this report if a single unique value is fired.

* Siempre y cuando la variable en el contexto del informe contenga un solo valor único, las visitas a una sola página podrán constar de muchas solicitudes de imagen. Tan pronto se rellene un segundo valor único, la visita dejará de considerarse como visita a una sola página.
* Se considera un tipo de informe de rutas. De forma predeterminada, la variable [!UICONTROL Páginas] tiene las rutas habilitadas. No obstante, cualquier variable de tráfico tiene también esta capacidad. La activación de rutas en otras variables de tráfico depende de su contrato. Póngase en contacto con el administrador de cuentas de su organización para obtener más detalles.
* Este informe puede utilizar un filtro de búsqueda para localizar artículos de línea específicos.
* Este informe se puede ver en formatos de [formatos de tendencias](/help/components/c-variables/dimensionslist/reports-types.md) y [clasificación](/help/components/c-variables/dimensionslist/reports-types.md) .

* No hay ningún desglose disponible en este informe.
* La única métrica disponible en este informe es [!UICONTROL Visitas].

