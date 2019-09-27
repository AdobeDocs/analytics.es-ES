---
description: Evalúa el efecto que los distintos códigos de seguimiento publicitario tienen en los eventos de conversión del sitio. Este informe se puede utilizar para conocer las campañas específicas que ofrecen un mejor rendimiento para los eventos de éxito. También se emplea para comprobar si las campañas están ayudando u obstaculizando las iniciativas del sitio, por ejemplo, para saber qué campañas generan mayores ingresos.
seo-description: Evalúa el efecto que los distintos códigos de seguimiento publicitario tienen en los eventos de conversión del sitio. Este informe se puede utilizar para conocer las campañas específicas que ofrecen un mejor rendimiento para los eventos de éxito. También se emplea para comprobar si las campañas están ayudando u obstaculizando las iniciativas del sitio, por ejemplo, para saber qué campañas generan mayores ingresos.
seo-title: Códigos de seguimiento
solution: Analytics
title: Códigos de seguimiento
topic: Informes
uuid: c893d592-10fd-4b40-84b3-8c8949a67b25
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Códigos de seguimiento

Evalúa el efecto que los distintos códigos de seguimiento publicitario tienen en los eventos de conversión del sitio. Este informe se puede utilizar para conocer las campañas específicas que ofrecen un mejor rendimiento para los eventos de éxito. También se emplea para comprobar si las campañas están ayudando u obstaculizando las iniciativas del sitio, por ejemplo, para saber qué campañas generan mayores ingresos.

**Propiedades generales**

* Este informe hace referencia a los datos directamente desde la variable [s.campaign](/help/implement/js-implementation/c-variables/page-variables.md) implementada en el sitio web.
* La variable en la que se basa este informe es una [variable de conversión](/help/admin/admin/conversion-var-admin/conversion-var-admin.md). Es decir, puede persistir más allá de la vista de página y se puede asociar a métricas dentro de la fecha de caducidad especificada.
* La métrica predeterminada del informe es Ingresos. Puede cambiar este valor predeterminado en el [!UICONTROL Administrador del grupo de informes] de las [!UICONTROL Herramientas de administración]. ( **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Individual Report Settings]** &gt; **[!UICONTROL Default Metrics]**.)

* Este informe puede verse tanto en formato de tendencias como de clasificación.
* Este informe puede utilizar un filtro de búsqueda para localizar artículos de línea específicos.
* Los informes [!UICONTROL Campañas] y [!UICONTROL Elementos creativos] son clasificaciones basadas en este informe y se crean automáticamente con cada grupo de informes.

* En este informe se puede utilizar la clasificación SAINT, lo que permite cambiar el nombre de los elementos de línea y consolidarlos.
* Este informe puede desglosarse en los siguientes informes (en función de la configuración de la organización y del grupo de informes):

   * Tiempo empleado por visita
   * Informes Páginas y Secciones de sitio, con todas las clasificaciones relacionadas
   * Profundidad de página, Páginas de entrada y Páginas de entrada originales
   * La mayoría de los informes de fuentes de tráfico
   * Número de visitas y Lealtad del cliente
   * Muchos informes Perfil del visitante y Tecnología, excluido Segmentación geográfica
   * Todos las variables de conversión personalizada

* En este informe se pueden utilizar las métricas siguientes (en función de la organización y la configuración del grupo de informes):

   * Pulsaciones: número de veces que se define la variable *`s.campaign`* se define
   * Todas las métricas de comercio electrónico estándar: ingresos, pedidos, unidades, carros de compra, vistas del carro de compras, cierres de compra, adiciones al carro de compra, eliminaciones del carro de compra.
   * Todos los eventos personalizados: eventos 1-80 y eventos 81-100 si se trabaja con el código H22 o superior
   * Visitas y Visitantes: disponibles en función del grupo de informes y la organización. Para obtener más información el usuario debe ponerse en contacto con el Administrador de cuentas.

**Propiedades de Reports &amp; Analytics**

* Click **[!UICONTROL Conversion]** &gt; **[!UICONTROL Campaigns]** &gt; **[!UICONTROL Tracking Code]** to locate this report, unless the menu is customized.

* Este informe también puede desglosarse mediante todas las [variables de lista](https://marketing.adobe.com/resources/help/en_US/sc/implement/list_var.html).
* Las vistas de página, visitas y visitantes únicos están disponibles como métricas.
* Este informe puede utilizar segmentos.

** Propiedades de los Ad Hoc Analysis**

* Además de usar la mayoría de las variables de conversión integradas, puede desglosar el informe Código de seguimiento por todos los demás informes de la interfaz de informes.
* Además de usar los eventos personalizados y de comercio electrónico, puede utilizar todas las métricas de conversión y tráfico, y una asignación diferente para todas las métricas de conversión.
* Este informe puede utilizar segmentos avanzados.

