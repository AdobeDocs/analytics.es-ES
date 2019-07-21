---
description: La serialización de eventos es el proceso de implementación de medidas para evitar que los informes de Analytics incluyan eventos duplicados. Esto se suele producir cuando un usuario actualiza la página varias veces, va a una determinada página varias veces o guarda la página web en su equipo (por ejemplo, si un cliente guarda una página de confirmación de compra en su equipo, cada vez que la consultase, los pedidos y los ingresos se volverían a contar si no se aplicara la serialización de eventos).
keywords: Implementación de Analytics
seo-description: La serialización de eventos es el proceso de implementación de medidas para evitar que los informes de Analytics incluyan eventos duplicados. Esto se suele producir cuando un usuario actualiza la página varias veces, va a una determinada página varias veces o guarda la página web en su equipo (por ejemplo, si un cliente guarda una página de confirmación de compra en su equipo, cada vez que la consultase, los pedidos y los ingresos se volverían a contar si no se aplicara la serialización de eventos).
seo-title: Información general sobre la serialización de eventos
solution: Analytics
title: Información general sobre la serialización de eventos
topic: Desarrollador e implementación
uuid: 8 c 7883 bb -5 ba 4-4440-af 80-c 0 d 15867570 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Información general sobre la serialización de eventos

La serialización de eventos es el proceso de implementación de medidas para evitar que los informes de Analytics incluyan eventos duplicados. Esto se suele producir cuando un usuario actualiza la página varias veces, va a una determinada página varias veces o guarda la página web en su equipo (por ejemplo, si un cliente guarda una página de confirmación de compra en su equipo, cada vez que la consultase, los pedidos y los ingresos se volverían a contar si no se aplicara la serialización de eventos).

La [!UICONTROL serialización de eventos] resulta útil en los siguientes casos:

* Una página se puede volver a cargar o actualizar y enviar repetidamente un evento. La [!UICONTROL serialización de eventos] usa un número de serie para cada evento para evitar que se vuelvan a contar.
* El usuario guarda la página en su equipo para verla más tarde. Este escenario es bastante común en páginas de confirmación de compra con el fin de revisar los recibos de compra. La [!UICONTROL serialización de eventos] evita que las posteriores recargas de la página vuelvan a contar los eventos.

>[!NOTE]
>
>Las fuentes de datos no admiten la serialización de eventos ni la anulación de duplicación.

Este documento describe el proceso utilizado en la implementación de la [!UICONTROL serialización de eventos] para los eventos [!UICONTROL conversion] y [!UICONTROL custom]. To use [!UICONTROL Event serialization], you must first enable it in  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL[select report suite]]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Success Events]** . A continuación, seleccione qué eventos desea registrar en la columna [!UICONTROL Grabación de eventos únicos].

## Comportamiento predeterminado {#section_892BB2BEFC434B69869D4504A8B54308}

El comportamiento predeterminado es que cada instancia de un evento se cuente una vez. Se establece un evento para cada [!UICONTROL vista de página] que se cuente, incluso aunque la página se vuelva a cargar o se actualice. La variable [!UICONTROL s.purchaseID] se usa para identificar cada pedido (compra) de forma única. Esto permite al usuario volver a cargar la página de pedido sin volver a contar el pedido, los ingresos o los productos. Hay una función similar para todos los eventos. Esto incluye eventos predefinidos como [!UICONTROL prodView] y [!UICONTROL scCheckout], así como todos los eventos personalizados.

<!-- 

event_serialization_impl.xml

 -->

To use [!UICONTROL Event serialization], you must first enable it in  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL[select report suite]]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Success Events]** . A continuación, seleccione qué eventos desea registrar en la columna [!UICONTROL Grabación de eventos únicos]. Hay tres valores distintos con los que se puede configurar un evento.

**Registrar siempre el evento**: este es el comportamiento predeterminado de todos los eventos cuando se activan por primera vez. Todos los eventos incluidos en las solicitudes de imagen se enviarán directamente a Analytics, incluidas las recargas de páginas.

**Registrar una vez por cada visita**: un evento que tenga este valor activado realizará un seguimiento solamente de la primera instancia de dicho evento que se produzca en una visita determinada. Después de que se haya iniciado una nueva visita, se podrá volver a realizar un seguimiento de todos los eventos configurados con este valor habilitado. Este es un método efectivo que permite acabar con los eventos duplicados mediante las actualizaciones del explorador.

**Utilizar ID del evento**: este valor permite la posibilidad de asociar cada evento a un ID único. Si Analytics detecta una eventID que ya ha detectado antes con esa variable, no la contará en los informes.

El único evento en el que no se puede habilitar la serialización de eventos es el evento de compra, ya que usa la variable s.purchaseID. El resto de los eventos de comercio electrónico y de los eventos personalizados pueden tener esta configuración habilitada.

* Use un identificador único para que un evento se active una vez por cada ID única.
* Envíe varios eventos y, a continuación, configure Analytics para que un evento se active una vez por visita.

Para implementar la [!UICONTROL serialización de eventos], proporcione una ID única para el evento, por ejemplo, event1:1234ABCD.

## Serialización de eventos - Una vez por ID única {#section_8806E48B497546F5A335383FB8627694}

Cuando la [!UICONTROL serialización de eventos] está implementada y [!DNL Analytics] recibe un número duplicado, omite el evento. Un evento solo se contabiliza una vez por valor único. Si el número es único, se contabiliza otra instancia del evento, como se muestra en el ejemplo siguiente:

| Nombre de usuario | Descripción | Sintaxis del evento | Recuento total de Event1 de Analytics |
|---|---|---|---|
| John | El usuario visita la página por primera vez. | event1:1000 | 1 |
| John | El usuario vuelve a cargar la página (podría ocurrir un error de envío del formulario y provocar que la página se vuelva a cargar). | event1:1000 | 1 |
| Stacy | El usuario visita la página por primera vez. | event1:1001 | 2 |
| Stacy | El usuario vuelve a cargar la página (podría ocurrir un error de envío del formulario y provocar que la página se vuelva a cargar). | event1:1001 | 2 |
| Jill | El usuario visita la página por primera vez, introduce la información correctamente y se mueve a la página siguiente. | event1:1002 | 3 |
| Jamie | El usuario visita la página por primera vez. | event1 | 4 |
| Jamie | El usuario olvida rellenar el campo de apellido del formulario. El formulario se muestra de nuevo con la información que falta resaltada. | event1 | 5 |

Al seleccionar las ID de serialización, tenga en cuenta lo siguiente:

* Las ID de serialización no deben superar los 20 caracteres.
* Las ID de serialización solo pueden contener caracteres alfanuméricos.
* Las ID de serialización son independientes para los distintos eventos de éxito. Por lo tanto, puede usar la misma ID para varios eventos de éxito si lo considera necesario (pero no para el mismo evento).
* Las ID de serialización se encuentran vinculadas a los grupos de informes. Téngalo en cuenta si decide usar el etiquetado de grupos múltiples para enviar datos a varios grupos de informes.
* Las ID de serialización nunca caducan, por lo que si se usa la misma ID años después, el evento de éxito no se contará de nuevo.
* La eliminación de cookies no impide la serialización de ID de evento, porque las ID de serialización se almacenan en servidores de Adobe y no están basadas en cookies.
* El único evento de éxito que no puede usar la serialización de ID de evento es el evento de compra, que usa una variable s.purchaseID especial para la serialización.

## Serialización de eventos - Una vez por visita {#section_C919D44F321A47FBBF043D0C57A2A050}

[!DNL Analytics] ofrece una función que permite activar un evento solo una vez por visita.

This can be enabled from the UI:  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Success Events]** .
