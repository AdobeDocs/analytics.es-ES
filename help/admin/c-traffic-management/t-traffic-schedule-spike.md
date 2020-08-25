---
title: Programar un pico de tráfico
description: Asociarse con el Adobe para asegurarse de que los eventos de alto tráfico no experimenten latencia.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 24%

---


# Programar un pico de tráfico

Adobe intenta asociarse con los clientes para garantizar que un evento de alto tráfico sea exitoso. La programación de picos de tráfico es el punto de partida en ese proceso de asociación. La sección Programar picos permite avisar a Adobe de los picos de tráfico temporales, para que se puedan asignar los recursos adecuados.

El equilibrio de datos avanzado del lado del servidor con varios empleados dedicados se utiliza para garantizar que todos los clientes tengan los informes más actualizados posibles. A medida que su organización notifica al Adobe de picos de tráfico, el Adobe puede asegurarse de que el aumento repentino del tráfico sea una experiencia positiva. Si no se notifica al Adobe el aumento del tráfico, puede aumentar la latencia durante períodos de sistema de informes críticos.

Lea la información sobre el tiempo de espera [necesario para aumentos](/help/admin/c-traffic-management/traffic-lead-time.md) de tráfico antes de programar un pico de tráfico.

1. Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]**.
1. Selección de un grupo de informes.
1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Administración de tráfico]** > **[!UICONTROL Programar pico]**.
1. En el campo **[!UICONTROL Fecha de inicio del pico]**, especifique la fecha en la que espera que comience el pico de tráfico.
1. En el campo **[!UICONTROL Fecha de fin del pico]**, especifique la fecha en la que espera que termine el pico de tráfico.
1. En el campo **[!UICONTROL Vistas de página diarias esperadas durante el pico]**, especifique el total de vistas de página diarias esperadas durante el período del pico de tráfico, y haga clic en **[!UICONTROL Enviar]**.

   Asegúrese de indicar el número total de vistas de página esperadas, no solo las vistas de página adicionales.

   >[!NOTE]
   >
   >Para programar un pico de tráfico, facilite un número de teléfono dentro de su información de contacto de usuario para que Adobe pueda ponerse en contacto con usted si tiene alguna pregunta que hacer.

## Por qué es importante programar siempre los picos de tráfico

Cuando los clientes notifican al Adobe los picos de tráfico para cada grupo de informes, Adobe hace todo lo posible para garantizar que tenga un impacto mínimo en el sistema de informes.

* Las organizaciones que tienen picos de tráfico programados reciben prioridad si los inicios de datos se mantienen latentes. La importancia de este concepto es especialmente crítica durante la temporada de fiestas, ya que muchas organizaciones programan picos de tráfico.
* Si el Adobe observa que se ha sobreestimado o subestimado significativamente el tráfico esperado en comparación con años anteriores, puede ponerse en contacto con usted para garantizar la precisión.
* Es importante programar un pico de tráfico cada año, incluso si su organización recibe el mismo pico cada año. Muchas organizaciones lanzan nuevas aplicaciones, combinan grupos de informes y migran o retiran grupos de informes a lo largo del año. El Adobe no tiene forma de saber con certeza qué grupos de informes reciben tráfico adicional a menos que su organización programe un pico de tráfico cada vez. Aunque Adobe utiliza datos históricos para obtener una estimación, es importante que los recursos adicionales se coloquen en el grupo de informes correcto.

## Acciones que su organización puede llevar a cabo

Adobe desea asegurarse de que su experiencia con el sistema de informes actualizado sea coherente. Para realizar esta tarea de manera más eficaz, Adobe recomienda encarecidamente lo siguiente:

* Programe todos los picos de tráfico según el Tiempo de espera [necesario para los aumentos](traffic-lead-time.md)de tráfico. **Es especialmente importante que cualquier pico de tráfico anticipado en los meses de noviembre a diciembre esté programado para el 15** de septiembre. Si no cumple con la fecha límite, programe el pico lo antes posible. Menos tiempo de espera es mejor que ninguno y Adobe funciona con los recursos actuales para adaptarse mejor a los grupos de informes.
* Si Adobe se pone en contacto con usted en relación con un pico de tráfico programado, asegúrese de comunicarse si el sistema de informes en tiempo real o el sistema de informes de procesamiento completo son más importantes. Algunas organizaciones dependen más del sistema de informes en tiempo real que otras. El comprender qué tipo de sistema de informes se utiliza puede ayudar a los Adobes a priorizar en consecuencia.
* Comunicarse con el administrador de su cuenta sobre los informes más importantes y cuándo los extrae puede ayudarles a defenderse.
