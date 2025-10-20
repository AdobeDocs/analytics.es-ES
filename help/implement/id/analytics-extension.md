---
title: Identificación de visitantes con la extensión de etiquetas de Adobe Analytics
description: Identifique correctamente a los visitantes al implementar la extensión de etiquetas de Adobe Analytics.
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# Identificación de visitantes con la extensión de etiquetas de Adobe Analytics

La extensión de etiquetas de Adobe Analytics proporciona permite implementar AppMeasurement mediante una interfaz de administración de etiquetas. Como esta extensión de etiquetas es esencialmente AppMeasurement, ofrece métodos similares para identificar a los visitantes y requiere una extensión de etiqueta independiente para el servicio de ID de visitante.

## Identificación de visitantes mediante el servicio de ID de visitante (recomendado)

Para utilizar el servicio de ID de visitante con la extensión de etiqueta de Adobe Analytics, incluya la extensión de etiqueta del servicio de Experience Cloud ID en la propiedad de etiqueta.

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com) con sus credenciales de Adobe ID.
1. Vaya a **[!UICONTROL Recopilación de datos]** > **[!UICONTROL Etiquetas]**.
1. Busque la propiedad de etiquetas deseada.
1. Vaya a **[!UICONTROL Extensions]** y, a continuación, seleccione la pestaña **[!UICONTROL Catalog]**.
1. Busque la extensión **[!UICONTROL Experience Cloud ID Service]** y, a continuación, seleccione **[!UICONTROL Instalar]**.

La extensión de etiqueta obtiene automáticamente el ID de organización de IMS, por lo que no es necesaria ninguna configuración adicional.

## Identificación de visitantes mediante la cookie `s_vi` (no recomendado)

>[!IMPORTANT]
>
>Adobe recomienda evitar este método para identificar a los visitantes.

Si su organización no utiliza la extensión de etiqueta del servicio de ID de visitante, la extensión de etiqueta de Adobe Analytics utilizará su propia forma de identificación del visitante. Cuando un visitante llega a su sitio por primera vez, la extensión comprueba la existencia de una cookie [`s_vi`](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/cookies/analytics). Esta cookie se establece en el dominio que coincide con **[!UICONTROL SSL Tracking Server]** (para HTTPS) o **[!UICONTROL Tracking Server]** (para HTTP) al [configurar la extensión de etiqueta](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/analytics/overview).

* Si participa en el [programa de certificados administrados](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/adobe-managed-cert), su servidor de seguimiento sería normalmente un dominio de origen, por lo que las cookies de `s_vi` serían de origen.
* Si no participa en el programa de certificados administrados, el servidor de seguimiento suele ser un subdominio de `adobedc.net`, `omtrdc.net` o `2o7.net`, por lo que la cookie `s_vi` se convierte en una cookie de terceros. Debido a los estándares modernos de privacidad del explorador, la mayoría de los exploradores rechazan las cookies de terceros. Una vez rechazado, AppMeasurement intenta establecer una cookie de reserva (`fid`) de origen en su lugar.

Si establece correctamente [!UICONTROL Servidor de seguimiento SSL], no se requieren más medidas de identificación de visitantes.

## Identificación de visitantes que utilizan `visitorID` (no recomendado)

>[!IMPORTANT]
>
>Adobe recomienda evitar este método para identificar a los visitantes.

El uso de la variable **[!UICONTROL ID de visitante]** permite que su organización complete el control independiente que identifica a los visitantes. Si establece [!UICONTROL ID de visitante] con un elemento de datos, tenga en cuenta las siguientes limitaciones:

* Cada visita debe contener el mismo valor de [!UICONTROL ID de visitante] que se contará como un visitante individual.
   * Cualquier visita que omita el elemento de datos [!UICONTROL ID de visitante] intenta usar automáticamente otro método de identificación de visitante, tratándolo como un visitante separado.
   * Cualquier visita que contenga un valor de [!UICONTROL ID de visitante] diferente al de una visita anterior se tratará como un visitante independiente.
   * Adobe no ofrece ninguna forma de unir las visitas con distintos ID de visitante.
* Las audiencias compartidas, Analytics para Target y los atributos del cliente no son compatibles con los visitantes identificados con [!UICONTROL ID de visitante].

Consulte [`visitorID`](/help/implement/vars/config-vars/visitorid.md) para obtener instrucciones de implementación mediante esta variable.
