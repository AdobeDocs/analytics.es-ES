---
title: Análisis entre dispositivos
description: Analytics de varios dispositivos cambia los datos de estar centrados en dispositivos a una persona mediante la vinculación de datos de dispositivos.
translation-type: tm+mt
source-git-commit: 40d8ecae1ac7e0a1df4a2df17f5104bee6ecf336

---


# Análisis entre dispositivos

> [!NOTE] La documentación de análisis cruzado está sujeta a cambios, ya que la función se desarrolla aún más. Vuelva a comprobar periódicamente las actualizaciones.

Cross-Device Analytics es una función que transforma Analytics desde una vista centrada en los dispositivos a una vista centrada en persona. Esta función utiliza el Gráfico del servicio de identidad de Adobe Experience Platform o Gráfico privado para identificar qué dispositivos pertenecen a individuos y los unen. Como resultado, los analistas pueden comprender el comportamiento de los usuarios que cruzan los exploradores, los dispositivos o las aplicaciones. Con CDA puede dar respuesta a preguntas como:

* ¿Cuántas personas están interactuando con mi marca? ¿Cuántos y qué tipos de dispositivos utilizan? ¿Cómo se superponen?
* ¿Con qué frecuencia comienzan una tarea en un dispositivo móvil y luego se trasladan a un ordenador de escritorio para completarla? ¿Los clics de campaña que llegan a un dispositivo llevan a la conversión en otro dispositivo diferente?
* ¿Cómo cambia mi comprensión de la eficacia de la campaña si tengo en cuenta los recorridos entre dispositivos? ¿Cómo cambia mi análisis de embudo?
* ¿Cuáles son las rutas más comunes que los usuarios realizan de un dispositivo a otro? ¿En qué punto abandonan? ¿Dónde tienen éxito?
* ¿En qué se diferencia el comportamiento de los usuarios con varios dispositivos de los usuarios con un único dispositivo?

Cuando se vinculan dispositivos, la persistencia de la variable se transfiere entre dispositivos. Por ejemplo, un usuario visita primero su sitio a través de una publicidad en su equipo de escritorio. Ese usuario encuentra su aplicación móvil, la instala y finalmente realiza una compra en su dispositivo móvil. Con Analytics entre dispositivos, los ingresos pueden atribuirse a la publicidad que hicieron clic en su equipo de escritorio.

Consulte [IQ de viaje: Página de análisis entre dispositivos](http://adobe.ly/aacda) para obtener más información sobre las funciones y características de análisis cruzado de dispositivos.

## Requisitos previos

Desde septiembre de 2019, Device Analytics requiere lo siguiente. Trabaje con equipos dentro de su organización y con su administrador de cuentas de Adobe para asegurarse de que cumple todos los siguientes.

> [!IMPORTANT] Si no se cumplen todos los requisitos previos, no se puede habilitar el análisis cruzado de dispositivos ni los resultados bajos al registrar datos.

* Los datos de su organización deben residir dentro del centro de datos Noroeste del Pacífico de Adobe. Se ha planificado la compatibilidad con centros de datos en otras regiones del mundo.
* Póngase en contacto con el administrador de cuentas de su organización para establecer estos puntos clave:
   * Se debe firmar un contrato con Adobe que incluya Adobe Analytics Ultimate.
   * Su organización debe utilizar el Gráfico o Gráfico privado de la Plataforma de identidad de Adobe Experience Platform. Consulte la página [principal](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) en la guía del usuario de Device Co-op.
   * Su organización debe aceptar que Adobe procese y almacene datos de Analytics en servidores de Microsoft Azure. Adobe utiliza Azure para almacenar datos de gráficos de dispositivos y realizar la vinculación de dispositivos. Por lo tanto, los datos de Adobe Analytics se pasan entre el centro de procesamiento de datos de Adobe y la presencia de Adobe en Microsoft Azure.
* Analytics de varios dispositivos se habilita en cada grupo de informes. El grupo de informes requiere lo siguiente:
   * En este momento, un grupo de informes no puede tener más de 100 millones de visitas al día. Este umbral aumentará en los próximos meses.
   * Grupo de informes "entre dispositivos", lo que significa que todos los datos de los dispositivos deben enviarse al mismo grupo de informes. Algunas organizaciones hacen referencia a esto como un grupo de informes "global", aunque CDA no tiene por qué ser global desde una perspectiva geográfica. Analytics no funciona entre los grupos de informes.
* Su implementación debe cumplir los requisitos siguientes:
   * Debe implementarse la última versión del servicio Experience Cloud ID. Consulte la página [principal](https://docs.adobe.com/content/help/en/id-service/using/home.html) en la guía del usuario del servicio de identidad de Experience Cloud. Es probable que la mayoría de implementaciones que utilicen Launch Platform Platform ya tengan implementado ECID.
   * Llame a `setCustomerIDs` la función cada vez que se pueda identificar a un individuo, como cuando un usuario inicia sesión o abre un correo electrónico. Este requisito se aplica a todas las plataformas, incluidas las aplicaciones móviles, si se utilizan. Consulte [setcustomerids](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) en la guía del usuario del servicio de identidad de Experience Cloud.

## Limitaciones

Analytics entre dispositivos es una función innovadora y robusta, pero tiene limitaciones en la forma en que se puede utilizar.

* CDA solo está disponible a través de Analysis Workspace.
* La vinculación no puede ocurrir en organizaciones IMS. Asegúrese de que no utiliza varias organizaciones IMS en su implementación.
* La vinculación no puede ocurrir en grupos de informes como se describe en Prerrequisitos anteriores.
* CDA no es compatible actualmente con Atributos del cliente. Los atributos del cliente no se pueden utilizar para crear un grupo de informes virtuales CDA, dentro de segmentos entre dispositivos o para crear informes dentro de un proyecto de espacio de trabajo de análisis basado en un grupo de informes virtuales CDA.
* CDA requiere Co-op Gráfico o Gráfico privado. No se admiten gráficos de dispositivos de terceros.
* No se admiten los ID de Analytics heredados. Solo se unen los visitantes con ID de Experience Cloud.
* El Servicio de atención al cliente aún no admite completamente esta función. El [foro de análisis entre dispositivos](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) se puede utilizar para admitir esta función, que incluye la participación activa y directa de los responsables de productos de Adobe.
* Analytics utiliza un grupo de informes virtuales y un procesamiento de tiempo de informes, que tienen sus propias limitaciones. Consulte [Grupos de informes virtuales](../vrs/vrs-about.md) e [Procesamiento de intervalo de tiempo para](../vrs/vrs-report-time-processing.md) obtener más información sobre estas limitaciones.
* Los nuevos dispositivos que visiten el sitio pueden llevar hasta dos semanas para ser procesados por el gráfico de Co-op o el gráfico privado. El nivel de identificación en CDA para las dos semanas más recientes suele ser menor que en los intervalos de fechas anteriores a dos semanas. Adobe tiene previsto mejorar el servicio de identidad de Adobe Experience Platform para unir nuevos dispositivos en tiempo real.
* Los datos históricos de los cambios del grupo de informes virtuales se basan en el reconocimiento y la vinculación de dispositivos de Adobe. Los datos del grupo de informes de origen no cambian.

Una vez que su organización cumpla todos los requisitos y comprenda las limitaciones, puede empezar [a configurar el análisis cruzado de dispositivos](cda-setup.md).
