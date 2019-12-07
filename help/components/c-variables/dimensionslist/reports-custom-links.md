---
description: Muestra los vínculos preferidos de los visitantes al sitio. Por ejemplo, es probable que la página de inicio de un sitio tenga varios vínculos a la misma página. Tal vez haya dos vínculos, uno gráfico y otro de texto, que lleven a la misma página. Este informe muestra el porcentaje de visitantes que han utilizado el vínculo gráfico frente al de texto.
title: Sintaxis de
topic: Reports
uuid: 2e0d0175-d5e4-4919-b601-3f488ef3e090
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Sintaxis de

Muestra los vínculos preferidos de los visitantes al sitio. Por ejemplo, es probable que la página de inicio de un sitio tenga varios vínculos a la misma página. Tal vez haya dos vínculos, uno gráfico y otro de texto, que lleven a la misma página. Este informe muestra el porcentaje de visitantes que han utilizado el vínculo gráfico frente al de texto.

Para poder supervisar vínculos específicos deberá modificarlos con etiquetas especiales (consulte [Seguimiento de vínculos](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html)).

Con el [!UICONTROL Informe Vínculos personalizados] se puede:

* Averiguar qué tipo de vínculos prefieren los visitantes para optimizar el diseño del sitio.
* Confirmar la necesidad de vínculos redundantes para páginas individuales.

## Nombres de vínculos de SDK móviles  {#section_70C91FE794104B5FBF289B19CC02EA8E}

Los [SDK móviles](https://marketing.adobe.com/resources/help/en_US/mobile/home.html) usan vínculos personalizados para realizar el seguimiento de acciones y métricas del ciclo vital. En los grupos de informes que se usan para medir aplicaciones móviles, es posible que vea los siguientes nombres de vínculos establecidos por el SDK:

| ADBINTERNAL:Lifecycle | Enviado por la llamada de ciclo de vida en los SDK 4.x. |
|---|---|
| AMACTION:[nombre de acción] | Enviado por el método trackAction() en los SDK 4.x, donde el nombre de la acción es el nombre establecido durante la invocación del método. |
| Evento de ADMS BP | Enviado por la llamada de ciclo de vida en los SDK 3.x. |

