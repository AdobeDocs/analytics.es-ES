---
title: Detalles del canal de último toque
description: Detalles del canal de mercadotecnia más reciente dentro de la caducidad del compromiso del visitante.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 0%

---


# Detalles del canal de último toque

Los informes de dimensión &#39;Detalles del canal de último toque&#39; detallan el canal de marketing más reciente con el que coincide un visitante durante el período de participación de ese visitante (de forma predeterminada, 30 días). Esta dimensión es valiosa para comprender qué contribuyó a que la visita coincidiera con un canal de marketing. Por ejemplo: si un visitante llegó a su sitio y coincidió con el canal de mercadotecnia de &#39;Búsqueda paga&#39;, puede utilizar el detalle de canal para ver qué motor de búsqueda se utilizó o qué palabra clave buscó.

## Rellenar esta dimensión con datos

Esta dimensión copia valores de otras variables. La variable utilizada hace referencia al valor de canal dentro de cada regla [de procesamiento](/help/admin/admin/marketing-channels-admin.md)de Marketing canal. Cuando una visita individual coincide con una regla de procesamiento de canal de marketing, la dimensión de canal [de](last-touch-channel.md) último toque se establece en el nombre del canal y esta dimensión se establece en el valor de canal establecido en la regla.

Si desea establecer esta dimensión en un valor específico, se requieren los siguientes pasos:

* Asegúrese de que el valor de dimensión deseado esté en un atributo de visita o en una variable personalizada.
* Establezca una regla de procesamiento de Marketing canal que contenga los criterios deseados para la visita.
* Seleccione el valor desplegable que desee en [!UICONTROL Definir el valor] del canal dentro de la regla de procesamiento de Marketing canal.
* La visita del visitante al sitio debe coincidir con los criterios descritos en la regla de procesamiento de Marketing canal.

## Valores de dimensión

Los valores de dimensión dependen de la lista desplegable de valores de canal. Por ejemplo, si establece el valor del canal en &#39;Dirección URL de la página&#39;, los valores de dimensión incluyen las direcciones URL de la página en el sitio. Si establece el valor del canal en Dominio de referencia, los valores de dimensión incluyen los dominios en los que se ha hecho clic el visitante para llegar al sitio. Esta dimensión agrega todos los valores de dimensión de detalle, independientemente del canal en el que se encuentren.

Adobe recomienda configurar los valores de canal relacionados con el canal de marketing para obtener más información sobre los detalles del canal.
