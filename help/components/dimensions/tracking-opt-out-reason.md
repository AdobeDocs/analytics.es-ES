---
title: Motivo de exclusión de seguimiento
description: Previsualiza qué datos se excluirán si habilita la Configuración de privacidad.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 7%

---

# Motivo de exclusión de seguimiento

*Esta página hace referencia a la [dimensión](overview.md) que le permite ver el posible impacto de los datos al habilitar ciertas opciones de configuración del grupo de informes. No está relacionado con el [servicio de inclusión de Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=es).*

La dimensión &quot;Razón de exclusión de seguimiento&quot; actúa como una previsualización de los datos que se excluirían si se habilita la Configuración de privacidad. Esta dimensión se usa principalmente para determinar si su implementación se vería afectada negativamente si habilitó [Configuración de privacidad](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html?lang=es) en Configuración del grupo de informes.

Las implementaciones típicas ven un 1% o menos del tráfico total del grupo de informes en esta dimensión si la configuración de privacidad aún no se ha habilitado. Los porcentajes superiores al 1 % de todo el tráfico sugieren un posible problema de implementación que impide que AppMeasurement establezca cookies de origen.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones que aún no han habilitado [Configuración de privacidad](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html?lang=es). Si su organización ya ha habilitado la configuración **[!UICONTROL Eliminar usuarios que bloquearon todas las cookies]** tanto para el escritorio como para los exploradores móviles, esta dimensión no contiene datos.

## Elementos de dimensión

Los elementos de dimensión incluyen `"Cookies disabled by Desktop Browser"` y `"Cookies disabled by Mobile Browser"`.

* **Cookies deshabilitadas por el explorador de escritorio**: El visitante bloqueó las cookies usando un explorador de escritorio y **[!UICONTROL Quitar usuarios que bloquearon todas las cookies en exploradores de escritorio]** está deshabilitado.
* **Cookies deshabilitadas por el explorador móvil**: El visitante bloqueó las cookies mediante un explorador móvil y **[!UICONTROL Quitar usuarios que bloquearon todas las cookies en exploradores móviles]** está deshabilitado.
