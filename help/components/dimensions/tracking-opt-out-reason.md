---
title: Motivo de exclusión de seguimiento
description: Previsualiza qué datos se excluirían si habilitó Configuración de privacidad.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: 4c896fe930b52e440f8b91725fa6451faaa76fc8
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 7%

---

# Motivo de exclusión de seguimiento

La dimensión &quot;Motivo de exclusión de seguimiento&quot; actúa como una previsualización de los datos que se excluirían si habilitó la Configuración de privacidad. Esta dimensión se utiliza principalmente para determinar si la implementación se vería afectada negativamente si activó [Configuración de privacidad](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) en Configuración del grupo de informes.

Las implementaciones típicas ven el 1 % o menos del tráfico general del grupo de informes en esta dimensión si la Configuración de privacidad aún no se ha habilitado. Los porcentajes superiores al 1% de todo el tráfico sugieren un posible problema de implementación que impide que AppMeasurement establezca cookies de origen.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones que aún no han habilitado [Configuración de privacidad](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). Si su organización ya ha habilitado la variable **[!UICONTROL Eliminar usuarios que han bloqueado todas las cookies]** para exploradores de escritorio y móviles, esta dimensión no contiene datos.

## Elementos de dimensión

Los elementos de dimensión incluyen `"Cookies disabled by Desktop Browser"` y `"Cookies disabled by Mobile Browser"`.

* **Cookies deshabilitadas por el explorador de escritorio**: El visitante bloqueó las cookies mediante un explorador de escritorio y **[!UICONTROL Eliminar usuarios que han bloqueado todas las cookies en los exploradores de escritorio]** está desactivado.
* **Cookies deshabilitadas por el explorador móvil**: El visitante bloqueó las cookies mediante un explorador móvil y **[!UICONTROL Eliminar usuarios que han bloqueado todas las cookies en exploradores móviles]** está desactivado.
