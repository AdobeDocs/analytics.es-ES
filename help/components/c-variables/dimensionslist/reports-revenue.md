---
description: Determina la cantidad de ingresos generados entre todos los productos durante un período de tiempo específico.
title: Ingresos
topic: Reports
uuid: e5b72798-f5c7-440d-a62d-376bfd115ac8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ingresos

Determina la cantidad de ingresos generados entre todos los productos durante un período de tiempo específico.

Utilice Ingresos para comprobar el nivel de éxito general y la tendencia de su sitio. También puede usarlo para señalar períodos en los que el sitio funcionó especialmente bien, para buscar la causa de ello y utilizarla en futuras campañas.

## Propiedades generales del informe {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* A continuación se indican los requisitos que deben cumplirse para que este informe pueda recopilar datos correctamente. En la misma solicitud de imagen, debe suceder lo siguiente:

   * Un evento de compra ([!UICONTROL purchase]) debe activarse en la  `s.events` campaign.

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

* [!UICONTROL Ingresos] redondea la cantidad total de un período de tiempo al valor de divisa más cercano. No redondea cada producto individual o entrada.
* Como Analytics redondea cada día a la divisa entera más cercana, la suma de cada día estará mínimamente desajustada si se compara con el total mensual. Esto se debe a que el total mensual no es la suma de cada día redondeado, sino la suma absoluta redondeada a la divisa entera más cercana.
* Puede crear un informe que no redondee los ingresos a la divisa entera más cercana. Para ello, utilice una  [métrica calculada](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/).
* Salvo que se utilice la variable `purchaseID`, es posible que los usuarios que actualicen la página aumenten los ingresos ya que, al hacerlo, enviarán estos datos a Adobe varias veces.
* Los desgloses por hora se basan en el huso horario del grupo de informes.
* Este informe no contiene elementos de línea. Solo puede verse en formato de tendencias.
* Se puede aplicar una granularidad de hora, día, semana, mes, trimestre y año. Estas granularidades están disponibles en función del intervalo de fechas de los informes.
* Este informe puede desglosarse en los siguientes informes (en función de la organización y la configuración del grupo de informes):

   * Informe de [!UICONTROL Tiempo empleado por visita].
   * Informes de [!UICONTROL Páginas y Secciones del sitio].
   * Informe de [!UICONTROL Vídeos].
   * Informes de [!UICONTROL Profundidad de página y Páginas de entrada].
   * La mayoría de los informes de [!UICONTROL fuentes de tráfico], incluyendo los informes de [!UICONTROL Palabras clave de búsqueda], [!UICONTROL Motores de búsqueda] y [!UICONTROL Dominios de referencia].

   * Informe de [!UICONTROL Código de seguimiento] y todos los informes de clasificación asociados.
   * Informe de [!UICONTROL variable products] y todos los informes de clasificación asociados. También informes de [!UICONTROL Categorías].

   * Casi todos los informes [!UICONTROL Perfil del visitante], excluyendo los informes [!UICONTROL Segmentación geográfica].

   * Todos los informes de variables de [!UICONTROL conversión personalizada] con subrelaciones básicas.

* Los desgloses no están disponibles por hora.

## Propiedades específicas de productos  {#section_ED87FFD020634453AABE86B0248BE69B}

* Puede acceder a este informe desde **[!UICONTROL Conversión]** &gt; **[!UICONTROL Compras]** &gt; **[!UICONTROL Ingresos]**.

* Los desgloses de [!UICONTROL fuentes de tráfico] se pueden encontrar en [!UICONTROL Métodos de búsqueda].

* Puede acceder a este informe desde **[!UICONTROL Métricas del sitio]** &gt; **[!UICONTROL Compras]** &gt; **[!UICONTROL Ingresos]**.

* Además de todos los desgloses enumerados anteriormente, también están disponibles los desgloses de [!UICONTROL Canal de marketing de primer toque y último toque].

* También puede acceder a este informe desde **[!UICONTROL Métricas del sitio]** &gt; **[!UICONTROL Compras]** &gt; **[!UICONTROL Ingresos]**.

* Además de los desgloses mencionados anteriormente, se pueden utilizar las variables de [!UICONTROL lista] y las variables actuales de [!UICONTROL vídeo].

* Este informe puede utilizar segmentos.

* Puede desglosar cada elemento de este informe según otros informes y variables, lo que permite ver los desgloses con cualquier granularidad que desee.
* Puede utilizar todas las métricas de [!UICONTROL conversión] y [!UICONTROL tráfico] junto con [!UICONTROL Ingresos]. Con todas las métricas de [!UICONTROL conversión] puede usar una asignación distinta.

* Este informe puede utilizar varios segmentos muy avanzados.

Si este informe no está disponible en la ubicación especificada, consulte a su administrador. Es posible que hayan cambiado el nombre predeterminado o la estructura de menús para adaptarlos a las necesidades específicas de su organización.
