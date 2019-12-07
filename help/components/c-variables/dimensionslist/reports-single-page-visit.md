---
description: No se debe confundir con la métrica Visitas a una sola página de los Ad Hoc Analysis. El informe Visitas a una sola página muestra las páginas en las que entran y de las que salen los visitantes de un sitio web sin realizar pasos para ver ninguna otra página.
title: Visita a una sola página
topic: Reports
uuid: 5ca52be8-c7f5-464a-8a06-55e8271760b4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visita a una sola página

No se debe confundir con la métrica Visitas a una sola página de los Ad Hoc Analysis. El informe Visitas a una sola página muestra las páginas en las que entran y de las que salen los visitantes de un sitio web sin realizar pasos para ver ninguna otra página.

Este informe se utiliza por lo general en el contexto del informe [!UICONTROL Páginas], aunque también se puede ver en todas las variables de tráfico que tengan las [!UICONTROL rutas] habilitadas. Puede utilizar el informe para identificar las páginas de entrada que tengan menos probabilidades de “invitar” a seguir explorando el sitio, o para determinar cuántas visitas constan de una sola página. Esta información le permite optimizar el contenido para reducir las salidas en esas páginas.

## Propiedades del informe  {#section_2D30F939FE0648EF983DD7C1BAB1181B}

* Es posible recuperar un informe idéntico si se extrae un informe [!UICONTROL Páginas] utilizando [!UICONTROL Acceso único] como métrica.

* Una visita a una sola página se considera una visita que contiene un único valor, no una sola solicitud de imagen.

   * En el contexto de un  [informe de páginas](/help/components/c-variables/dimensionslist/reports-pages.md), solamente puede activarse una única página en la visita.
   * En el contexto del [informe de secciones delsitio](/help/components/c-variables/dimensionslist/reports-site-sections.md), se activa una sola sección del sitio única dentro de la visita.
   * En el contexto de una [variable de tráfico](/help/admin/admin/c-traffic-variables/traffic-var.md), una visita rellena este informe si se activa un único valor único.

* Siempre y cuando la variable en el contexto del informe contenga un solo valor único, las visitas a una sola página podrán constar de muchas solicitudes de imagen. Tan pronto se rellene un segundo valor único, la visita dejará de considerarse como visita a una sola página.
* Se considera un tipo de informe de rutas. De forma predeterminada, la variable [!UICONTROL Páginas] tiene las rutas habilitadas. No obstante, cualquier variable de tráfico tiene también esta capacidad. La activación de rutas en otras variables de tráfico depende de su contrato. Póngase en contacto con el administrador de cuentas de su organización para obtener más detalles.
* Este informe puede utilizar un filtro de búsqueda para localizar artículos de línea específicos.
* Este informe se puede ver en formatos de  formatos de [tendencias](/help/components/c-variables/dimensionslist/reports-types.md) y [clasificación](/help/components/c-variables/dimensionslist/reports-types.md).

* No hay ningún desglose disponible en este informe.
* La única métrica disponible en este informe es [!UICONTROL Visitas].

