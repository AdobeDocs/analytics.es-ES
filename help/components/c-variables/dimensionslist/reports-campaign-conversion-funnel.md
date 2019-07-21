---
description: Muestra los promedios de las métricas del grupo de informes de campañas. Las métricas predeterminadas son Pulsaciones, Ventas totales, Pedidos e Ingresos.
seo-description: Muestra los promedios de las métricas del grupo de informes de campañas. Las métricas predeterminadas son Pulsaciones, Ventas totales, Pedidos e Ingresos.
seo-title: Canal de conversión de campañas
solution: Analytics
title: Canal de conversión de campañas
topic: 'Informes '
uuid: b 0 a 90917-e 4 c 7-40 da -854 e -58649 de 09742
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Canal de conversión de campañas

Muestra los promedios de las métricas del grupo de informes de campañas. Las métricas predeterminadas son Pulsaciones, Ventas totales, Pedidos e Ingresos.

**[!UICONTROL Campañas]** &gt; **[!UICONTROL Canal de conversión de campañas]**

La parte superior de un gráfico de canal muestra los datos de conversión. La parte inferior muestra las estadísticas de todos los eventos del área principal basados en los pedidos y un máximo de dos métricas más, Ingresos y Unidades.

Tenga en cuenta la siguiente información para interpretar los datos del canal de conversión:

* Es posible que no estén completas las estadísticas para los períodos de tiempo actuales en el momento que se vean los datos, lo que podría afectar a las tendencias de un día anterior al día actual.
* Cuando no se aplica ningún filtro al canal, la métrica Visitas representa las visitas de conversión o las visitas durante las cuales se ejecutó un evento de éxito, una variable de campaña o cualquier variable eVar. Las visitas durante las cuales no se pasó ninguna de estas propiedades a los informes no se incluyen en este total.
* Cuando se aplica un filtro al canal, la métrica Visitas representa instancias (o pulsaciones). Este valor representa el número total de veces que los usuarios del sitio rellenaron la variable indicada, excluidas las instancias que no cumplen los requisitos del filtro. Una única visita puede implicar múltiples instancias.
* En los niveles más profundos del canal es posible informar sobre números más elevados que en los niveles más superficiales. Por ejemplo, puede ver más pedidos que pulsaciones o más cierres de compra que vistas del producto. Esto se produce por varios motivos:

   * Hay más pedidos que pulsaciones si la variable del código de seguimiento se ajusta en un caducidad larga de cookie (por ejemplo, un mes), y los usuarios realizan únicamente una pulsación pero vuelven varias veces y realizan pedidos durante ese período, antes de que caduque el valor del código de seguimiento.
   * Hay más cierres de compra que vistas del producto si el usuario puede omitir la página de vista del producto (como en el caso de una página de venta vertical) o puede guardar el carro de compras y regresar más tarde para completar el pedido. Si la vista del producto se ha efectuado con anterioridad al intervalo de fechas seleccionado y el cierre de compra se produce después, verá una vista de cierre de compra y ninguna vista del producto. Si nota esa discrepancia, no se trata de un problema de los informes, ni tampoco un error de implementación. Por el contrario, puede usar esos datos para comprender cómo los usuarios interactúan con el sitio, incluso si no se ajustan al canal de la manera esperada.

