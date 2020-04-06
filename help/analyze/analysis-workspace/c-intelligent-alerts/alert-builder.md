---
description: 'null'
title: Generador de alertas
uuid: ebc2d457-4abd-4b1a-9357-489b5aeb3f64
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Generador de alertas

>[!IMPORTANT]
>
>Las alertas inteligentes están disponibles solo para los clientes de Adobe Analytics Prime y Adobe Analytics Ultimate.

## Acceso al Generador de alertas

Acceda al Generador de alertas de una de las cuatro maneras siguientes:

* Mediante el siguiente método abreviado en Espacio de trabajo de Análisis:

   `ctrl (or cmd) + shift + a`
* Accediendo a **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]**.
* By selecting one or more freeform table line items, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**.
* Desde un informe de Informes y análisis, vaya a **[!UICONTROL More]** > **[!UICONTROL Add Alert]**.

## Generar alertas

La interfaz del Generador de alertas resulta familiar a quienes hayan creado segmentos o calculado métricas en Analytics:

![](assets/alert_builder.png)

<!--Meike, I edited this table for validation -->

**Nombre de la alerta**

Especifique un nombre para la alerta. El nombre de la alerta puede contener el nombre del umbral del informe o de las métricas.

**Granularidad de tiempo**

Especifique cuándo desea que se compruebe la métrica: cada hora, cada día, semanalmente o mensualmente.

>[!NOTE] La granularidad mensual no es compatible con los grupos de informes con un calendario personalizado en el Generador de alertas.

**Destinatarios**

Especifique hacia dónde se puede enviar la alerta. Se puede enviar una alerta a un usuario de Analytics, a un grupo de Analytics, a una dirección de correo electrónico sin procesar o a un número de teléfono.

>[!IMPORTANT]
>
>El número de teléfono debe estar precedido por “+” y un [código de país](https://countrycode.org/).

El correo electrónico que el usuario recibe una vez que se activa una alerta tiene un aspecto similar al siguiente:

![](assets/alerts-email.PNG)

**Fecha de caducidad**

Establezca la fecha de caducidad de la alerta.

**Enviar una alerta cuando...**

*... se active cualquiera de estas métricas*

* Arrastre y suelte las métricas en el lienzo para añadir activadores.

   Si alguno de los componentes (métricas, dimensiones o segmentos) de la alerta no es compatible con el grupo de informes seleccionado, aparecerá un mensaje **“componentes no compatibles”**.
* Determine el umbral que debe superar la métrica antes de que se establezca una alerta. Puede establecer este valor en un umbral y, a continuación, en una de las siguientes condiciones:

   * existe una anomalía
   * la anomalía es mayor de lo esperado
   * la anomalía es menor de lo esperado
   * es superior o igual a
   * es menor o igual que
   * cambia por
   * Puede establecer el umbral en 90 %, 95 %, 99 %, 99,75 % y 99,9 %.
   Tenga en cuenta que también puede utilizar las métricas calculadas.

*... con estos filtros*

* Arrastre y suelte segmentos o dimensiones para añadir filtros. Por ejemplo, si se agrega un segmento &quot;Solo dispositivos móviles&quot;, la regla solo se activará para dispositivos móviles.
* Se agregarán filtros adicionales mediante una instrucción AND.

**Agregar una regla**

Puede añadir las reglas AND u OR si hace clic en el icono de engranaje.

## Vista previa de alertas {#section_10D75BA7B77E4C5FAF58A719C082E070}

La previsualización de alerta interactiva muestra con qué frecuencia, aproximadamente, se activará una alerta en función de la experiencia anterior.

Por ejemplo, si establece la granularidad de tiempo en diaria, la previsualización puede indicarle que la alerta se habría activado para una métrica determinada x veces durante los últimos 30 o 31 días.

Si descubre que se habrían activado demasiadas alertas, puede ajustar el umbral en el Administrador de [alertas](/help/components/c-alerts/alert-manager.md).

![](assets/alert_preview.png)
