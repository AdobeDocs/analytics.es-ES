---
description: 'null'
keywords: Analytics Implementation
title: Implementación de exclusiones de Adobe
topic: Developer and implementation
uuid: fc3a411c-8476-409d-99de-05b34ace5019
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implementación de exclusiones de Adobe

Es posible que algunos visitantes de un sitio web no deseen que su información de navegación se agregue a servicios y productos de Adobe Experience Cloud, se analice con estos, o se use con fines publicitarios o para proporcionar contenido relevante. Adobe permite especificar a los visitantes de un sitio web que así lo consideren que no desean que su información se recopile con los productos de Adobe siguientes:

* Adobe Analytics
* Adobe Target
* Adobe Audience Targeted Creative
* Adobe AudienceManager
* Adobe AdLens
* Adobe Experience Manager 

## Recomendaciones sobre la política de privacidad {#section_BBDEE21C259842F7881642E31FB3D9B7}

Adobe recomienda proporcionar a los visitantes de un sitio web información fácilmente accesible y comprensible sobre la posibilidad de expresar su disconformidad frente a la recopilación de su información de navegación por parte de los servicios y productos de Adobe.

Los visitantes pueden obtener más información sobre el uso que Adobe suele realizar de la información que recopila para ofrecer productos y servicios a sus clientes en el [Centro de privacidad de Adobe](https://www.adobe.com/privacy.html). No obstante, usted ejerce el control exclusivo sobre cómo implementar nuestros servicios en sus sitios web y, por tanto, usted decide si desea describir a los visitantes los medios específicos de los que disponen para usar los productos y servicios de Adobe. Usted es el responsable de crear su propia política de privacidad, de su cumplimiento, de su cumplimiento a través de un contrato de servicio con Adobe y de su cumplimiento a través de toda la legislación aplicable.

## Exclusión para Adobe Analytics (incluidos los Reports &amp; Analytics, Data Warehouse y Ad Hoc Analysis) {#section_8089B80CDA4043C9BC2DED49E484E8D7}

Adobe ofrece tres tipos de exclusiones para Adobe Analytics (incluidos los [!UICONTROL Reports &amp; Analytics], [!UICONTROL Data Warehouse] y [!UICONTROL Ad Hoc Analysis]):

* Si implementa productos de Adobe Analytics con su propia cookie de origen, debe [desarrollar un vínculo de exclusión personalizado](/help/implement/js-implementation/data-collection/opt-out-link.md) para los visitantes de su sitio web.
* Los clientes tienen la opción de habilitar la exclusión utilizando la configuración de cookies del explorador. Consulte [Habilitar la configuración de privacidad para las cookies de explorador](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/browser_cookie_settings.html).

Independientemente del mecanismo de exclusión que elija, Adobe recomienda describir claramente la disponibilidad de este en la política de privacidad o por cualquier otro medio determinado por la legislación o recomendado por las prácticas recomendadas actualas.
