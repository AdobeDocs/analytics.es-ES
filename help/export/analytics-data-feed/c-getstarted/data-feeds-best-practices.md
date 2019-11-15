---
description: 'A continuación se indican algunas de las prácticas recomendadas para el procesamiento y la entrega de una fuente de datos. Recomendaciones '
keywords: Data Feed;best practices;traffic spike;hourly;ftp
solution: Analytics
title: Prácticas recomendadas e información general
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Prácticas recomendadas e información general

A continuación se indican algunas de las prácticas recomendadas para el procesamiento y la entrega de una fuente de datos. Recomendaciones:

* Las fuentes de datos deberían entregarse en un plazo de 12 horas tras finalizar un periodo determinado un 95 % de las veces.

   Por ejemplo, si tiene una fuente por hora, la solicitud de fuente de datos correspondiente al periodo entre las 3 a. m. y las 4 a. m. debería entregarse a las 4 p. m. un 95 % de las veces. Las fuentes de datos para grupos de informes con un volumen de tráfico alto pueden tardar más en procesarse y entregarse, especialmente si se configuran por día en lugar de por hora.
* Asegúrese de que [comunica cualquier pico de tráfico anticipado](https://marketing.adobe.com/resources/help/en_US/reference/t_traffic_schedule_spike.html) con antelación. Cualquier incremento de la latencia tiene un impacto directo en la rapidez con la que puede iniciarse el proceso de fuente de datos.
* Asegúrese de que tiene suficiente espacio en su sitio de FTP. Límpielo de forma regular para que no se quede sin espacio en disco de forma involuntaria.
* Si cambia las credenciales de FTP, asegúrese de que las credenciales en el sistema de fuente de datos de Adobe están actualizadas.
* Utilice la entrega por horas siempre que sea posible. Hace que los archivos sean más pequeños y más rápidos de producir/transmitir.
* Considere la posibilidad de utilizar la entrega de "varios archivos" (normalmente se realiza con fuentes diarias grandes). La entrega de varios archivos rompe el archivo único y monolítico y lo convierte en archivos más pequeños que entrega al mismo tiempo. Además, los archivos más pequeños hacen que crear, comprimir/descomprimir y transmitir datos sea más rápido.
* Si utiliza SFTP como método de entrega, no lea ni elimine archivos con el sufijo ".part". El sufijo ".part" indica que el archivo se ha transferido parcialmente, no se ha completado. Una vez transferido el archivo, se cambiará su nombre sin el sufijo ".part".
* Cree sus procesos de ETL asumiendo que, ocasionalmente, el archivo podría transferirse más de una vez. De lo contrario, puede que los datos acaben duplicados.
