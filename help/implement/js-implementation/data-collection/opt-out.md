---
description: 'null'
keywords: Implementación de análisis
seo-description: 'null'
seo-title: Implementación de exclusiones de Adobe
solution: Analytics
title: Implementación de exclusiones de Adobe
topic: Desarrollador e implementación
uuid: fc 3 a 411 c -8476-409 d -99 de -05 b 34 ace 5019
translation-type: tm+mt
source-git-commit: b59e232b98c7e180478103ac2939a2c8c64a1407

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

## Opt-outs for Adobe Analytics (including Reports &amp; Analytics, Data Warehouse, Ad Hoc Analysis) {#section_8089B80CDA4043C9BC2DED49E484E8D7}

Adobe offers three types of opt-outs for Adobe Analytics (including [!UICONTROL Reports &amp; Analytics], [!UICONTROL Data Warehouse], [!UICONTROL Ad Hoc Analysis]):

* Si implementa productos de Adobe Analytics con su propia cookie de origen, debe [desarrollar su propio vínculo de no participación personalizado](../../../implement/js-implementation/data-collection/opt-out-link.md#concept_C2C4F19811A445EF9E9BEAC709B568A9) para los visitantes del sitio web.
* Los clientes tienen la opción de habilitar la exclusión utilizando la configuración de cookies del explorador. Consulte [Habilitar la configuración de privacidad para las cookies de explorador](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/?f=browser_cookie_settings).

Independientemente del mecanismo de exclusión que elija, Adobe recomienda describir claramente la disponibilidad de este en la política de privacidad o por cualquier otro medio determinado por la legislación o recomendado por las prácticas recomendadas actualas.
