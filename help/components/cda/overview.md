---
title: Análisis entre dispositivos
description: Aprenda a cambiar los datos de centrados en el dispositivo a centrados en la persona mediante la vinculación de los datos del dispositivo.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
feature: CDA
role: Admin
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 59%

---

# Análisis entre dispositivos

{{available-existing-customers}}

Análisis entre dispositivos (CDA) es una función que transforma Analytics de una vista centrada en el dispositivo a una vista centrada en la persona. Como resultado, los analistas pueden comprender el comportamiento del usuario que cruza navegadores, dispositivos o aplicaciones. Adobe admite dos flujos de trabajo generales para vincular datos de dispositivos:

* [**Vinculación basada en el campo**](field-based-stitching.md): se recomienda la opción de vinculación porque solo utiliza la coincidencia determinística para vincular dispositivos.
La vinculación basada en el campo permite elegir una variable de Analytics como base para la vinculación entre dispositivos en un grupo de informes virtuales.

* [**Gráfico del dispositivo**](device-graph.md): el análisis entre dispositivos se comunica con un gráfico privado para unir dispositivos.

Con CDA, puede dar respuesta a preguntas como:

* ¿Cuántas personas interactúan con mi marca? ¿Cuántos y qué tipos de dispositivos utilizan? ¿Cómo se superponen?
* ¿Con qué frecuencia comienzan una tarea en un dispositivo móvil y luego se trasladan a un ordenador de escritorio para completarla? ¿Los clics de campaña que llegan a un dispositivo llevan a la conversión en otro dispositivo diferente?
* ¿Cómo cambia mi comprensión de la eficacia de la campaña si tengo en cuenta los recorridos entre dispositivos? ¿Cómo cambia mi análisis de embudo?
* ¿Cuáles son las rutas más comunes que los usuarios realizan de un dispositivo a otro? ¿En qué punto abandonan? ¿Dónde tienen éxito?
* ¿En qué se diferencia el comportamiento de los usuarios con varios dispositivos de los usuarios con un único dispositivo?

Cuando se vinculan dispositivos, la persistencia de las variables se transfiere entre dispositivos. Por ejemplo: un usuario visita su sitio por primera vez a través de un anuncio en su equipo de escritorio. Ese usuario encuentra su aplicación móvil, la instala y, finalmente, realiza una compra en su dispositivo móvil. Con análisis entre dispositivos, puede atribuir ingresos según el dispositivo móvil al anuncio en el que hicieron clic en el equipo de escritorio.

Microsoft Azure se utiliza para el análisis entre dispositivos. Adobe utiliza Azure para almacenar datos de gráficos de dispositivos y vincular dispositivos. De este modo, los datos de Adobe Analytics se pasan de un lado a otro entre el centro de procesamiento de datos de Adobe y las instancias proporcionadas por Adobe en Microsoft Azure.

Consulte la [página de demostración de análisis entre dispositivos](https://express.adobe.com/page/8ZpjsX6Lp5XTM/) para obtener más información acerca de las funcionalidades y características de Análisis entre dispositivos.

## Requisitos previos

El uso de análisis entre dispositivos requiere los métodos [vinculación basada en el campo](field-based-stitching.md) y [gráfico del dispositivo](device-graph.md), y ambos tienen sus propios requisitos previos específicos.

* Se debe firmar un contrato con Adobe que incluya Adobe Analytics Ultimate.
* Su organización elige en qué grupos de informes habilitar CDA. Adobe recomienda grupos de informes que contienen datos entre dispositivos, es decir, datos de varios tipos de dispositivos, exploradores o aplicaciones. Algunas organizaciones se refieren a este concepto como un grupo de informes &quot;global&quot;, aunque el análisis entre dispositivos no tiene que ser estrictamente global desde una perspectiva geográfica.

## Limitaciones

El análisis entre dispositivos es una característica innovadora y sólida, pero tiene limitaciones en la forma de utilizarlo. Los métodos de [vinculación basada en el campo](field-based-stitching.md) y [gráficos del dispositivo](device-graph.md) también tienen sus propias limitaciones específicas.

* Cross-Device Analytics solo está disponible a través de Analysis Workspace.
* El análisis entre dispositivos no funciona en todos los grupos de informes ni combina datos de varios grupos de informes.
* Los grupos de informes de Adobe Analytics no pueden asignarse a más de un ID de organización. Dado que el análisis entre dispositivos vincula dispositivos dentro de un grupo de informes determinado, el análisis entre dispositivos no se puede usar para unir datos en varios ID de organización.
* El análisis entre dispositivos utiliza una compleja canalización de procesamiento, con varios componentes dependientes. Esta canalización se ejecuta en paralelo con el flujo de trabajo base de informes de Analytics. Se espera una discordancia de datos de aproximadamente el 1 % para el número total de visitas entre el grupo de informes original y el grupo de informes virtuales de análisis entre dispositivos.
* Análisis entre dispositivos utiliza un grupo de informes virtuales y un procesamiento de tiempo de informes, que tienen sus propias limitaciones. Por ejemplo, actualmente no admiten variables de Canales de marketing. Consulte [Grupos de informes virtuales](/help/components/vrs/vrs-about.md) y [Procesamiento de tiempo de los informes](/help/components/vrs/vrs-report-time-processing.md) para saber más sobre estas limitaciones.
* Private Graph aprovecha las mismas sincronizaciones de ID que las sincronizaciones de ID utilizadas por la funcionalidad [Atributos del cliente](https://experienceleague.adobe.com/es/docs/core-services/interface/services/customer-attributes/attributes) ubicada en Experience Cloud y Adobe Analytics. Sin embargo, los grupos de informes virtuales de Cross-Device Analytics (basados en gráficos privados o en la vinculación basada en el campo) no son compatibles con el resto de la funcionalidad Atributos del cliente. Es decir, las dimensiones basadas en atributos del cliente no están disponibles para su uso en los grupos de informes virtuales de análisis entre dispositivos.
* Actualmente, Análisis entre dispositivos no es compatible con A4T.
* La API 1.4 no es compatible. Los conectores de Power BI y Report Builder dependen de la API 1.4 y, por lo tanto, no son compatibles con CDA.
* La monitorización activa del proceso de vinculación de análisis entre dispositivos por parte de Adobe se limita solo a los grupos de informes de producción.
* Actualmente, Análisis entre dispositivos no es compatible con la [API de reparación de datos](https://developer.adobe.com/analytics-apis/docs/2.0/) de Adobe Analytics
* Los datos históricos del grupo de informes virtuales cambian según el reconocimiento y la vinculación de dispositivos de Adobe. Los datos del grupo de informes de origen no cambian.
* Los datos conectados siguen una latencia de 8 a 12 horas.
* Los datos del historial de asignación de un dispositivo determinado se almacenan durante un año.
* Si un dispositivo alcanza un número muy alto de entradas del historial de asignación en un año, el historial de asignación se trunca. El límite exacto depende de la opción de vinculación utilizada.
