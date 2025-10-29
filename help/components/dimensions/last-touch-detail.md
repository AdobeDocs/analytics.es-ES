---
title: Detalles de canal de último contacto
description: Detalles del canal de marketing más reciente dentro de la caducidad de la participación del visitante.
feature: Dimensions
exl-id: def03267-f3e5-4772-a707-5678c45eba6d
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 80%

---

# Detalles de canal de último contacto

Los informes de &quot;Detalles de canal de último contacto&quot; [dimension](overview.md) detallan el canal de marketing más reciente con el que coincide un visitante durante el periodo de participación de ese visitante (de forma predeterminada, 30 días). Esta dimensión es valiosa para comprender qué contribuyó a que la visita coincidiera con un canal de marketing. Por ejemplo: si un visitante llegó a su sitio y coincidió con el canal de marketing de “Búsqueda de pago”, puede utilizar el detalle de canal para ver qué motor de búsqueda se utilizó o qué palabra clave buscó.

## Rellene esta dimensión con datos

Esta dimensión copia valores de otras variables. La variable utilizada hace referencia al valor de canal dentro de cada [regla de procesamiento del canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md). Cuando una visita individual coincide con una regla de procesamiento de canal de marketing, la dimensión de [canal de último contacto](last-touch-channel.md) se establece en el nombre del canal y esta dimensión se establece en el valor de canal establecido en la regla.

Si desea establecer esta dimensión en un valor específico, se requieren los siguientes pasos:

* Asegúrese de que el elemento de dimensión deseado esté en un atributo de visita o en una variable personalizada.
* Establezca una regla de procesamiento de canal de marketing que contenga los criterios deseados para la visita.
* Seleccione el valor desplegable que desee en [!UICONTROL Establecer el valor del canal] dentro de la regla de procesamiento del canal de marketing.
* La visita del visitante al sitio debe coincidir con los criterios descritos en la regla de procesamiento del canal de marketing.

## Elementos de dimensión

Los elementos de Dimension dependen del valor de canal enumerado en la lista desplegable de para la regla de procesamiento de canal de marketing aplicable. Por ejemplo, si establece el valor del canal en “Dirección URL de la página”, los elementos de dimensión incluyen las direcciones URL de la página en el sitio. Si establece el valor del canal en Dominio de referencia, los elementos de dimensión incluyen los dominios en los que ha hecho clic el visitante para llegar al sitio. Esta dimensión agrega todos los elementos de dimensión de detalle, independientemente del canal en el que se encuentren.

Adobe recomienda configurar los valores de canal relacionados con el canal de marketing para obtener más información sobre los detalles del canal.
