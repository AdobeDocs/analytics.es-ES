---
title: Análisis entre dispositivos
description: Cambie los datos de centrados en el dispositivo a centrados en la persona mediante la vinculación de los datos del dispositivo.
translation-type: tm+mt
source-git-commit: a46b68c7e4ea82b31ed400bf3e6180a7358bb3b5
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 95%

---


# Análisis entre dispositivos

Análisis entre dispositivos es una función que transforma Analytics de una vista centrada en el dispositivo a una vista centrada en la persona. Como resultado, los analistas pueden comprender el comportamiento del usuario que cruza navegadores, dispositivos o aplicaciones. Adobe admite dos flujos de trabajo generales para vincular datos de dispositivos:

* [**Vinculación basada en el campo**](field-based-stitching.md): Permite elegir una variable de Analytics como base para la vinculación entre dispositivos en un grupo de informes virtuales. Utiliza la coincidencia determinística para vincular dispositivos. Adobe recomienda utilizar la vinculación basada en el campo para los casos de uso de coincidencia más determinísticos.
* [**Gráfico del dispositivo**](device-graph.md): CDA se comunica con un gráfico del dispositivo para vincular dispositivos. El gráfico de cooperación utiliza coincidencia determinística y probabilística.

Con CDA, puede dar respuesta a preguntas como:

* ¿Cuántas personas interactúan con mi marca? ¿Cuántos y qué tipos de dispositivos utilizan? ¿Cómo se superponen?
* ¿Con qué frecuencia comienzan una tarea en un dispositivo móvil y luego se trasladan a un ordenador de escritorio para completarla? ¿Los clics de campaña que llegan a un dispositivo llevan a la conversión en otro dispositivo diferente?
* ¿Cómo cambia mi comprensión de la eficacia de la campaña si tengo en cuenta los recorridos entre dispositivos? ¿Cómo cambia mi análisis de embudo?
* ¿Cuáles son las rutas más comunes que los usuarios realizan de un dispositivo a otro? ¿En qué punto abandonan? ¿Dónde tienen éxito?
* ¿En qué se diferencia el comportamiento de los usuarios con varios dispositivos de los usuarios con un único dispositivo?

Cuando se vinculan dispositivos, la persistencia de las variables se transfiere entre dispositivos. Por ejemplo: un usuario visita su sitio por primera vez a través de un anuncio en su equipo de escritorio. Ese usuario encuentra su aplicación móvil, la instala y, finalmente, realiza una compra en su dispositivo móvil. Con Análisis entre dispositivos, puede atribuir los ingresos en el dispositivo móvil a la publicidad en la que hicieron clic en su equipo de escritorio.

Con un espíritu de colaboración y transparencia, queremos que nuestros clientes sean conscientes de nuestro uso de Microsoft Azure en asociación con Análisis entre dispositivos. Adobe utiliza Azure para almacenar datos de gráficos de dispositivos y vincular dispositivos. De este modo, los datos de Adobe Analytics se pasan de un lado a otro entre el centro de procesamiento de datos de Adobe y las instancias proporcionadas por Adobe en Microsoft Azure.

Consulte [Journey IQ: Página de demostración de análisis entre dispositivos](http://adobe.ly/aacda) para obtener más información sobre las funciones y características de Análisis entre dispositivos.

## Requisitos previos

El uso de CDA requiere lo siguiente. Los métodos de [vinculación basada en el campo](field-based-stitching.md) y [gráficos del dispositivo](device-graph.md) también tienen sus propios requisitos previos específicos.

* Se debe firmar un contrato con Adobe que incluya Adobe Analytics Ultimate.
* El análisis entre dispositivos se habilita por grupo de informes. Adobe recomienda un grupo de informes que contenga datos entre dispositivos, es decir, datos de varios tipos de dispositivos (web, aplicación, etc.). Algunas organizaciones se refieren a este concepto como un grupo de informes “global”, aunque el CDA no tiene que ser estrictamente global desde una perspectiva geográfica.

## Limitaciones

El análisis entre dispositivos es una característica innovadora y sólida, pero tiene limitaciones en la forma de utilizarlo. Los métodos de [vinculación basada en el campo](field-based-stitching.md) y [gráficos del dispositivo](device-graph.md) también tienen sus propias limitaciones específicas.

* CDA solo está disponible a través de Analysis Workspace.
* El análisis entre dispositivos no funciona en todos los grupos de informes ni combina datos de varios grupos de informes.
* Los grupos de informes de Adobe Analytics no pueden asignarse a más de una organización de IMS. Dado que CDA vincula dispositivos dentro de un grupo de informes determinado, CDA no se puede usar para unir datos en varias organizaciones IMS.
* Actualmente, CDA no es compatible con Atributos del cliente. Estas dos funciones pueden coincidir en grupos de informes virtuales independientes que hacen referencia al mismo grupo de informes de origen.
* Análisis entre dispositivos utiliza un grupo de informes virtuales y un procesamiento de tiempo de informes, que tienen sus propias limitaciones. Consulte [Grupos de informes virtuales](../vrs/vrs-about.md) y [Procesamiento de tiempo de los informes](../vrs/vrs-report-time-processing.md) para saber más sobre estas limitaciones.
* La API 1.4 no es compatible. Los conectores de Power BI y Report Builder dependen de la API 1.4 y, por lo tanto, no son compatibles con CDA.
* Los datos históricos del grupo de informes virtuales cambian según el reconocimiento y la vinculación de dispositivos de Adobe. Los datos del grupo de informes de origen no cambian.
