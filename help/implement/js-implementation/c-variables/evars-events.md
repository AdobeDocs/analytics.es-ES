---
description: 'Si desea rastrear información adicional pero no tiene suficientes variables para hacerlo, ahora tiene acceso a eVars y eventos de éxito adicionales '
keywords: Analytics Implementation;evars;events;evars number;how many evars;how many events
title: Eventos y eVars adicionales
topic: Developer and implementation
uuid: 6f53069b-6941-40f1-9db6-2d1839822b8f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Eventos y eVars adicionales

Si desea rastrear información adicional pero no tiene suficientes variables para hacerlo, ahora tiene acceso a eVars y eventos de éxito adicionales:

> [!NOTE] El código H de JavaScript no admite estos eventos y eVars adicionales.

## Derechos a dimensiones y eventos personalizados {#section_869EC3D8A5614036A9C586F2B74FA7DC}

| Producto de Adobe Analytics |  |  |  |
|---|---|---|---|
| Adobe Analytics - Foundation | 75 props | 200 eVars | 1000 eventos |
| Adobe Analytics - [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html) | 75 props | 200 eVars | 1000 eventos |
| Adobe Analytics - [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html) | 75 props | 200 eVars | 1000 eventos |
| Adobe Analytics - [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) | 75 props | 250 eVars | 1000 eventos |

## Rellenar variables y eventos {#section_DEA51A22BCBB4B92BDD25814AAD296E4}

* Las variables se pueden rellenar en la biblioteca de recopilación de datos si está utilizando una de estas versiones de [!DNL AppMeasurement]:

   * AppMeasurement para JavaScript versión 1.4+
   * AppMeasurement para Flash versión 3.9+
   * AppMeasurement para Java versión 1.2.8+
   * AppMeasurement para Silverlight/.NET versión 1.4.2+
   * AppMeasurement para PHP versión 1.2.2+

* Si está en una versión de código anterior o en JavaScript H*, puede rellenar los datos de contexto y utilizar las reglas de procesamiento para rellenar las variables.
* Todas las versiones de código de recopilación de datos pueden rellenar los eventos 101 a 1000.
* Las reglas de procesamiento se pueden utilizar para rellenar los eVars 76 a 250 basándose en datos de contexto u otras variables.

## Preguntas frecuentes {#section_E915B03236BD47DCA065F1FC5A6E30C6}

* **¿Tendrán todas las interfaces de Adobe Analytics acceso inmediato a estas variables nuevas?** Estas interfaces permiten acceder a lo siguiente: [!UICONTROL Analysis Workspace], [!UICONTROL Reports &amp; Analytics], [!UICONTROL Report Builder], [!UICONTROL Ad Hoc Analysis], API y [!UICONTROL Data Workbench].

* **¿Se mostrarán los eVars y eventos adicionales de forma automática en mis fuentes de datos?** Las fuentes de datos tendrán acceso a las nuevas variables y eventos una vez se hayan activado. Las nuevas columnas de eVar no aparecerán hasta que elija incluirlas. Sin embargo, los eventos nuevos aparecerán en la columna event_list en cuanto estén habilitados y la tabla de búsqueda de eventos contendrá los nombres de eventos para esos ID de evento. No active los eventos nuevos a menos que esté preparado para consumirlos en las Fuentes de datos.

* **¿Cómo puedo solicitar nuevas columnas de fuentes de datos?** Para solicitar columnas nuevas, refiérase a [Configuración de fuentes de datos](https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_configure.html).

* **¿Qué sucede si soy un cliente de Analytics Ultimate que quiere volver a Analytics Prime y, actualmente, tengo más de 200 eVars activadas?** Adobe no desactivará ninguna de las eVars existentes, pero no podrá activar más. Si desactiva eVars, no podrá volver a activarlas hasta que se encuentre por debajo del límite de 200 eVars activadas de Analytics Prime.

