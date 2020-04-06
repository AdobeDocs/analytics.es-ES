---
description: Adobe requiere un aviso previo para nuevas configuraciones de cuenta, picos de tráfico e incrementos de tráfico. El hardware debe asignarse por adelantado para minimizar la latencia y los posibles efectos adversos para el sistema en general.
title: Tiempo de espera necesario para aumentos de tráfico
topic: Admin tools
uuid: aa3fb882-51b0-458f-917b-7c54d5659623
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Tiempo de espera necesario para aumentos de tráfico

Adobe requiere un aviso previo para nuevas configuraciones de cuenta, picos de tráfico e incrementos de tráfico. El hardware debe asignarse por adelantado para minimizar la latencia y los posibles efectos adversos para el sistema en general.

La asignación del hardware está dirigida por alertas enviadas mediante la interfaz de usuario de Reports &amp; Analytics.

>[!IMPORTANT] Adobe no puede admitir solicitudes de cambio de tráfico de “marcador de posición”. A no ser que se especifique lo contrario, respete el tiempo de espera sugerido tanto como sea posible, incluido el hecho de no enviar una alerta demasiado pronto. Consulte [Programar un pico de tráfico](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) o [Especificar un incremento permanente de tráfico](/help/admin/c-traffic-management/t-traffic-permanent.md).

Utilice las siguientes directrices para determinar con qué antelación debe enviar una alerta de tráfico:

## Plazos de asignación de hardware

<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Estimaciones de tráfico diario (visitas individuales) </th>
   <th colname="col2" class="entry"> <p>Tiempo de espera necesario (de enero a octubre) </p> </th>
   <th colname="col3" class="entry"> <p>Tiempo de espera necesario (de noviembre a diciembre) </p> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Hasta 1.000.000 </td>
   <td colname="col2"> No se necesita tiempo de espera </td>
   <td colname="col3"> No se necesita tiempo de espera </td>
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

Otras cosas a considerar:

* Si tiene varios grupos de informes que comienzan o aumentan y que se suman a los números enumerados arriba, el tiempo de espera se aplica como una suma del tráfico esperado para cada uno de ellos.
* Tenga disponible la siguiente información para enviar un cambio de tráfico:

   * ID del grupo de informes
   * Visitas diarias estimadas
   * Fecha de lanzamiento

* Las alertas de cliente también son necesarias cuando el tráfico disminuye o un grupo de informes queda obsoleto.

## Anulación de asignaciones de hardware por tráfico inexistente

Se anulará la asignación de hardware para nuevas cuentas, picos de tráfico e incrementos de tráfico si el tráfico proyectado en la alerta del cliente no se materializa dentro de las 4 semanas de la “Fecha de lanzamiento”. Si el tráfico aún está anticipado, se debe generar una nueva alerta de cliente como incremento de tráfico.
