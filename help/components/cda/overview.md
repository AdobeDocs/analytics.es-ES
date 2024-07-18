---
title: Análisis entre dispositivos
description: Cambie los datos de centrados en el dispositivo a centrados en la persona mediante la vinculación de los datos del dispositivo.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
feature: CDA
role: Admin
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 90%

---

# Análisis entre dispositivos

Análisis entre dispositivos (CDA) es una función que transforma Analytics de una vista centrada en el dispositivo a una vista centrada en la persona. Como resultado, los analistas pueden comprender el comportamiento del usuario que cruza navegadores, dispositivos o aplicaciones. Adobe admite dos flujos de trabajo generales para vincular datos de dispositivos:

* [**Vinculación basada en el campo**](field-based-stitching.md): se recomienda la opción de vinculación porque solo utiliza la coincidencia determinística para vincular dispositivos.
Permite elegir una variable de Analytics como base para la vinculación entre dispositivos en un grupo de informes virtuales.

* [**Gráfico del dispositivo**](device-graph.md): CDA se comunica con un gráfico privado para vincular dispositivos.

Con CDA, puede dar respuesta a preguntas como:

* ¿Cuántas personas interactúan con mi marca? ¿Cuántos y qué tipos de dispositivos utilizan? ¿Cómo se superponen?
* ¿Con qué frecuencia comienzan una tarea en un dispositivo móvil y luego se trasladan a un ordenador de escritorio para completarla? ¿Los clics de campaña que llegan a un dispositivo llevan a la conversión en otro dispositivo diferente?
* ¿Cómo cambia mi comprensión de la eficacia de la campaña si tengo en cuenta los recorridos entre dispositivos? ¿Cómo cambia mi análisis de embudo?
* ¿Cuáles son las rutas más comunes que los usuarios realizan de un dispositivo a otro? ¿En qué punto abandonan? ¿Dónde tienen éxito?
* ¿En qué se diferencia el comportamiento de los usuarios con varios dispositivos de los usuarios con un único dispositivo?

Cuando se vinculan dispositivos, la persistencia de las variables se transfiere entre dispositivos. Por ejemplo: un usuario visita su sitio por primera vez a través de un anuncio en su equipo de escritorio. Ese usuario encuentra su aplicación móvil, la instala y, finalmente, realiza una compra en su dispositivo móvil. Con análisis entre dispositivos, puede atribuir ingresos según el dispositivo móvil al anuncio en el que hicieron clic en el equipo de escritorio.

Con un espíritu de colaboración y transparencia, queremos que nuestros clientes sean conscientes de nuestro uso de Microsoft Azure en asociación con Análisis entre dispositivos. Adobe utiliza Azure para almacenar datos de gráficos de dispositivos y vincular dispositivos. De este modo, los datos de Adobe Analytics se pasan de un lado a otro entre el centro de procesamiento de datos de Adobe y las instancias proporcionadas por Adobe en Microsoft Azure.

Consulte [Journey IQ: Página de demostración de análisis entre dispositivos](https://adobe.ly/aacda) para obtener más información sobre las funciones y características de Análisis entre dispositivos.

## Requisitos previos

El uso de CDA requiere lo siguiente. Los métodos de [vinculación basada en el campo](field-based-stitching.md) y [gráficos del dispositivo](device-graph.md) también tienen sus propios requisitos previos específicos.

* Se debe firmar un contrato con Adobe que incluya Adobe Analytics Ultimate.
* Su organización elige en qué grupos de informes habilitar CDA. Adobe recomienda grupos de informes que contienen datos entre dispositivos, es decir, datos de varios tipos de dispositivos, exploradores o aplicaciones. Algunas organizaciones se refieren a este concepto como un grupo de informes “global”, aunque el CDA no tiene que ser estrictamente global desde una perspectiva geográfica.

## Limitaciones

El análisis entre dispositivos es una característica innovadora y sólida, pero tiene limitaciones en la forma de utilizarlo. Los métodos de [vinculación basada en el campo](field-based-stitching.md) y [gráficos del dispositivo](device-graph.md) también tienen sus propias limitaciones específicas.

* CDA solo está disponible a través de Analysis Workspace.
* El análisis entre dispositivos no funciona en todos los grupos de informes ni combina datos de varios grupos de informes.
* Los grupos de informes de Adobe Analytics no pueden asignarse a más de un ID de organización. Dado que el CDA vincula dispositivos dentro de un grupo de informes determinado, el CDA no se puede usar para unir datos en varios ID de organización.
* CDA utiliza una compleja canalización de procesamiento, con varios componentes dependientes. Esto se ejecuta en paralelo con el flujo de trabajo base de creación de informes de Analytics. Por lo tanto, se espera una discordancia de datos de aproximadamente el 1 % para el número total de visitas entre el grupo de informes original y el grupo de informes virtuales de CDA.
* Análisis entre dispositivos utiliza un grupo de informes virtuales y un procesamiento de tiempo de informes, que tienen sus propias limitaciones. Por ejemplo, actualmente no admiten variables de Canales de marketing. Consulte [Grupos de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=es) y [Procesamiento de tiempo de los informes](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=es#report-time-processing-limitations) para saber más sobre estas limitaciones.
* Private Graph aprovecha las mismas sincronizaciones de ID que las utilizadas por la funcionalidad [Atributos del cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=es#customer-attributes) ubicada en Experience Cloud y Adobe Analytics. Sin embargo, los grupos de informes virtuales de CDA (basados en gráficos privados o en la vinculación basada en el campo) no son compatibles con el resto de la funcionalidad Atributos del cliente. Es decir, las dimensiones basadas en atributos del cliente no están disponibles para su uso con los grupos de informes virtuales de CDA.
* En la actualidad, CDA no es compatible con A4T.
* La API 1.4 no es compatible. Los conectores de Power BI y Report Builder dependen de la API 1.4 y, por lo tanto, no son compatibles con CDA.
* La monitorización activa del proceso de vinculación de CDA por Adobe se limita solo a los grupos de informes de producción.
* Actualmente, CDA no es compatible con la [API de reparación de datos](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/data-repair.md) de Adobe Analytics.
* Los datos históricos del grupo de informes virtuales cambian según el reconocimiento y la vinculación de dispositivos de Adobe. Los datos del grupo de informes de origen no cambian.
* Los datos conectados siguen una latencia de 8 a 12 horas.
* Los datos del historial de asignación de un dispositivo determinado se almacenan durante un año.
* Si un dispositivo alcanza un número muy alto de entradas del historial de asignación en un año, el historial de asignación se trunca. El límite exacto depende de la opción de vinculación utilizada.
