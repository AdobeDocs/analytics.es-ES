---
title: Convertir libros heredados de Report Builder
description: Obtenga información sobre cómo migrar y convertir libros de Report Builder heredados al nuevo Report Builder. Siga las instrucciones paso a paso de esta guía de migración sobre cómo convertir sin problemas los libros basados en Adobe Analytics.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 9743d7ac2a6c7e63d7a6701e60d05683c5680d36
workflow-type: tm+mt
source-wordcount: '1179'
ht-degree: 0%

---

# Convertir libros heredados de Report Builder

El Report Builder heredado finaliza su vida útil en junio de 2026. Debe migrar sus libros de trabajo de la versión heredada de Report Builder a la nueva versión de Report Builder. El nuevo Report Builder ofrece una forma cómoda de migrar libros rápidamente que se crean con el Report Builder heredado.

>[!IMPORTANT]
>
>Duplique cada libro y cambie el nombre de una versión antes de convertir el libro heredado. Esto garantiza que siempre tenga una copia del libro heredado original, en caso de que lo necesite.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Convertir libros](https://experienceleague.adobe.com/es/docs/analytics-learn/tutorials/exporting/report-builder/upgrade-and-reschedule-workbooks){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Para convertir libros heredados, primero debe tener [configurado el nuevo Report Builder](/help/analyze/report-builder/report-builder-setup.md).


## Abrir un libro preexistente

Para abrir un libro de trabajo heredado, puede:

* Abra un libro preexistente programado desde la ficha **[!UICONTROL Programar]** en [Report Builder hub](report-builder-hub.md). Esta acción es el método preferido para libros heredados programados. Tiene la opción de usar la programación asociada con el libro heredado en cuanto [programe el libro heredado convertido](#schedule-a-converted-legacy-workbook).

   1. Abra [!DNL Excel] y seleccione ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** en la barra de cinta [!DNL Excel].

   1. Seleccione **[!UICONTROL Login]** e inicie sesión en Report Builder.

   1. Seleccione **[!UICONTROL Programar]** en [Report Builder hub](report-builder-hub.md).
   1. Seleccione la ficha **[!UICONTROL Heredado]**. La pestaña enumera los libros programados basados en Report Builder heredados que ha creado.

      ![Libros de trabajo heredados](assets/upgrade-legacy-schedule.png)

   1. Seleccione ![SelectBox](/help/assets/icons/SelectBox.svg) el libro programado que desea convertir de la lista y seleccione ![Descargar](/help/assets/icons/Download.svg). El libro se ha descargado y se abre en una nueva ventana en [!DNL Excel]. Ahora puede [convertir el libro Report Builder heredado](#convert-a--workbook).


* Abra un libro heredado directamente desde el equipo local o la red. Cuando se utiliza este método, no se ofrece el uso de la programación que podría estar asociada con el libro de trabajo heredado. <br/>Cuando el libro heredado está abierto en [!DNL Excel]:

   1. Seleccione ![AdobeLogoRedOnWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** de la barra de cinta [!DNL Excel].
   1. Seleccione **[!UICONTROL Login]** e inicie sesión en Report Builder.
   1. A continuación [convierta el libro heredado](#convert-a-workbook).


## Conversión de un libro heredado

Para convertir el libro heredado:

1. Una vez abierto un libro preexistente, el nuevo Report Builder detecta si este libro contiene [solicitudes heredadas de Report Builder](/help/analyze/legacy-report-builder/home.md).

   ![Captura de pantalla del informe de actualización de Report Builder [!DNL Excel] que muestra la actualización de la migración](assets/upgrade-workbook.png){zoomable="yes"}

1. Si se encuentran una o más solicitudes heredadas, haga clic en **[!UICONTROL Actualizar]** en el cuadro de diálogo **[!UICONTROL Actualizar libro]** para actualizar el libro.

   >[!NOTE]
   >
   >Debe actualizar cada solicitud individualmente. La actualización masiva no es compatible.


1. Aparece un cuadro de diálogo **[!UICONTROL Advertencia]** que le avisa de los cambios realizados en el libro si lo actualiza. También le insta a crear una copia de seguridad del libro heredado antes de continuar.

   ![Captura de pantalla del informe de actualización de Report Builder [!DNL Excel] que muestra la advertencia de migración](assets/upgrade-warning.png){zoomable="yes"}

1. Haga clic en **[!UICONTROL Continuar]** para continuar con la actualización.

   Si la actualización se realiza correctamente, aparece una notificación **[!UICONTROL La actualización del libro se ha completado]**.

   ![Captura de pantalla del informe de actualización de Report Builder [!DNL Excel] que muestra la migración completada](assets/upgrade-complete.png)

   * Seleccione **[!UICONTROL Cerrar]** para cerrar la notificación y continuar trabajando en el libro con solicitudes actualizadas para el nuevo Report Builder.

   * Seleccione **[!UICONTROL Descargar informe de actualización]** para descargar y abrir un nuevo libro de [!DNL Excel] que muestre el resultado de la actualización. Para ver un ejemplo, consulte lo siguiente.

     ![Captura de pantalla del informe de actualización de Report Builder [!DNL Excel] que muestra el informe de migración](assets/upgrade-report.png)

Ahora puede [administrar los bloques de datos](/help/analyze/report-builder/manage-reportbuilder.md) del libro. Estos bloques de datos son el resultado de la actualización y reemplazan las solicitudes de Report Builder heredadas.


## Programar un libro heredado convertido

Tiene la opción de usar los detalles de programación del libro heredado que descargó y abrió desde la pestaña **[!UICONTROL Schedule]** en Report Builder hub. Esta opción no está disponible para libros heredados con detalles de programación que se abren desde el equipo local o la red.

1. Para programar un libro heredado convertido con una programación heredada:

   * Seleccione **[!UICONTROL Enviar libro]** desde Report Builder hub o
   * Seleccione **[!UICONTROL Programar libro]** de la ficha **[!UICONTROL Libros]** disponible en la ficha **[!UICONTROL Programaciones]** de Report Builder.

1. Se le ofrece utilizar los detalles de programación del libro de trabajo heredado como la configuración de programación predeterminada.

   ![Captura de pantalla de las [!DNL Excel] opciones de configuración de programación heredadas de Report Builder](assets/upgrade-legacy-schedule-convert.png)

   * Seleccione **[!UICONTROL Usar]** para usar los detalles de la programación heredada. Los detalles de la programación se rellenan previamente en la interfaz [Enviar libro](schedule-reportbuilder.md#schedule-a-workbook).
   * Seleccione **[!UICONTROL No usar]** para no usar los detalles de la programación heredada.
   * Seleccione **[!UICONTROL Cancelar]** para cancelar.

   Seleccione **[!UICONTROL Quitar metadatos heredados del uso futuro]** para no usar los detalles de programación heredados para este libro en el futuro.


## Migración desde Report Builder heredado

Algunas funciones del Report Builder heredado no son compatibles, se admiten parcialmente o se implementan de forma diferente en Report Builder:

* **Solicitudes en tiempo real**. Las solicitudes en tiempo real no son compatibles y se eliminan del libro heredado convertido.

* **Informes de ruta/visitas en el orden previsto**. Las solicitudes de visitas en el orden previsto no son compatibles y se eliminan del libro heredado convertido.

* Opción **[!DNL FTP]para informes programados**. La opción de programar informes para enviarlos a una ubicación [!DNL FTP] ya no está disponible.

* Opción **Publicar libro en [!DNL Power BI] para informes programados**. La opción de programar informes para [!DNL Power BI] ya no está disponible.

* **Métricas de visitantes**. Las siguientes métricas se convierten en *visitantes únicos* en el libro heredado convertido, aunque el resultado del informe puede no ser una coincidencia exacta: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` y `visitorsyearly`. Esta conversión también se aplica a `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` y `mobilevisitorsyearly`.

* **Reautenticación automática**. Cuando abra un nuevo archivo de [!DNL Excel], deberá volver a autenticarse explícitamente. Esta nueva autenticación es una característica de seguridad de la funcionalidad [!DNL Office Add-ins].

* **Copie una hoja de cálculo con un grupo de bloques de datos**. Para admitir la copia de una hoja de cálculo que contenga más de un bloque de datos:

   1. Seleccione la ficha de hoja de cálculo del libro [!DNL Excel] que desee copiar.
   1. En el menú contextual de la ficha, seleccione **[!UICONTROL Mover o copiar...]**
   1. En el diálogo **[!UICONTROL Mover o copiar]**:
      1. Seleccione el lugar donde desea copiar la hoja de cálculo copiada.
      1. Asegúrese de habilitar **[!UICONTROL Crear una copia]**.
      1. Seleccione **[!UICONTROL Aceptar]**.
   1. Desde la hoja de cálculo de origen:
      1. Seleccione el rango de celdas que incluye todos los bloques de datos.
      1. Seleccione ![Copiar](/help/assets/icons/Copy.svg) **[!UICONTROL Copiar bloque de datos]** del [concentrador de Report Builder](/help/analyze/report-builder/report-builder-hub.md).
   1. En la hoja de cálculo de destino:
      1. Seleccione la celda en la que desea pegar el rango de celdas copiado.
      1. Seleccione ![Pegar](/help/assets/icons/Paste.svg) **[!UICONTROL Pegar bloque de datos]** del [concentrador de Report Builder](/help/analyze/report-builder/report-builder-hub.md).

* **Intervalo de fecha**. Report Builder no migra las opciones de formato de intervalo de fechas **[!UICONTROL Mostrar los períodos de inicio y finalización como]** aplicados a una etiqueta de fila para un intervalo de fechas en el Report Builder heredado.

* **Promedio**. Report Builder no migra la opción de formato seleccionada **[!UICONTROL Opciones medias]** (**[!UICONTROL Promedio diario]** hasta **[!UICONTROL Promedio anual]**) aplicada a una métrica en el Report Builder heredado. Utilice una métrica calculada para sustituir la opción seleccionada.

* **Anteponer/posponer texto**. Report Builder no migra el **[!UICONTROL texto de anteponer/posponer]** aplicado a una métrica en el Report Builder heredado.

* **Subtotales**. Report Builder no migra la opción de formato **[!UICONTROL SubTotal(this request)]** aplicada a una métrica en el Report Builder heredado. Cuando haya usado **[!UICONTROL SubTotal(this request)]** en una solicitud de libro de trabajo heredado, la funcionalidad se convierte a **[!UICONTROL Total]**. Por ejemplo: en un bloque de datos heredado con los 5 nombres de página principales donde ha utilizado **[!UICONTROL SubTotal(Vistas de página)]** para devolver la suma de las vistas de página de los 5 nombres de página principales. Después de la migración, el mismo bloque de datos con los cinco nombres de página principales devuelve la suma de las vistas de página para *todos* los nombres de página. Use la funcionalidad de métricas calculadas para sustituir la funcionalidad **[!UICONTROL SubTotal]** heredada.
