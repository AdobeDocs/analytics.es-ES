---
description: Adobe requiere un aviso previo para las nuevas configuraciones de cuenta, los picos de tráfico y los aumentos de tráfico. El hardware debe asignarse por adelantado para minimizar la latencia y los posibles impactos adversos en el sistema en general.
title: Tiempo de espera necesario para aumentos de tráfico
feature: Report Suite Settings
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
TQID: 'https://experienceleague.adobe.com/NJpOBQXD9CulN-UjbKnQiPzPWusWzLEo0RgvBioJe3I'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
source-git-commit: 50f9ff18816ad88f231762b8b37c1ab9e1787b6f
workflow-type: tm+mt
source-wordcount: 328
ht-degree: 100%

---

# Tiempo de espera necesario para aumentos de tráfico

Adobe requiere un aviso previo para las nuevas configuraciones de cuenta, los picos de tráfico y los aumentos de tráfico. El hardware debe asignarse por adelantado para minimizar la latencia y los posibles impactos adversos en el sistema en general.

>[!IMPORTANT]
>
>Adobe no puede admitir solicitudes de cambio de tráfico de “marcador de posición”. A no ser que se especifique lo contrario, respete el tiempo de espera sugerido tanto como sea posible, incluido el hecho de no enviar una alerta demasiado pronto.

Siga estas directrices para determinar con qué anticipación debe enviar una alerta de tráfico:

## Tiempos de espera de la asignación de hardware


<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Tipo de cambio de tráfico </th>
   <th colname="col2" class="entry"> Tiempo de espera necesario </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Nueva configuración de cuenta </td>
   <td colname="col2"> <ul><li>3 días hábiles</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Pico de tráfico o incremento repentino de tráfico permanente de hasta un 25 % en volumen diario promedio comparado con los últimos 30 días</td>
   <td colname="col2"> <ul><li>Grupos de informes con menos de 100 millones de visitas al día: no se requiere notificación</li><li>Grupos de informes con más de 100 millones de visitas al día: 5 días hábiles</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Pico de tráfico o incremento repentino de tráfico permanente de más de un 25 % en volumen diario promedio comparado con los últimos 30 días</td>
   <td colname="col2"> <ul><li>5 días hábiles</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Eventos festivos de octubre a diciembre </td>
   <td colname="col2"> <ul><li>Un mes natural</li></ul> </td>
  </tr>
 </tbody>
</table>

Otras cuestiones para tener en cuenta:

* Si hay varios grupos de informes que se están poniendo en marcha o ampliando y que suman las cifras indicadas más arriba, el tiempo de espera se aplica como una suma del tráfico previsto para cada uno de ellos.
* Disponga de la siguiente información para enviar un cambio de tráfico:

   * ID del grupo de informes
   * Visitas estimadas por día
   * Fecha de entrada al modo de producción

* También son necesarias Alertas de cliente cuando el tráfico disminuye o un grupo de informes está obsoleto.

## Anulación de asignaciones de hardware por tráfico inexistente

Se anulará la asignación de hardware para nuevas cuentas, picos de tráfico e incrementos de tráfico si el tráfico proyectado en la alerta del cliente no se materializa dentro de las 4 semanas de la “Fecha de lanzamiento”. Si el tráfico aún está anticipado, se debe generar una nueva alerta de cliente como incremento de tráfico.
