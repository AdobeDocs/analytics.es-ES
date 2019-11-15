---
description: Cuando configura una fuente, algunos ajustes permiten definir la frecuencia con la que se procesan los trabajos.
keywords: Data Feed;job;settings;daily;hourly;Data Backfills for Hourly Data Feeds;backfill
solution: Analytics
title: Configuración de trabajos
uuid: e124b4f1-0168-4eaa-8657-19207b2f263f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Configuración de trabajos

Al configurar una fuente, algunos ajustes determinan la frecuencia con la que se procesan los trabajos.

Utilice los siguientes ajustes para configurar los tiempos de procesamiento de los trabajos. Estos ajustes se aplican en el nivel de fuente, no en el de trabajo.

<table id="table_2070F73212F245E98DADC6B5DFDB1C72"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Diaria </td> 
   <td colname="col2"> <p>Los datos de cada día se entregan en un único archivo comprimido con un tamaño de 2 GB como máximo. Si los datos sin comprimir del archivo sobrepasan ese tamaño, se crean archivos adicionales. Todos los archivos se entregan una vez todos los días. </p> <p>El nombre de cada archivo tiene el siguiente formato: </p> <p> <span class="filepath"> <span class="varname"> reportsuite</span>-<span class="varname"> date</span>.tar</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Por hora (predeterminado) </td> 
   <td colname="col2"> <p>Se entregan datos de cada hora en un solo archivo comprimido que contiene todos los datos recibidos durante esa hora. Se reciben 24 entregas diferentes cada día, y cada archivo se entrega después de procesar los datos de esa hora. </p> <p>El término "por hora" describe el intervalo de tiempo de los datos que se envían con cada exportación de datos individual y no el intervalo de tiempo en el que se produce la entrega. Las fuentes de datos por hora se procesan y se entregan de la mejor forma posible. </p> <p>En el caso de las fuentes de datos por hora, se espera que el 95 % del tiempo que la fuente se entregue dentro de las 12 horas posteriores al cierre del valor de los datos de esa hora. Las fuentes de datos de los grupos de informes con un volumen de tráfico elevado pueden tardar más en procesarse y entregarse. </p> <p>Recibir una fuente de datos por hora no es lo mismo que recibir fuentes diarias con varias entregas de archivos. Si se reciben fuentes de datos por hora, los datos de cada día se dividen en 24 archivos basados en los datos recopilados durante esa hora, y cada archivo se entrega en cuanto está disponible. Una fuente diaria que se entrega en varios archivos se entrega una vez al día después de procesar los datos del día anterior, y se divide en incrementos de 2 GB en función de la cantidad de datos recopilados. </p> <p>El nombre de cada archivo tiene el siguiente formato: </p> <p> <span class="filepath"> <span class="varname"> reportsuite</span>-<span class="varname"> date</span>-<span class="varname"> hour</span>.tar</span> </p> <p>Consulte <a href="/help/export/analytics-data-feed/c-df-contents/jobs-faq.md"  >Preguntas más frecuentes sobre trabajos</a> para obtener más información sobre los factores que pueden influir en las fuentes por hora. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rellenos de datos para fuentes de datos por hora </td> 
   <td colname="col2"> <p>Si solicita datos de fechas anteriores al configurar una fuentes de datos por hora, los datos para las fechas de hace más de 60 días podrían entregarse en un formato de día en vez de en formato de hora. </p> <p>En este caso, no recibirá 24 entregas separadas para estos días, sino que recibirá una entrega única con un tiempo de registro de medianoche que contiene todos los datos para ese día. Si está solicitando este tipo de relleno, asegúrese de que su ETL está configurado para procesar entregas diarias. </p> </td> 
  </tr> 
 </tbody> 
</table>

