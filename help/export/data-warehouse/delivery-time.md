---
title: Solucionar problemas de tiempos de envío de solicitudes Data Warehouse
description: Determinar posibles problemas con una solicitud del Data Warehouse que puede prolongar las horas de envío.
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
TQID: 'https://experienceleague.adobe.com/oWkM-wTuJ75sR6AzkjD8WfY9DYLUdtToSGyu8hJIXVk'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: f47edbe0-f963-46ff-a667-71011396f5f3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 358
ht-degree: 59%

---

# Resolución de problemas de las horas de envío de la solicitud del Data Warehouse

Una solicitud del Data Warehouse determinada puede tardar entre menos de una hora a varios días o más. Es difícil estimar la cantidad exacta de tiempo que se tarda en procesar una solicitud, debido a los siguientes factores:

* Intervalo de fecha de la solicitud
* Cantidad de tráfico que recibió su grupo de informes durante el período de tiempo solicitado
* El número de reglas dentro de un segmento y qué variables dentro de un segmento se utilizaron
* Cantidad de datos incluidos en el segmento
* El número de desgloses utilizados y el número de valores únicos dentro de cada desglose
* Número de métricas utilizadas
* Número de solicitudes simultáneas que se procesan
* Reglas VISTA, si están configuradas para aplicarse a solicitudes del Data Warehouse

## Modificar solicitudes para acelerar el envío

Si las solicitudes de Data Warehouse tardan bastante tiempo, considere la posibilidad de modificar las solicitudes. Modificar una solicitud es la única manera de acelerar la entrega de una solicitud de Data Warehouse.

Para acelerar la entrega de una solicitud de Data Warehouse, puede modificarla de cualquiera de las siguientes maneras:

* **Utilice un segmento que contenga una muestra de datos más pequeña**: Cuanto menor sea la cantidad de datos con los que funciona una solicitud, más rápido devolverá un informe.
* **Ejecutar solicitudes en incrementos de 14 días o menos**: Las solicitudes más pequeñas se procesan más rápido que las solicitudes grandes.
* **Usar menos desgloses:** Muchos desgloses en una solicitud aumentan exponencialmente el tiempo que se tarda en procesarla.

## Utilizar un método alternativo

Si necesita estos tipos de informes de forma más oportuna, considere las siguientes alternativas:

* **Analysis Workspace**: Aunque no hay elementos de dimensión ilimitados disponibles, incluye casi todos los demás casos de uso que ofrece el Data Warehouse.
* **Fuente de datos**: Toma todos los datos sin procesar de un grupo de informes diariamente y los envía a un destino de nube. A continuación, puede importar los datos en su propia base de datos y ejecutar consultas para obtener los datos que necesite.
* **Solución de servicios de ingeniería personalizados**: Los Servicios de ingeniería de Adobe pueden proporcionar una solución personalizada para su organización a un coste adicional. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información.
