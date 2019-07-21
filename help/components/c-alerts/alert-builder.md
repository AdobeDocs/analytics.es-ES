---
description: 'null'
seo-description: 'null'
seo-title: Generador de alertas
title: Generador de alertas
uuid: 86 d 00 a 33-dc 99-4 dc 3-a 732-0 b 895 ba 487 bc
translation-type: tm+mt
source-git-commit: 8b2feced9fd503395d06dc12c8e5d7985ca89161

---


# Generador de alertas

>[!IMPORTANT]
>
>Intelligent Alerts are available to Adobe [!DNL Analytics] Prime and Adobe [!DNL Analytics] Ultimate customers only.

Acceda al Generador de alertas de una de las cuatro formas disponibles:

* Mediante el acceso directo siguiente en Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* By going to **[!UICONTROL Workspace]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL New Alert]**.
* Seleccione uno o más elementos de línea de la tabla improvisada, haga clic con el botón derecho y elija **[!UICONTROL Crear alerta a partir de la selección]**.
* From within a [!UICONTROL Reports &amp; Analytics] report, by going to **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]**.

La interfaz del Generador de alertas resulta familiar a quienes hayan creado segmentos o calculado métricas en [!DNL Analytics]:

![](assets/alert_builder.png)

**Nombre de la alerta**

Especifique un nombre para la alerta. El nombre de la alerta puede contener el nombre del umbral de informe o de métricas.

**Granularidad de tiempo**

Especifique cuándo desea que se compruebe la métrica: cada hora, cada día, semanalmente o mensualmente.

>[!NOTE]
>
>Para los grupos de informes con un calendario personalizado, no es compatible con la granularidad mensual en el Generador de alertas.

**Destinatarios**

Especifique hacia dónde se puede enviar la alerta. An alert can be sent to an [!DNL Analytics] user, an [!DNL Analytics] group, a raw email address, or to a phone number.

>[!IMPORTANT]
>
>The phone number must be preceded by a "+" and a [country code](https://countrycode.org/).

**Fecha de caducidad**

Establezca la fecha de caducidad de la alerta.

**Enviar una alerta cuando...**

*... se active cualquiera de estas métricas*

* Arrastre y suelte las métricas en el lienzo para añadir activadores.

   Note that an **"incompatible components”** message will appear if not all the components (metrics/dimensions/segments) in the alert are compatible with the currently selected report suite.

* Determine el umbral que debe superar la métrica para que se establezca la alerta. Puede ajustar este valor a un umbral y, a continuación, a una de las condiciones siguientes:

   * existe anomalía
   * anomalía por encima de lo esperado
   * anomalía por debajo de lo esperado
   * la anomalía supera
   * es mayor que o igual a
   * es menor que o igual a
   * cambia por un

* “La anomalía supera” es una nueva condición que va más allá de los umbrales (estáticos) existentes. Utiliza los algoritmos de Detección de anomalías para definir de forma dinámica el activador. Puede establecer el umbral en 90 %, 95 %, 99 %, 99,75 % y 99,9 %.
* La granularidad por horas se establece en el umbral del 99,75 %, mientras que la granularidad diaria se establece en el 99 %.
* Tenga en cuenta que también puede utilizar las métricas calculadas.

*... con estos filtros*

Arrastre y suelte los segmentos o dimensiones para añadir filtros. Por ejemplo, si añade un segmento “Solo dispositivos móviles” significará que la regla solamente se activará para los dispositivos móviles.

Se añadirán filtros adicionales mediante una declaración AND.

**Agregar una regla**

Puede añadir las reglas AND u OR si hace clic en el icono de engranaje.

## Vista previa de alertas {#section_10D75BA7B77E4C5FAF58A719C082E070}

La vista previa de alertas interactiva le muestra con qué frecuencia, aproximada, se activará una alerta en función de las experiencias pasadas.

Por ejemplo, si establece la granularidad de tiempo a diario, en la vista previa podrá ver cuántas veces se habrá activado una alerta para una métrica en particular durante los últimos 30 o 31 días.

Si observa que se habían activado demasiadas alertas, puede ajustar el umbral en el [Administrador de alertas](/help/components/c-alerts/alert-manager.md).

![](assets/alert_preview.png)
