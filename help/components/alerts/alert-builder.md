---
description: Aprenda a crear alertas en Analysis Workspace.
title: Creación de alertas
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 100%

---

# Creación de alertas {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Granularidad de tiempo"
>abstract="La granularidad de tiempo hace referencia a la frecuencia con la que se comprueba la alerta."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>El uso de alertas con detección de anomalías (también conocido como _alertas inteligentes_) solo está disponible para organizaciones con un paquete de Adobe Analytics Prime o Ultimate.

Las alertas de Adobe Analytics permiten recibir notificaciones basadas en porcentajes modificados o puntos de datos específicos. Según el paquete de Adobe Analytics, también puede utilizar alertas para activarlas en función de los umbrales de anomalías. Las alertas de uso de llamadas al servidor son un tipo diferente de alerta que solo está disponible para los administradores de Analytics. Estas alertas le notifican del riesgo o de la aparición de un exceso en los datos de asignación y consumo de llamadas al servidor. Para obtener más información, consulte [Alertas de uso de llamadas al servidor](/help/admin/tools/server-call-usage/scu-alerts.md).

Para obtener información más detallada sobre las alertas, consulte [Información general sobre alertas](alerts-overview.md).

Para crear una alerta, haga lo siguiente:

1. Utilice cualquiera de las siguientes formas para crear una alerta:

   * Abra un proyecto en Analysis Workspace y seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Crear alerta]**.
   * Abra un proyecto en Analysis Workspace y, a continuación, utilice el método abreviado siguiente: ***cmd + mayús + a*** (macOS) o ***ctrl + mayús + a*** (Windows).
   * Abra un proyecto en Analysis Workspace, seleccione uno o más elementos de línea en una tabla de forma libre, haga clic con el botón derecho y seleccione **[!UICONTROL Crear alerta a partir de la selección]**. Esta acción rellena previamente de forma instantánea el [Generador de alertas](alert-builder.md) para crear una alerta con las métricas y los filtros correctos.
   * Cree una alerta [ desde el administrador de alertas](/help/components/alerts/alert-manager.md#create-alerts).

   Aparece el generador de alertas. Esta interfaz es similar a la interfaz para generar segmentos o métricas calculadas en Analytics.



## Generador de alertas

La interfaz del Generador de alertas es similar a la interfaz que se utiliza para generar segmentos o métricas calculadas en Customer Journey Analytics:

![Interfaz del generador de alertas](assets/alert-builder.png)

Especifique los siguientes detalles en el Generador de alertas para una alerta:

| Elemento | Descripción |
|---------|----------|
| **[!UICONTROL Título]** | Especifique un nombre para la alerta. El nombre de la alerta puede contener el nombre del umbral de informe o de métricas. |
| **[!UICONTROL Descripción (opcional)]** | Especifique una descripción para la alerta.  |
| **[!UICONTROL Granularidad de tiempo]** | Seleccione con qué frecuencia desea que se compruebe la métrica: diariamente, semanalmente o mensualmente.<p> |
| **[!UICONTROL Destinatarios]** | Especifique hacia dónde se puede enviar la alerta. Se puede enviar una alerta a un usuario de Analytics, un grupo de Analytics o a una dirección de correo electrónico sin procesar o a un número de teléfono.<p><b>Importante</b>: El número de teléfono debe estar precedido por `+` y un [código de país](https://countrycode.org/).</p><p>Un ejemplo del correo electrónico que recibe un usuario:</p><p>![Correo electrónico de alerta](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Fecha de caducidad]** | Establezca la fecha y la hora en que desea que la alerta caduque. |
| **[!UICONTROL Retraso]** | El tiempo necesario hasta que se completen los datos y hasta que estén disponibles para la creación de informes en Customer Journey Analytics varía según la organización, y suele oscilar entre 3 y 9 horas después del evento de datos. Para que las alertas sean precisas, los datos de evento de un intervalo de eventos determinado deben estar completos, lo que significa que Adobe ya no recibe datos de evento para el intervalo de eventos especificado.<p>Para tener en cuenta este retraso en el tiempo de ingesta, las alertas tienen un retraso predeterminado de 9 horas antes de enviarse.</p><p>Puede ajustar el retraso predeterminado de 9 horas a cualquier valor entre 0 y 24 horas. Sin embargo, si se reduce el retraso por debajo de 9 horas, puede indicar que está generando informes sobre datos incompletos, lo que da como resultado una información de alerta inexacta.</p><p>Considere los siguientes puntos a la hora de reducir el tiempo de demora:</p><ul><li>**Conozca la disponibilidad de los datos en comparación con su integridad**: todos los datos por lotes se incorporan a un conjunto de datos de Experience Platform solo después de un período de 3 a 9 horas. Para que las alertas sean precisas, la ingesta de datos debe ser completa, con todos los datos por lotes disponibles en el conjunto de datos.</li><li>**Determine cuánto tiempo tardan los datos en estar completos y disponibles en el conjunto de datos**: los tiempos de ingesta de datos difieren según la organización. Asegúrese de que el tiempo de demora que elija para el envío de alertas sea el mismo o menos frecuente que el tiempo que tardan los datos por lotes en estar disponibles en el conjunto de datos de Platform<!--add link? -->.</li><p>**Sugerencia:** la forma más precisa de saber el tiempo necesario para completar e incorporar todos los datos por lotes en el conjunto de datos de Platform es consultar a los ingenieros de datos de su organización.</p><p>También puede hacerse una idea general de cuánto tiempo tarda el envío por lotes de su organización en estar disponible en el conjunto de datos de Experience Platform. Creación de la siguiente tabla de forma libre en Analysis Workspace:</p><ol><li>En una tabla de forma libre de Analysis Workspace, añada una métrica de [!UICONTROL **Eventos**] y una dimensión de [!UICONTROL **Día**].</li><li>Desglose la dimensión [!UICONTROL **Día**] mediante una dimensión [!UICONTROL **Horas**].<p>Las horas que carecen de datos se muestran como 0.</p></li></ol><li>**Tenga en cuenta los errores en sus cálculos**: si reduce el tiempo de demora predeterminado, configure el retraso durante al menos una hora más que el tiempo que tarda su organización en completar la ingesta de datos. Por ejemplo, si hay un demora de 3 horas hasta que se complete la ingesta de datos, debe establecer el retraso en 4 horas.</li> |
| **[!UICONTROL Enviar una alerta cuando]** | [!UICONTROL **Se active cualquiera de estas métricas**]: arrastre y suelte las métricas (incluidas las métricas calculadas) aquí para crear activadores para la alerta.<p>Aparezca un mensaje **&quot;componentes incompatibles&quot;** si no todas las métricas, las dimensiones o los segmentos de la alerta son compatibles con la vista de datos seleccionada.  </p><p>Determine el umbral que debe superar la métrica para que se establezca la alerta. Puede ajustar este valor a un umbral y, a continuación, a una de las condiciones siguientes:</p><ul><li>existe anomalía</li><li>anomalía por encima de lo esperado</li><li>anomalía por debajo de lo esperado</li><li>mayor o igual que</li><li>menor o igual que</li><li>cambia por un</li><li>Puede establecer el umbral en 90 %, 95 %, 99 %, 99,75 % y 99,9 %.</li></ul><p>[!UICONTROL **Con todos estos filtros**]: arrastre y suelte los segmentos o dimensiones para añadir filtros a la alerta. Por ejemplo, si añade un segmento *Solo dispositivos móviles* significará que la regla solamente se activa para los dispositivos móviles. Puede añadir filtros adicionales mediante una instrucción AND. Puede añadir las reglas AND u OR si hace clic en el icono de engranaje.</p><p>Consulte [Alertas - casos de uso](alerts-use-cases.md) para ver casos de uso por ejemplo.</p> |
| **[!UICONTROL Vista previa]** | La vista previa de alertas interactiva le muestra con qué frecuencia, aproximadamente, se activa una alerta en función de la experiencia pasada.<p>Por ejemplo, si establece la granularidad de tiempo a diario, en la vista previa podrá ver cuántas veces se activó una alerta para una métrica en particular durante los últimos 30 o 31 días.</p><p>Si considera que se activan demasiadas alertas, puede ajustar el umbral en [Gestionar alertas](alert-manager.md).</p><p>![](assets/alert-preview.png){width="50%"}</p> |

<!--

   ![](assets/alert-builder.png)

1. Specify the following options to configure the alert:

   | Option | Description |
   |---------|----------|
   | [!UICONTROL **Title**]  | Specify a name for the alert. The alert name might contain the name of the report or the metrics threshold. |
   | [!UICONTROL **Description (optional)**] | Specify a description for the alert. |
   | [!UICONTROL **Time granularity**] | Select how often you want the metric to be checked: Hourly, Daily, Weekly, or Monthly.<p><b>Note:</b> For report suites with a custom calendar, monthly granularity in the Alert Builder is not supported.<!--true?--</p |
   | [!UICONTROL **Recipients**] | Specify where the alert can be sent. An alert can be sent to an Analytics user, an Analytics group, a raw email address, or to a phone number.<p><b>Important:</b> The phone number must be preceded by `+` and a [country code](https://countrycode.org/).</p><p>The e-mail that a user would receive once an alert has been triggered looks similar to:</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Expiration date**] | Set the date and time when you want the alert to expire. |
   | [!UICONTROL **Send an alert when**] | [!UICONTROL **Any of these metrics trigger**]: Drag and drop metrics (including calculated metrics) here to create triggers for the alert.<p>An **"incompatible components"** message appears if not all the metrics, dimensions, or segments in the alert are compatible with the currently selected data view.</p><p>Determine the threshold that the metric must exceed before an alert is set. You can set this value to a threshold and then to one of the following conditions:</p><ul><li>anomaly exists</li><li>anomaly is above expected</li><li>anomaly is below expected</li><li>is above or equals</li><li>is below or equals</li><li>changes by</li><li>You can set a threshold of 90%, 95%, 99%, 99.75%, and 99.9%.</li></ul><p>[!UICONTROL **With all of these filters**]: Drag and drop segments or dimensions to add filters. For example, adding a *Mobile Devices Only* segment would mean that the rule triggers only for mobile devices. You can add additional filters by using an AND statement. You can add AND or OR rules by clicking the gear icon.</p><p>See [Alerts - use cases](/help/components/alerts/alerts-use-cases.md) for example.</p> |
   | [!UICONTROL **Preview**] | The interactive alert preview shows you how often, approximately, an alert will fire based on past experience.<p>For example, if you set the time granularity to daily, the preview can tell you that the alert would have been triggered for a certain metric x times during the last 30 or 31 days. The preview approximation window is established by the alert frequency setting. For daily alert frequencies, the preview window approximates the previous 30 days. For weekly alert frequencies, the preview window approximates the last 12 weeks. For monthly alert frequencies, the preview window approximates the previous 12 months.</p><p>If you find that too many alerts will be triggered, you can adjust the threshold in the [Alert Manager](/help/components/alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Select [!UICONTROL **Save**].

-->