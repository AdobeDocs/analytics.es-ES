---
title: Detalles del canal de primer toque
description: Detalles del primer canal de marketing dentro de la caducidad del compromiso del visitante.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---


# Detalles del canal de primer toque

Los informes de dimensión &#39;Detalles de canal de primer toque&#39; detallan el primer canal de marketing con el que coincide un visitante durante el período de participación de ese visitante (de forma predeterminada, 30 días). Esta dimensión es valiosa para comprender qué contribuyó a que la visita coincidiera con un canal de marketing. Por ejemplo: si un visitante llegó a su sitio y coincidió con el canal de mercadotecnia de &#39;Búsqueda paga&#39;, puede utilizar el detalle de canal para ver qué motor de búsqueda se utilizó o qué palabra clave buscó.

## Rellenar esta dimensión con datos

Esta dimensión copia valores de otras variables. La variable utilizada hace referencia al valor de canal dentro de cada regla [de procesamiento](/help/admin/admin/marketing-channels-admin.md)de Marketing canal. Cuando una visita individual coincide con una regla de procesamiento de canal de marketing, la dimensión de canal [de](last-touch-channel.md) último toque se establece en el nombre del canal y esta dimensión se establece en el valor de canal establecido en la regla.

Si desea establecer esta dimensión en un valor específico, se requieren los siguientes pasos:

* Asegúrese de que el elemento de dimensión deseado esté en un atributo de visita o en una variable personalizada.
* Establezca una regla de procesamiento de Marketing canal que contenga los criterios deseados para la visita.
* Seleccione el valor desplegable que desee en [!UICONTROL Definir el valor] del canal dentro de la regla de procesamiento de Marketing canal.
* La visita del visitante a su sitio debe coincidir con los criterios descritos en la regla de procesamiento de Marketing canal __ y debe ser el primer valor de canal de mercadotecnia que lo haga en el período de compromiso del visitante.

Si una visita posterior coincide con criterios de un canal de marketing diferente, esta dimensión no se sobrescribe con el nuevo canal de marketing.

## Elementos de dimensión

Los elementos de dimensión dependen de la lista desplegable de valores de canal. Por ejemplo, si establece el valor del canal en &#39;Dirección URL de la página&#39;, los elementos de dimensión incluyen direcciones URL de la página en el sitio. Si establece el valor del canal en Dominio de referencia, los elementos de dimensión incluyen los dominios en los que se hizo clic el visitante para llegar al sitio. Esta dimensión agrega todos los elementos de dimensión detallados, independientemente del canal en el que se encuentren.

Adobe recomienda configurar los valores de canal relacionados con el canal de marketing para obtener más información sobre los detalles del canal.
