---
title: Plantilla de CDA Workspace
description: Describe cada campo de la plantilla CDA de Analysis Workspace.
translation-type: tm+mt
source-git-commit: be842d1ca4080171dbec7fd8b5966d8861f79487
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Plantilla de CDA Workspace

Adobe ofrece una plantilla para ver datos de rendimiento vitales entre dispositivos.

1. Vaya a [experience.adobe.com](https://experiencecloud.adobe.com) e inicie sesión con sus credenciales de Adobe ID.
1. Haga clic en el icono de 9 cuadrículas en la parte superior y, a continuación, haga clic en Analytics.
1. Haga clic en [!UICONTROL Workspace] en la parte superior y, a continuación, en [!UICONTROL “Crear nuevo proyecto”].
1. Localice la plantilla &quot;Journey IQ: análisis entre dispositivos&quot; y, a continuación, haga clic en [!UICONTROL Crear].
1. Si se le solicita, cambie el grupo de informes a uno que admita CDA.

Se crea un proyecto de Analysis Workspace que contiene varios paneles. En la parte superior, se muestra una tabla de contenido e introducción, lo que permite el contexto del informe y la navegación hacia informes individuales. Haga clic en un vínculo dentro de la tabla de contenido o expanda el acordeón de un panel para ver dichos informes.

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **Nota especial para los miembros del Gráfico de cooperación**: muestra qué parte del grupo de informes contiene visitantes en regiones donde se admite el gráfico de cooperación y en regiones donde no se admite.
* **Identificación de los usuarios**: muestra la frecuencia con la que se identifican los visitantes del sitio mediante métodos basados en el análisis entre dispositivos.
* **Medición del tamaño de la audiencia**: muestra una comparación de &#39;Dispositivos únicos&#39; con &#39;Personas&#39;. La proporción de estos dos números se conoce como &#39;compresión entre dispositivos&#39;, una métrica calculada visible en este panel. Esta métrica de compresión depende de varios factores:
   * Uso del gráfico de colaboración o del gráfico privado: En términos generales, las organizaciones que utilizan la colaboración entre dispositivos tienden a ver mejores tasas de compresión que las organizaciones que utilizan el gráfico privado.
   * Velocidad de inicio de sesión: Cuantos más usuarios inicien sesión en el sitio, más podrá Adobe identificar y unir a los visitantes entre dispositivos. Los sitios con una tasa de inicio de sesión baja también tienen tasas de compresión bajas.
   * Cobertura del Experience Cloud ID: Solo se pueden vincular los visitantes con un ECID. Un porcentaje menor de visitantes que utilizan un ECID se correlaciona con tasas de compresión más bajas.
   * Uso de varios dispositivos: Si los visitantes del sitio no utilizan varios dispositivos, puede ver tasas de compresión más bajas.
   * Granularidad de informes: La compresión por día suele ser menor que la compresión por mes o año. Las posibilidades de que un individuo utilice varios dispositivos se reducen en un solo día en comparación con todo un mes. Segmentar, filtrar o utilizar dimensiones de desglose también puede mostrar una tasa de compresión más baja.
* **Segmentos basados en personas**: contiene una lista desplegable de segmentos que le permite ver datos específicos del dispositivo. Este panel promueve la experimentación con segmentos para ver cómo la inclusión o la exclusión de tipos de dispositivos afectan los informes.
* **Análisis del viaje entre dispositivos**: proporciona informes de flujo y visitas en el orden previsto en función del tipo de dispositivo.
* **Atribución entre dispositivos**: combine las características de Journey IQ y Attribution IQ.
* **Otros consejos y trucos**: temas útiles en torno a CDA que le permite aprovecharlo al máximo.
