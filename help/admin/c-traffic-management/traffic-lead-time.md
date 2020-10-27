---
description: Adobe necesita que se informe por adelantado en caso de nuevas configuraciones de cuentas, picos de tráfico e incrementos de tráfico. El hardware debe asignarse por adelantado para minimizar la latencia y las posibles consecuencias adversas en el sistema general.
title: Tiempo de espera necesario para aumentos de tráfico
topic: Admin tools
uuid: aa3fb882-51b0-458f-917b-7c54d5659623
translation-type: tm+mt
source-git-commit: a114bef4679da24d4fd6323a55c9ccf52ac772ed
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 100%

---


# Tiempo de espera necesario para aumentos de tráfico

Adobe necesita que se informe por adelantado en caso de nuevas configuraciones de cuentas, picos de tráfico e incrementos de tráfico. El hardware debe asignarse por adelantado para minimizar la latencia y las posibles consecuencias adversas en el sistema general.

La asignación del hardware está dirigida por alertas enviadas mediante la interfaz de usuario de Reports &amp; Analytics.

>[!IMPORTANT]
>
> Adobe no puede admitir solicitudes de cambio de tráfico de “marcador de posición”. A no ser que se especifique lo contrario, respete el tiempo de espera sugerido tanto como sea posible, incluido el hecho de no enviar una alerta demasiado pronto. Consulte [Programar un pico de tráfico](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) o [Especificar un incremento permanente de tráfico](/help/admin/c-traffic-management/t-traffic-permanent.md).

Respete las siguientes normas para determinar la antelación del envío de alertas de tráfico:

## Tiempos de espera de Asignación de hardware

<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Estimativos de tráfico DIARIO (visitas individuales) </th>
   <th colname="col2" class="entry"> <p>Tiempo de espera necesario (de enero a octubre) </p> </th>
   <th colname="col3" class="entry"> <p>Tiempo de espera necesario (de noviembre a diciembre) </p> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Hasta 1.000.000 </td>
   <td colname="col2"> No existe tiempo de espera necesario </td>
   <td colname="col3"> No existe tiempo de espera necesario </td>
  </tr>
  <tr>
   <td colname="col1"> 1 000 000 - 5 000 000 </td>
   <td colname="col2"> Dos días HÁBILES </td>
   <td colname="col3" morerows="3"> Todos los incrementos de tráfico planeados para noviembre y diciembre deberían enviarse antes del 1 de septiembre. El objetivo de esto es permitir tiempo para la capacidad de compra si es necesario para ajustarse al tráfico de las fiestas. </td>
  </tr>
  <tr>
   <td colname="col1"> 5 000 000 - 10 000 000 </td>
   <td colname="col2"> Una semana natural </td>
  </tr>
  <tr>
   <td colname="col1"> 10 000 000 - 25 000 000 </td>
   <td colname="col2"> Dos semanas naturales </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Más de 25.000.000 </p> </td>
   <td colname="col2"> Uno o más meses </td>
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
