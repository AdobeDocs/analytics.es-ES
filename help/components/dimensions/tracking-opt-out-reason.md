---
title: Motivo de exclusión de seguimiento
description: Previsualiza qué datos se excluirán si habilita la Configuración de privacidad.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
TQID: https://experienceleague.adobe.com/mFYYrj4iBWBi87sErHnWTYXce3lUhV0pwUt63x3vfnY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 11%

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
