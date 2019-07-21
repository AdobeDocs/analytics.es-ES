---
description: 'A continuación se indican algunas de las prácticas recomendadas para el procesamiento y la entrega de una fuente de datos. Recomendaciones '
keywords: Fuente de datos; prácticas recomendadas; pico de tráfico; por hora; ftp
seo-description: 'A continuación se indican algunas de las prácticas recomendadas para el procesamiento y la entrega de una fuente de datos. Recomendaciones '
seo-title: Prácticas recomendadas e información general
solution: Analytics
title: Prácticas recomendadas e información general
uuid: f 2 d 6 c 13 a -5 d 4 e -4 fc 2-8 baa -28 c 69 f 0 cf 5 f 6
translation-type: tm+mt
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566

---


# Prácticas recomendadas e información general

A continuación se indican algunas de las prácticas recomendadas para el procesamiento y la entrega de una fuente de datos. Recomendaciones:

* Las fuentes de datos deberían entregarse en un plazo de 12 horas tras finalizar un periodo determinado un 95 % de las veces.

   Por ejemplo, si tiene una fuente por hora, la solicitud de fuente de datos correspondiente al periodo entre las 3 a. m. y las 4 a. m. debería entregarse a las 4 p. m. un 95 % de las veces. Las fuentes de datos para grupos de informes con un volumen de tráfico alto pueden tardar más en procesarse y entregarse, especialmente si se configuran por día en lugar de por hora.
* Asegúrese de que [comunica cualquier pico de tráfico anticipado](https://marketing.adobe.com/resources/help/en_US/reference/t_traffic_schedule_spike.html) con antelación. Cualquier incremento de la latencia tiene un impacto directo en la rapidez con la que puede iniciarse el proceso de fuente de datos.
* Asegúrese de que tiene suficiente espacio en su sitio de FTP. Límpielo regularmente para no quedarse sin espacio en el disco de forma inesperada.
* Si cambia las credenciales de FTP, asegúrese de que las credenciales en el sistema de fuente de datos de Adobe están actualizadas.
* Utilice la entrega por horas siempre que sea posible. Hace que los archivos sean más pequeños y más rápidos de producir/transmitir.
* Considere utilizar la entrega de "varios archivos" (normalmente se hace con fuentes grandes diarias). La entrega de varios archivos rompe el archivo único y monolítico y lo convierte en archivos más pequeños que entrega al mismo tiempo. Además, los archivos más pequeños hacen que crear, comprimir/descomprimir y transmitir datos sea más rápido.
* Si utiliza un sFTP como método de entrega, no lea ni elimine los archivos que contengan el sufijo “.part”. Este sufijo indica que solo se ha transferido una parte del archivo en lugar del archivo completo. Cuando el archivo se haya transferido, desaparecerá el sufijo “.part” de su nombre.
* Cree sus procesos de ETL asumiendo que, ocasionalmente, el archivo podría transferirse más de una vez. De lo contrario, puede que los datos acaben duplicados.
