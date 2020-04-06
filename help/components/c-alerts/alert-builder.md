---
description: 'null'
title: Generador de alertas
uuid: 86d00a33-dc99-4dc3-a732-0b895ba487bc
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Generador de alertas

>[!IMPORTANT]
>
>Las alertas inteligentes están disponibles solo para los clientes de Adobe [!DNL Analytics] Prime y Adobe [!DNL Analytics] Ultimate.

Acceda al Generador de alertas de una de las cuatro maneras siguientes:

* Mediante el siguiente método abreviado en Espacio de trabajo de Análisis:

   `ctrl (or cmd) + shift + a`
* Accediendo a **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]**.
* By selecting one or more freeform table line items, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**.
* Desde un [!UICONTROL Reports & Analytics] informe, vaya a **[!UICONTROL More]** > **[!UICONTROL Add Alert]**.

La interfaz del Generador de alertas resulta familiar a quienes hayan creado segmentos o calculado métricas en [!DNL Analytics]:

![](assets/alert_builder.png)

**Nombre de la alerta**

Especifique un nombre para la alerta. El nombre de la alerta puede contener el nombre del umbral del informe o de las métricas.

**Granularidad de tiempo**

Especifique cuándo desea que se compruebe la métrica: cada hora, cada día, semanalmente o mensualmente.

>[!NOTE] La granularidad mensual no es compatible con los grupos de informes con un calendario personalizado en el Generador de alertas.

**Destinatarios**

Especifique hacia dónde se puede enviar la alerta. Se puede enviar una alerta a un usuario de [!DNL Analytics], un grupo de [!DNL Analytics] o a una dirección de correo electrónico sin procesar o a un número de teléfono.

>[!IMPORTANT]
>
>El número de teléfono debe estar precedido por “+” y un [código de país](https://countrycode.org/).

**Fecha de caducidad**

Establezca la fecha de caducidad de la alerta.

**Enviar una alerta cuando...**

*... se active cualquiera de estas métricas*

* Arrastre y suelte las métricas en el lienzo para añadir activadores.

   Tenga en cuenta que si alguno de los componentes (métricas, dimensiones o segmentos) de la alerta no es compatible con el grupo de informes seleccionado, aparecerá un mensaje **“componentes no compatibles”**.

* Determine el umbral que debe superar la métrica antes de que se establezca una alerta. Puede establecer este valor en un umbral y, a continuación, en una de las siguientes condiciones:

   * existe una anomalía
   * la anomalía es mayor de lo esperado
   * la anomalía es menor de lo esperado
   * la anomalía supera
   * es superior o igual a
   * es menor o igual que
   * cambia por

* &quot;La anomalía supera&quot; es una nueva condición que va más allá de los umbrales (estáticos) existentes. Extrae los algoritmos de detección de anomalías que definen dinámicamente el activador. Puede establecer el umbral en 90 %, 95 %, 99 %, 99,75 % y 99,9 %.
* Las granularidades por hora se establecen en un umbral del 99,75 % y las granularidades diarias en el 99 %.
* Tenga en cuenta que también puede utilizar las métricas calculadas.

*... con estos filtros*

Arrastre y suelte segmentos o dimensiones para añadir filtros. Por ejemplo, si se agrega un segmento &quot;Solo dispositivos móviles&quot;, la regla solo se activará para dispositivos móviles.

Se agregarán filtros adicionales mediante una instrucción AND.

**Agregar una regla**

Puede añadir las reglas AND u OR si hace clic en el icono de engranaje.

## Vista previa de alertas {#section_10D75BA7B77E4C5FAF58A719C082E070}

La previsualización de alerta interactiva muestra con qué frecuencia, aproximadamente, se activará una alerta en función de la experiencia anterior.

Por ejemplo, si establece la granularidad de tiempo en diaria, la previsualización puede indicarle que la alerta se habría activado para una métrica determinada x veces durante los últimos 30 o 31 días.

Si descubre que se habrían activado demasiadas alertas, puede ajustar el umbral en el Administrador de [alertas](/help/components/c-alerts/alert-manager.md).

![](assets/alert_preview.png)
