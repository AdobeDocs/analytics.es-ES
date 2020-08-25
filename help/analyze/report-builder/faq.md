---
title: Preguntas más frecuentes sobre Report Builder
description: Preguntas más frecuentes para Report Builder.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---


# Preguntas más frecuentes sobre Report Builder

Preguntas más frecuentes sobre Report Builder.

## ¿Puedo usar la `TODAY()` función o `DATERANGE()` en libros?

La [`TODAY()` función](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) en Excel devuelve el día actual. La [`DATEVALUE()` función](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) convierte una cadena de fecha en un valor de serie. Aunque resulta útil para muchas funciones de Excel, Adobe recomienda enfáticamente no utilizar estas funciones como parte de solicitudes programadas de Report Builder. El Servicio de atención al cliente de Adobe no admite solicitudes de resolución de problemas con cualquiera de estas funciones.

Los informes programados se procesan en servidores que probablemente no compartan zonas horarias como el grupo de informes. El `TODAY()` usuario espera y los `TODAY()` usos del servidor de procesamiento suelen ser diferentes. Además, la fecha utilizada se basa en el momento de procesar inicios. Si se ejecutan muchos informes simultáneamente, la fecha puede cambiar entre el momento en que se solicita y el momento en que se inicio el procesamiento debido a retrasos. Este problema está presente si la hora programada está cerca de la medianoche.

Los informes programados también se procesan en servidores que probablemente no compartan la sintaxis de fecha. Por ejemplo, `7/1/YYYY` puede referirse al 1 de julio o al 7 de enero, según el país o la región. El uso de la `DATEVALUE()` función en esta fecha daría como resultado diferentes valores de serie en función del equipo que la ejecute.

Como alternativa al uso de estas funciones de Excel, Adobe recomienda utilizar intervalos de fechas dentro de las solicitudes de Report Builder. En la primera página del asistente para solicitudes, seleccione Fechas **** preestablecidas en el menú desplegable y, en Fechas más utilizadas, seleccione **[!UICONTROL Hoy]** u otro intervalo de fechas deseado. Esta configuración toma el tiempo del grupo de informes en el momento en que se ejecutó y no el tiempo del servidor que procesa la solicitud.

## ¿Qué tan grande y compleja puedo hacer mis libros?

Report Builder admite libros hasta los límites siguientes:

* **1000 solicitudes**: Un libro puede contener hasta 1000 solicitudes de datos en un solo libro. Si tiene informes o proyectos que requieren más de 1000 solicitudes, Adobe recomienda separarlos en varios libros.
* **20.000 solicitudes por hora por compañía**: Report Builder utiliza la API de sistema de informes de Analytics para recuperar datos. Cada solicitud individual utiliza una llamada de API cada vez que se crea o actualiza. Si su organización acumula más de 20.000 llamadas de API en una hora determinada, debe esperar hasta la hora siguiente para recuperar los datos de nuevo.
* **Tiempo** de procesamiento de 4 horas: Los informes programados agotan el tiempo de espera después de procesar las últimas 4 horas. Si el libro contiene muchas solicitudes complejas que utilizan conjuntos de datos grandes, el informe programado puede fallar.
