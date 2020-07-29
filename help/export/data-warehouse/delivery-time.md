---
title: Resolución de problemas de los tiempos de envío de la solicitud de Data warehouse
description: Determinar posibles problemas con una solicitud de Data warehouse que puede prolongar los tiempos de envío.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---


# Resolución de problemas de los tiempos de envío de la solicitud de Data warehouse

Una solicitud de Data warehouse determinada puede tardar entre menos de una hora y varios días o más. Es difícil estimar la cantidad exacta de tiempo que se tarda en procesar una solicitud, debido a los siguientes factores:

* Intervalo de fechas de la solicitud
* Cantidad de tráfico que recibió su grupo de informes durante el período de tiempo solicitado
* El número de reglas dentro de un segmento y qué variables dentro de un segmento utilizaron
* Cantidad de datos incluidos en el segmento
* El número de desgloses utilizados y el número de valores únicos dentro de cada desglose
* Número de métricas utilizadas
* Número de solicitudes simultáneas que se procesan
* Reglas de VISTA, si están configuradas para aplicarse a solicitudes de DataWarehouse

Si observa que las solicitudes de data warehouse tardan mucho tiempo, considere la posibilidad de modificar las solicitudes para adaptarse a lo siguiente:

* **Utilice un segmento que contenga una muestra de datos** más pequeña: Cuanto menor sea la cantidad de datos con los que funciona una solicitud, más rápido devolverá un informe.
* **Ejecutar solicitudes en incrementos de 14 días o menos**: Las solicitudes más pequeñas se procesan más rápido que las solicitudes grandes.
* **Usar menos desgloses:** Muchos desgloses en una solicitud de Data warehouse aumentan exponencialmente el tiempo que se tarda en procesar.

>[!IMPORTANT]
>
> *No hay forma de acelerar el envío de una solicitud de Data warehouse.*

Si necesita estos tipos de informes de manera más oportuna, considere las siguientes alternativas:

* **Analysis Workspace**: Aunque no hay elementos de dimensión ilimitados disponibles, incluye casi todos los demás casos de uso que ofrece la Data warehouse.
* **Fuente** de datos: Toma todos los datos sin procesar de un grupo de informes diariamente y los envía a un sitio FTP. A continuación, puede importar estos datos en su propia base de datos y ejecutar consultas para obtener los datos que busca.
* **Solución** de servicios de ingeniería personalizados: Los Servicios de ingeniería de Adobe pueden proporcionar una solución personalizada para su organización a un costo adicional. Póngase en contacto con el administrador de cuentas de su organización para obtener más información.
