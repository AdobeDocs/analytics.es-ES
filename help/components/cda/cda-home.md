---
title: Análisis entre dispositivos
description: El análisis entre dispositivos cambia los datos de estar centrados en el dispositivo a estar centrados en la persona, al unir los datos del dispositivo.
translation-type: ht
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Análisis entre dispositivos

> [!NOTE] La documentación de Análisis entre dispositivos está sujeta a cambios a medida que la función se desarrolla. Vuelva regularmente para ver las actualizaciones.

Análisis entre dispositivos es una función que transforma Analytics de una vista centrada en el dispositivo a una vista centrada en la persona. Esta función utiliza el gráfico colaborativo o el gráfico privado de Adobe Experience Platform Identity Service. para identificar qué dispositivos pertenecen a individuos y coordínelos. Como resultado, los analistas pueden comprender el comportamiento del usuario que cruza navegadores, dispositivos o aplicaciones. Con CDA puede dar respuesta a preguntas como:

* ¿Cuántas personas están interactuando con mi marca? ¿Cuántos y qué tipos de dispositivos utilizan? ¿Cómo se superponen?
* ¿Con qué frecuencia comienzan una tarea en un dispositivo móvil y luego se trasladan a un ordenador de escritorio para completarla? ¿Los clics de campaña que llegan a un dispositivo llevan a la conversión en otro dispositivo diferente?
* ¿Cómo cambia mi comprensión de la eficacia de la campaña si tengo en cuenta los recorridos entre dispositivos? ¿Cómo cambia mi análisis de embudo?
* ¿Cuáles son las rutas más comunes que los usuarios realizan de un dispositivo a otro? ¿En qué punto abandonan? ¿Dónde tienen éxito?
* ¿En qué se diferencia el comportamiento de los usuarios con varios dispositivos de los usuarios con un único dispositivo?

Cuando se vinculan dispositivos, la persistencia de las variables se transfiere entre dispositivos. Por ejemplo: un usuario visita su sitio por primera vez a través de un anuncio en su equipo de escritorio. Ese usuario encuentra su aplicación móvil, la instala y, finalmente, realiza una compra en su dispositivo móvil. Con Análisis entre dispositivos, los ingresos pueden atribuirse a la publicidad en la que hicieron clic en su equipo de escritorio.

Consulte [Journey IQ: Página de demostración de análisis entre dispositivos](http://adobe.ly/aacda) para obtener más información sobre las funciones y características de Análisis entre dispositivos.

## Requisitos previos

A partir de septiembre de 2019, Análisis entre dispositivos requiere lo siguiente. Trabaje con equipos de su organización y con el administrador de cuentas de Adobe para asegurarse de que cumple todos los requisitos siguientes.

> [!IMPORTANT] Si no se cumplen todos los requisitos previos, es posible que no se pueda habilitar el análisis entre dispositivos o que se obtengan resultados deficientes al vincular datos.

* Los datos de su organización deben residir en el centro de datos del Noroeste del Pacífico de Adobe. Está previsto prestar apoyo a los centros de datos de otras regiones del mundo.
* Contacte con el administrador de cuentas de su organización para establecer estos puntos clave:
   * Se debe firmar un contrato con Adobe que incluya Adobe Analytics Ultimate.
   * Su organización debe utilizar el gráfico colaborativo o el gráfico privado de Adobe Experience Platform Identity Service. Consulte la página [principal](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) en la guía del usuario de Device Co-op.
   * Su organización debe aceptar permitir que Adobe procese y almacene datos de Analytics en servidores de Microsoft Azure. Adobe utiliza Azure para almacenar datos de gráficos de dispositivos y realizar la vinculación de dispositivos. De este modo, los datos de Adobe Analytics se pasan de un lado a otro entre el centro de procesamiento de datos de Adobe y la presencia de Adobe en Microsoft Azure.
* El análisis entre dispositivos se habilita por grupo de informes. Los grupos de informes que se han habilitado para CDA requieren lo siguiente:
   * El grupo de informes no puede tener más de 100 millones de visitas al día. Este umbral aumentará en los próximos meses.
   * Adobe recomienda que un grupo de informes contenga datos entre dispositivos, es decir, datos de varios tipos de dispositivos (web, aplicación, etc.). Algunas organizaciones se refieren a este concepto como un grupo de informes “global”, aunque el CDA no tiene que ser estrictamente global desde una perspectiva geográfica. El análisis entre dispositivos no funciona en todos los grupos de informes ni combina datos de varios grupos de informes.
* Su implementación debe cumplir los siguientes requisitos:
   * Se debe implementar la versión más reciente del servicio Experience Cloud ID. Consulte la página [principal](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html) en la guía del usuario del servicio de Experience Cloud ID. Es probable que la mayoría de las implementaciones que utilizan Adobe Experience Platform Launch ya hayan implementado ECID.
   * Llame a la función `setCustomerIDs` cada vez que se pueda identificar a un individuo, como cuando un usuario inicia sesión o abre un correo electrónico. Este requisito se aplica a todas las plataformas, incluidas las aplicaciones móviles, si se utilizan. Consulte [setCustomerIDs](https://docs.adobe.com/content/help/es-ES/id-service/using/id-service-api/methods/setcustomerids.html) en la guía del usuario del servicio de Experience Cloud ID.

## Limitaciones

El análisis entre dispositivos es una característica innovadora y sólida, pero tiene limitaciones en la forma de utilizarlo.

* CDA solo está disponible a través de Analysis Workspace.
* La configuración no puede producirse en los grupos de informes como se describe en los requisitos previos anteriores.
* Los grupos de informes de Adobe Analytics no pueden asignarse a más de una organización de IMS. Dado que CDA vincula dispositivos dentro de un grupo de informes determinado, CDA no se puede usar para unir datos en varias organizaciones IMS.
* Actualmente, CDA no es compatible con Atributos del cliente. Atributos del cliente no se puede usar para crear un grupo de informes virtuales CDA, dentro de segmentos entre dispositivos o para generar informes dentro de un proyecto de Analysis Workspace basado en un grupo de informes virtuales CDA.
* CDA requiere gráficos colaborativos o privados. Los gráficos de dispositivos de terceros no son compatibles.
* Los ID de Analytics heredados no son compatibles. Solo se vinculan los visitantes con Experience Cloud ID.
* El Servicio de atención al cliente aún no admite esta función. El foro [Análisis entre dispositivos](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) se puede utilizar para ofrecer compatibilidad con esta función, que incluye la participación activa y directa de los responsables de productos de Adobe.
* Análisis entre dispositivos utiliza un grupo de informes virtuales y un procesamiento de tiempo de informes, que tienen sus propias limitaciones. Consulte [Grupos de informes virtuales](../vrs/vrs-about.md) y [Procesamiento de tiempo de los informes](../vrs/vrs-report-time-processing.md) para saber más sobre estas limitaciones.
* Los nuevos dispositivos que visiten el sitio pueden tardar hasta dos semanas en procesarse mediante el gráfico de colaboración o el gráfico privado. El nivel de vinculación en CDA para las dos últimas semanas es generalmente inferior al de los intervalos de fechas de más de dos semanas. Adobe planea mejorar el servicio de identidad de Adobe Experience Platform para conectar nuevos dispositivos en tiempo real en el futuro.
* Los datos históricos del grupo de informes virtuales cambian según el reconocimiento y la vinculación de dispositivos de Adobe. Los datos del grupo de informes de origen no cambian.

Una vez que su organización haya cumplido todos los requisitos y haya comprendido las limitaciones, puede empezar a [configurar análisis](cda-setup.md) cruzados de dispositivos.
