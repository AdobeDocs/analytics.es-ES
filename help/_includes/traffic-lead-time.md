---
description: Adobe necesita que se informe por adelantado en caso de nuevas configuraciones de cuentas, picos de tráfico e incrementos de tráfico. El hardware debe asignarse por adelantado para minimizar la latencia y las posibles consecuencias adversas en el sistema general.
title: Tiempo de espera necesario para aumentos de tráfico
feature: Report Suite Settings
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 100%

---

# Tiempo de espera necesario para aumentos de tráfico

Adobe necesita que se informe por adelantado en caso de nuevas configuraciones de cuentas, picos de tráfico e incrementos de tráfico. El hardware debe asignarse por adelantado para minimizar la latencia y las posibles consecuencias adversas en el sistema general.

>[!IMPORTANT]
>
> Adobe no puede admitir solicitudes de cambio de tráfico de “marcador de posición”. A no ser que se especifique lo contrario, respete el tiempo de espera sugerido tanto como sea posible, incluido el hecho de no enviar una alerta demasiado pronto.

Respete las siguientes normas para determinar la antelación del envío de alertas de tráfico:

## Tiempos de espera de Asignación de hardware


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

* Si tiene varios grupos de informes que empiezan o se incrementan y así suman a las cifras enumeradas anteriormente, el tiempo de espera se aplica a ellos como suma del tráfico esperado para cada uno de ellos.
* Tenga la siguiente información disponible para enviar un cambio de tráfico:

   * ID del grupo de informes
   * Visitas estimadas por día
   * Fecha go-live

* Las Alertas de clientes también son necesarias cuando el tráfico se reduce o cuando un grupo de informes queda obsoleto.

## Anulación de asignaciones de hardware por tráfico inexistente

Se anulará la asignación de hardware para nuevas cuentas, picos de tráfico e incrementos de tráfico si el tráfico proyectado en la alerta del cliente no se materializa dentro de las 4 semanas de la “Fecha de lanzamiento”. Si el tráfico aún está anticipado, se debe generar una nueva alerta de cliente como incremento de tráfico.
