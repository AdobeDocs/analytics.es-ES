---
title: Programar un pico de tráfico
description: Asociarse con Adobe para asegurarse de que los eventos de alto tráfico no experimenten latencia.
feature: Report Suite Settings
role: Admin
exl-id: a6bbd975-6d31-40f5-8f80-491ec3a5c5f5
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 97%

---

# Programar un pico de tráfico

Adobe intenta asociarse con los clientes para garantizar que un evento de alto tráfico se realice correctamente. La programación de los picos de tráfico es el punto de partida de ese proceso de asociación. La sección Programación de pico permite alertar a Adobe de los picos de tráfico temporales para que se puedan asignar los recursos adecuados para administrarlos. Puede estimar las llamadas al servidor anteriores para hacerse una mejor idea del tamaño del pico de tráfico que debe programar.

Se utiliza el equilibrio de datos avanzado del lado del servidor con varios empleados dedicados para garantizar que todos los clientes tengan los informes más actualizados posibles. A medida que su organización notifica a Adobe de picos de tráfico, Adobe puede asegurarse de que el aumento repentino de tráfico sea una experiencia positiva. Si no se notifica a Adobe de los incrementos de tráfico, puede aumentar la latencia durante períodos críticos de creación de informes.

{{$include /help/_includes/traffic-lead-time.md}}

## Programar un pico de tráfico

Para programar un pico de tráfico:

1. Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Administradores]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Grupos de informes]**.
1. Selección de un grupo de informes.
1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Administración de tráfico]** > **[!UICONTROL Programar pico]**.
1. (Opcional) Puede estimar las llamadas al servidor anteriores para hacerse una mejor idea del tamaño del pico de tráfico que debe programar.

   Por ejemplo, puede obtener el promedio diario de llamadas al servidor correspondiente a un lapso de tiempo específico del año pasado, además de un aumento esperado del volumen de llamadas de este año. Así, podrá programar un pico de tráfico basado en este factor de multiplicación.

   1. En el área **[!UICONTROL Llamadas al servidor anteriores]**, seleccione una fecha de inicio y de finalización para los grupos de informes seleccionados.

      Se generan las cantidades para [!UICONTROL **Día punta**], [!UICONTROL **Pico diario de llamadas al servidor**] y [!UICONTROL **Promedio diario de llamadas al servidor**].

   1. Introduzca un valor para el factor de multiplicación y, a continuación, seleccione **[!UICONTROL Hacer clic para multiplicar y establecer]**.

      El valor de todas las columnas se multiplica para cada grupo de informes.
1. En el área [!UICONTROL **Establecer parámetros de pico**], en el campo **[!UICONTROL Fecha de inicio del pico]**, especifique la fecha en la que espera que comience el pico de tráfico.
1. En el campo **[!UICONTROL Fecha de fin del pico]**, especifique la fecha en la que espera que termine el pico de tráfico.
1. En el campo **[!UICONTROL Pico diario de llamadas al servidor]**, especifique el pico total de páginas vistas previsto por día durante el periodo del pico de tráfico.
1. En el campo **[!UICONTROL Pico horario de llamadas al servidor]**, especifique el pico total de páginas vistas previsto por hora durante el periodo del pico de tráfico.
1. Seleccione **[!UICONTROL Enviar]**.

   Asegúrese de indicar el número total de vistas de página esperadas, no solo las vistas de página adicionales.

   >[!NOTE]
   >
   >Para programar un pico de tráfico, facilite un número de teléfono dentro de su información de contacto de usuario para que Adobe pueda ponerse en contacto con usted si tiene alguna pregunta que hacer.

## Por qué es importante programar siempre los picos de tráfico

Cuando los clientes notifican a Adobe de picos de tráfico para cada grupo de informes, Adobe hace todo lo posible para garantizar que tenga un impacto mínimo en la creación de informes.

* Las organizaciones que tienen picos de tráfico programados reciben prioridad si los datos empiezan a latentes. La importancia de este concepto es especialmente crítica durante la temporada de vacaciones, ya que muchas organizaciones programan picos de tráfico.
* Si Adobe observa que ha sobreestimado o subestimado significativamente el tráfico esperado en comparación con años anteriores, puede ponerse en contacto con usted para garantizar la precisión.
* Es importante programar un pico de tráfico cada año, incluso si la organización recibe el mismo pico cada año. Muchas organizaciones lanzan nuevas aplicaciones, combinan grupos de informes y migran o retiran grupos de informes a lo largo del año. Adobe no permite saber con certeza qué grupos de informes reciben tráfico adicional a menos que su organización programe un pico de tráfico cada vez. Aunque Adobe utiliza datos históricos para obtener una estimación, es importante que los recursos adicionales se coloquen en el grupo de informes correcto.

## Acciones que puede llevar a cabo su organización

Adobe desea asegurarse de que su experiencia con los informes actualizados sea coherente. Para realizar esta tarea con mayor eficacia, Adobe recomienda encarecidamente lo siguiente:

* Programe el tiempo de espera para todos los picos de tráfico. **Es especialmente importante que cualquier pico de tráfico anticipado en los meses de noviembre a diciembre esté programado para el 15 de septiembre**. Si se pierde la fecha límite, programe el pico lo antes posible. Menos tiempo de espera es mejor que ninguno y Adobe funciona con los recursos actuales para adaptarse mejor a los grupos de informes.
* Si Adobe se pone en contacto con usted con respecto a un pico de tráfico programado, asegúrese de comunicar si la creación de informes en tiempo real o la creación de informes de procesamiento completo son más importantes. Algunas organizaciones dependen más de la creación de informes en tiempo real que otras. Comprender qué tipo de creación de informes se utiliza puede ayudar a Adobe a priorizar en consecuencia.
* Comunicarse con el equipo de su cuenta de Adobe para conocer los informes más importantes y cuándo extraerlos puede ayudarle a abogar por usted.
