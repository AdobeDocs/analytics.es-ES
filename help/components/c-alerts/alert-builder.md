---
description: Utilice alertas en Analysis Workspace.
title: Información general del Generador de alertas
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: a71c3c6911ed2c2eb9202c8f149a44d6364017b8
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 36%

---

# Creación de alertas

>[!NOTE]
>
>El uso de alertas con detección de anomalías (también conocido como _alertas inteligentes_) solo está disponible para organizaciones con un paquete Adobe Analytics Select, Prime o Ultimate.

Las alertas de Adobe Analytics permiten recibir notificaciones basadas en porcentajes modificados o puntos de datos específicos. Según el paquete de Adobe Analytics, también puede utilizar alertas para activarlas en función de los umbrales de anomalías. (Las alertas de uso de llamadas al servidor son un tipo diferente de alerta que solo están disponibles para los administradores de Analytics. Estas alertas le notifican del riesgo o de la aparición de un exceso en los datos de asignación y consumo de llamadas al servidor. Para obtener más información, consulte [Alertas de uso de llamadas al servidor](/help/admin/admin/c-server-call-usage/scu-alerts.md).)

Para obtener información general más detallada sobre las alertas, consulte [Información general sobre alertas](/help/components/c-alerts/intellligent-alerts.md).

Para crear una alerta:

1. Comience a crear una alerta accediendo al generador de alertas. Puede acceder al Generador de alertas de cualquiera de estas formas:

   * Abra un proyecto en Analysis Workspace y seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Crear alerta]**.
   * Abra un proyecto en Analysis Workspace y utilice el siguiente método abreviado:

     `ctrl (or cmd) + shift + a`
   * Abra un proyecto en Analysis Workspace, seleccione uno o más elementos de línea en una tabla de forma libre, haga clic con el botón derecho y seleccione **[!UICONTROL Crear alerta a partir de la selección]**.

     De este modo, se rellena instantáneamente el generador de alertas para crear una alerta con las métricas y los filtros correctos.
   * Cree una alerta [desde el administrador de alertas](/help/components/c-alerts/alert-manager.md#create-alerts).

   Aparece el Generador de alertas. Esta interfaz resulta familiar a quienes hayan creado segmentos o calculado métricas en Analytics:

   ![](assets/alert-builder.png)

1. Especifique las siguientes opciones para configurar la alerta:

   | Opción | Descripción |
   |---------|----------|
   | [!UICONTROL **Título**] | Especifique un nombre para la alerta. El nombre de la alerta puede contener el nombre del umbral de informe o de métricas. |
   | [!UICONTROL **Descripción (opcional)**] | Especifique una descripción para la alerta. |
   | [!UICONTROL **Granularidad de tiempo**] | Seleccione la frecuencia con la que desea que se compruebe la métrica: cada hora, cada día, semanalmente o mensualmente.<p><b>Nota:</b>Para las vistas de datos con un calendario personalizado, no se admite la granularidad mensual en el Generador de alertas.<!--true?--></p> |
   | [!UICONTROL **Destinatarios**] | Especifique hacia dónde se puede enviar la alerta. Se puede enviar una alerta a un usuario de Analytics, un grupo de Analytics o a una dirección de correo electrónico sin procesar o a un número de teléfono.<p><b>Importante:</b>El número de teléfono debe estar precedido por &quot;+&quot; y [código de país](https://countrycode.org/).</p><p>El correo electrónico que el usuario recibe una vez que se activa una alerta tiene un aspecto similar al siguiente:</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Fecha de caducidad**] | Establezca la fecha y la hora en que desea que la alerta caduque. |
   | [!UICONTROL **Enviar una alerta cuando**] | [!UICONTROL **déclencheur de cualquiera de estas métricas**]: arrastre y suelte las métricas (incluidas las calculadas) aquí para crear déclencheur para la alerta.<p>Aparece el mensaje **&quot;componentes incompatibles&quot;** si no todas las métricas, dimensiones o segmentos de la alerta son compatibles con la vista de datos seleccionada actualmente.</p><p>Determine el umbral que debe superar la métrica para que se establezca la alerta. Puede ajustar este valor a un umbral y, a continuación, a una de las condiciones siguientes:</p><ul><li>existe anomalía</li><li>anomalía por encima de lo esperado</li><li>anomalía por debajo de lo esperado</li><li>mayor o igual que</li><li>menor o igual que</li><li>cambia por un</li><li>Puede establecer el umbral en 90 %, 95 %, 99 %, 99,75 % y 99,9 %.</li></ul><p>[!UICONTROL **Con todos estos filtros**]: Arrastre y suelte los segmentos o dimensiones para agregar filtros. Por ejemplo, si agrega un segmento &quot;Solo dispositivos móviles&quot; significará que la regla se aplica únicamente a los déclencheur móviles. Puede agregar filtros adicionales mediante una instrucción AND. Puede añadir las reglas AND u OR si hace clic en el icono de engranaje.</p><p>Consulte [Alertas - casos de uso](/help/components/c-alerts/alerts-use-cases.md) para ver casos de uso por ejemplo.</p> |
   | [!UICONTROL **Vista previa**] | La vista previa de alertas interactiva le muestra con qué frecuencia, aproximada, se activará una alerta en función de las experiencias pasadas.<p>Por ejemplo, si establece la granularidad de tiempo a diario, en la vista previa podrá ver cuántas veces se habrá activado una alerta para una métrica en particular durante los últimos 30 o 31 días.</p><p>Si observa que se habían activado demasiadas alertas, puede ajustar el umbral en el [Administrador de alertas](/help/components/c-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Seleccione [!UICONTROL **Guardar**].
