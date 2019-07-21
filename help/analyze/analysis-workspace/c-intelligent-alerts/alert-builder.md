---
description: 'null'
seo-description: 'null'
seo-title: Generador de alertas
title: Generador de alertas
uuid: ebc 2 d 457-4 abd -4 b 1 a -9357-489 b 5 aeb 3 f 64
translation-type: tm+mt
source-git-commit: 4b47e33d964c040cf94dc1c4ad97e43958d9d94a

---


# Generador de alertas

>[!IMPORTANT]
>
>Las alertas inteligentes solo están disponibles para los clientes de Adobe Analytics Prime y Adobe Analytics Ultimate.

## Generador de alertas de acceso

Acceda al Generador de alertas de una de las cuatro formas disponibles:

* Mediante el acceso directo siguiente en Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* By going to **[!UICONTROL Workspace]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL New Alert]**.
* Seleccione uno o más elementos de línea de la tabla improvisada, haga clic con el botón derecho y elija **[!UICONTROL Crear alerta a partir de la selección]**.
* From within a Reports &amp; Analytics report, by going to **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]**.

## Generar alertas

La interfaz del Generador de alertas resulta familiar a quienes hayan creado segmentos o calculado métricas en Analytics:

![](assets/alert_builder.png)

<!--Meike, I edited this table for validation -->

**Nombre de la alerta**

Especifique un nombre para la alerta. El nombre de la alerta puede contener el nombre del umbral de informe o de métricas.

**Granularidad de tiempo**

Especifique cuándo desea que se compruebe la métrica: cada hora, cada día, semanalmente o mensualmente.

>[!NOTE]
>
>Para los grupos de informes con un calendario personalizado, no es compatible con la granularidad mensual en el Generador de alertas.

**Destinatarios**

Especifique hacia dónde se puede enviar la alerta. Se puede enviar una alerta a un usuario de Analytics, un grupo de Analytics o a una dirección de correo electrónico sin procesar o a un número de teléfono.

>[!IMPORTANT]
>
>The phone number must be preceded by a "+" and a [country code](https://countrycode.org/).

El correo electrónico que un usuario recibe una vez que se ha activado una alerta similar a esta:

![](assets/alerts-email.PNG)

**Fecha de caducidad**

Establezca la fecha de caducidad de la alerta.

**Enviar una alerta cuando...**

*... se active cualquiera de estas métricas*

* Arrastre y suelte las métricas en el lienzo para añadir activadores.

   An **"incompatible components”** message will appear if not all the components (metrics/dimensions/segments) in the alert are compatible with the currently selected report suite.
* Determine el umbral que debe superar la métrica para que se establezca la alerta. Puede ajustar este valor a un umbral y, a continuación, a una de las condiciones siguientes:

   * existe anomalía
   * anomalía por encima de lo esperado
   * anomalía por debajo de lo esperado
   * mayor o igual que
   * es menor que o igual a
   * cambia por un
   * Puede establecer el umbral en 90 %, 95 %, 99 %, 99,75 % y 99,9 %.
   Tenga en cuenta que también puede utilizar las métricas calculadas.

*... con estos filtros*

* Arrastre y suelte los segmentos o dimensiones para añadir filtros. Por ejemplo, si añade un segmento “Solo dispositivos móviles” significará que la regla solamente se activará para los dispositivos móviles.
* Se añadirán filtros adicionales mediante una declaración AND.

**Agregar una regla**

Puede añadir las reglas AND u OR si hace clic en el icono de engranaje.

## Preview Alerts {#section_10D75BA7B77E4C5FAF58A719C082E070}

La vista previa de alertas interactiva le muestra con qué frecuencia, aproximada, se activará una alerta en función de las experiencias pasadas.

Por ejemplo, si establece la granularidad de tiempo a diario, en la vista previa podrá ver cuántas veces se habrá activado una alerta para una métrica en particular durante los últimos 30 o 31 días.

Si observa que se habían activado demasiadas alertas, puede ajustar el umbral en el [Administrador de alertas](/help/components/c-alerts/alert-manager.md).

![](assets/alert_preview.png)
