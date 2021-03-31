---
title: Preguntas frecuentes sobre Report Builder
description: Preguntas frecuentes para el Report Builder.
feature: Report Builder
role: Profesional empresarial, administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 1%

---


# Preguntas frecuentes sobre Report Builder

Preguntas frecuentes sobre el Report Builder.

## ¿Puedo utilizar la función `TODAY()` o `DATERANGE()` en libros?

La función [`TODAY()`](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) en Excel devuelve el día actual. La función [`DATEVALUE()`](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) convierte una cadena de fecha en un valor de serie. Aunque es útil para muchas funciones de Excel, Adobe recomienda encarecidamente no utilizar estas funciones como parte de solicitudes programadas de Report Builder. El Servicio de atención al cliente de Adobe no admite solicitudes de resolución de problemas que utilicen cualquiera de estas funciones.

Los informes programados se procesan en servidores que probablemente no compartan zonas horarias como el grupo de informes. El `TODAY()` que un usuario espera y el `TODAY()` que utiliza el servidor de procesamiento pueden ser a menudo diferentes. Además, la fecha utilizada se basa en el momento en que comienza el procesamiento. Si se ejecutan muchos informes simultáneamente, la fecha puede cambiar entre el momento en que se solicita y el momento en que comienza a procesarse debido a retrasos. Este problema está presente si la hora programada está cerca de la medianoche.

Los informes programados también se procesan en servidores que probablemente no comparten sintaxis de fecha. Por ejemplo, `7/1/YYYY` puede referirse al 1 de julio o al 7 de enero, según su país o región. El uso de la función `DATEVALUE()` en esta fecha resultaría en diferentes valores de serie según el equipo que lo ejecute.

Como alternativa al uso de estas funciones de Excel, Adobe recomienda encarecidamente el uso de intervalos de fechas dentro de las solicitudes del Report Builder. En la primera página del asistente para solicitudes, seleccione **[!UICONTROL Fechas preestablecidas]** en el menú desplegable y, en Fechas más utilizadas, seleccione **[!UICONTROL Hoy]** u otro intervalo de fechas deseado. Esta configuración toma el tiempo del grupo de informes en el momento en que se ejecutó y no el tiempo en que el servidor procesa la solicitud.

## ¿Qué tan grande y complejo puedo hacer mis libros de trabajo?

Report Builder admite libros hasta los límites siguientes:

* **1000 solicitudes**: Un libro puede contener hasta 1000 solicitudes de datos en un solo libro de trabajo. Si tiene informes o proyectos que requieren más de 1000 solicitudes, Adobe recomienda separarlos en varios libros.
* **20.000 solicitudes por hora por empresa**: Report Builder utiliza la API de informes de Analytics para recuperar datos. Cada solicitud individual utiliza una llamada de API cada vez que se crea o actualiza. Si su organización acumula más de 20 000 llamadas a la API en una hora determinada, debe esperar hasta la hora siguiente para recuperar datos de nuevo.
* **Tiempo** de procesamiento de 4 horas: Los informes programados agotan el tiempo de espera después de procesarse las últimas 4 horas. Si el libro contiene muchas solicitudes complejas que utilizan conjuntos de datos grandes, el informe programado puede fallar.
