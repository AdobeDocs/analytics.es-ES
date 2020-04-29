---
description: Determina la cantidad de ingresos generados entre todos los productos durante un período de tiempo específico.
title: Ingresos
topic: Reports
uuid: e5b72798-f5c7-440d-a62d-376bfd115ac8
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Ingresos

Determina la cantidad de ingresos generados entre todos los productos durante un período de tiempo específico.

Utilice Ingresos para comprobar el nivel de éxito general y la tendencia de su sitio. También puede usarlo para señalar períodos en los que el sitio funcionó especialmente bien, para buscar la causa de ello y utilizarla en futuras campañas.

## Propiedades generales del informe {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* A continuación se indican los requisitos que deben cumplirse para que este informe pueda recopilar datos correctamente. En la misma solicitud de imagen, debe suceder lo siguiente:

   * A [!UICONTROL purchase] event must fire in the `s.events` variable.

   * La variable `products` debe aparecer definida con un número en el campo de precio.
   * Por ejemplo, en este caso se pasarían 35,99 $ al informe de ingresos:

      ```js
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js
       s.events="purchase"
      ```

* Si hay más de un producto presente en la variable [!UICONTROL s.products], todos se contabilizarán en el informe de ingresos. Por ejemplo: [!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] pasaría 9 dólares en ingresos a los informes.

   >[!NOTE]
   >
   >Los ingresos no se multiplican si la cantidad se incrementa en un solo producto. Por ejemplo, [!DNL s.products="Womens;Socks;5;4.50"] no pasa a 22,50 $ a los informes, sino que pasa 4,50 $. Compruebe que la implementación pasa los ingresos totales en relación con la cantidad enumerada ([!DNL s.products="Womens;Socks;5;22.50"]).

* [!UICONTROL Revenue] redondea la cantidad total de un período de tiempo al valor de moneda más cercano. No redondea cada producto individual o entrada.
* Como Analytics redondea cada día a la divisa entera más cercana, la suma de cada día estará mínimamente desajustada si se compara con el total mensual. Esto se debe a que el total mensual no es la suma de cada día redondeado, sino la suma absoluta redondeada a la divisa entera más cercana.
* Puede crear un informe que no redondee los ingresos a la divisa entera más cercana. Para ello, utilice una  [métrica calculada](https://docs.adobe.com/content/help/es-ES/analytics/components/calculated-metrics/cm-overview.html).
* Salvo que se utilice la variable `purchaseID`, es posible que los usuarios que actualicen la página aumenten los ingresos ya que, al hacerlo, enviarán estos datos a Adobe varias veces.
* Los desgloses por hora se basan en el huso horario del grupo de informes.
* Este informe no contiene elementos de línea. Solo puede verse en formato de tendencias.
* Se puede aplicar una granularidad de hora, día, semana, mes, trimestre y año. Estas granularidades están disponibles en función del intervalo de fechas de los informes.
* Este informe puede desglosarse en los siguientes informes (en función de la organización y la configuración del grupo de informes):

   * [!UICONTROL Time Spent per Visit] informe.
   * [!UICONTROL Pages and Site Sections] informe.
   * [!UICONTROL Videos] informe.
   * [!UICONTROL Page Depth and Entry Pages] informe.
   * La mayoría de [!UICONTROL Traffic Sources]los informes, incluidos [!UICONTROL Search Keywords], [!UICONTROL Search Engines]e informes [!UICONTROL Referring Domains] .

   * [!UICONTROL Tracking Code] y todos los informes de clasificación asociados.
   * [!UICONTROL Products variable] y todos los informes de clasificación asociados. También [!UICONTROL Categories] informes.

   * Casi todos [!UICONTROL Visitor Profile] los informes, excluidos [!UICONTROL GeoSegmentation] los informes.

   * Todos los informes [!UICONTROL Custom Conversion] de variables con subrelaciones básicas.

* Los desgloses no están disponibles por hora.

## Propiedades específicas de productos  {#section_ED87FFD020634453AABE86B0248BE69B}

* Para acceder a este informe, vaya a **[!UICONTROL Conversion]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* [!UICONTROL Traffic Sources] los desgloses se encuentran en [!UICONTROL Finding Methods].

* Para acceder a este informe, vaya a **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* Además de todos los desgloses enumerados anteriormente, hay disponibles [!UICONTROL First and Last Touch Marketing Channel] desgloses.

* Para acceder a este informe, vaya a **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* In addition to the previously mentioned breakdowns, [!UICONTROL List]variables and the current [!UICONTROL Video] variables can be used.

* Este informe puede utilizar segmentos.

* Puede desglosar cada elemento de este informe según otros informes y variables, lo que permite ver los desgloses con cualquier granularidad que desee.
* Puede utilizar todas [!UICONTROL conversion] las métricas y [!UICONTROL traffic] junto con [!UICONTROL Revenue]. You can use different allocation for all [!UICONTROL conversion] metrics.

* Este informe puede utilizar varios segmentos muy avanzados.

Si este informe no está disponible en la ubicación especificada, consulte a su administrador. Es posible que hayan cambiado el nombre predeterminado o la estructura de menús para adaptarlos a las necesidades específicas de su organización.
