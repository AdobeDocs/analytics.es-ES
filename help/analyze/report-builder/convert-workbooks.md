---
title: Conversión de libros heredados de Report Builder
description: Obtenga información sobre cómo convertir los libros heredados basados en Report Builder para utilizar el nuevo Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: d7832dc56eb680f57a6875cf32e29fd5a8858098
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 1%

---

# Convertir libros heredados de Report Builder

Como parte del cambio a una nueva funcionalidad de Report Builder, puede convertir rápidamente sus libros basados en Report Builder heredados actuales (libros heredados) para utilizar la nueva funcionalidad de Report Builder [bloques de datos](create-a-data-block.md).

>[!IMPORTANT]
>
>Duplique cada libro y cambie el nombre de una versión antes de convertir el libro heredado. Esto garantiza que siempre tenga una copia del libro heredado original, en caso de que lo necesite.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Convertir libros](https://video.tv.adobe.com/v/3446185?captions=spa&quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Para convertir libros heredados, primero debe tener [configurado el nuevo Report Builder](/help/analyze/report-builder/report-builder-setup.md).


## Abrir un libro preexistente

Para abrir un libro de trabajo heredado, puede:

* Abra un libro heredado directamente desde el equipo local o la red. Cuando el libro heredado está abierto en Excel:

   1. Seleccione ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** en la barra de cinta de Excel.
   1. Seleccione **[!UICONTROL Login]** e inicie sesión en Report Builder.
   1. A continuación [convierta el libro heredado](#convert-a-workbook).

* Abra un libro preexistente programado desde la ficha **[!UICONTROL Programar]** en [Report Builder hub](report-builder-hub.md). Para ello, haga lo siguiente:

   1. Abra Excel y seleccione ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** en la barra de cinta de Excel.

   1. Seleccione **[!UICONTROL Login]** e inicie sesión en Report Builder.

   1. Seleccione **[!UICONTROL Programar]** en [Report Builder hub](report-builder-hub.md).
   1. Seleccione la ficha **[!UICONTROL Heredado]**. La pestaña enumera los libros programados basados en Report Builder heredados.

      ![Libros de trabajo heredados](assets/upgrade-legacy-schedule.png)

   1. Seleccione ![SelectBox](/help/assets/icons/SelectBox.svg) el libro programado que desea convertir de la lista y seleccione ![Descargar](/help/assets/icons/Download.svg). El libro se descarga y se abre en una nueva ventana en Excel. Ahora puede [convertir el libro Report Builder heredado](#convert-a--workbook).


## Conversión de un libro heredado

Para convertir el libro heredado:

1. Una vez abierto un libro preexistente, el nuevo Report Builder detecta si este libro contiene [solicitudes heredadas de Report Builder](/help/analyze/legacy-report-builder/home.md).

   ![solicitud de actualización del libro](assets/upgrade-workbook.png){zoomable="yes"}

1. Si se encuentran una o más solicitudes heredadas, haga clic en **[!UICONTROL Actualizar]** en el cuadro de diálogo **[!UICONTROL Actualizar libro]** para actualizar el libro.

   >[!NOTE]
   >
   >Debe actualizar cada solicitud individualmente. La actualización masiva no es compatible.


1. Aparece un cuadro de diálogo **[!UICONTROL Advertencia]** que le avisa de los cambios realizados en el libro si lo actualiza. También le insta a crear una copia de seguridad del libro heredado antes de continuar.

   ![advertencia de actualización](assets/upgrade-warning.png){zoomable="yes"}

1. Haga clic en **[!UICONTROL Continuar]** para continuar con la actualización.

   Si la actualización se realiza correctamente, aparece una notificación **[!UICONTROL La actualización del libro se ha completado]**.

   ![actualización completa](assets/upgrade-complete.png)

   * Seleccione **[!UICONTROL Cerrar]** para cerrar la notificación y continuar trabajando en el libro con solicitudes actualizadas para el nuevo Report Builder.

   * Seleccione **[!UICONTROL Descargar informe de actualización]** para descargar y abrir un nuevo libro de Excel que muestre el resultado de la actualización. Para ver un ejemplo, consulte lo siguiente.

     ![Libro de informes de actualización de Excel Report Builder](assets/upgrade-report.png)

Ahora puede [administrar el bloque de datos](/help/analyze/report-builder/manage-reportbuilder.md).


## Programar un libro heredado convertido

Tiene la opción de usar los detalles de programación del libro heredado que descargó y abrió desde la pestaña **[!UICONTROL Schedule]** en Report Builder hub. Esta opción no está disponible para libros heredados con detalles de programación que se abren desde el equipo local o la red.

1. Programar un libro. Para programar un libro heredado convertido con una programación heredada:

   * Seleccione **[!UICONTROL Enviar libro]** desde Report Builder hub o
   * Seleccione **[!UICONTROL Programar libro]** de la ficha **[!UICONTROL Libros]** disponible en la ficha **[!UICONTROL Programaciones]** de Report Builder.

1. Se le ofrece utilizar los detalles de programación del libro de trabajo heredado como la configuración de programación predeterminada.

   ![Migrar programación de libro heredado](assets/upgrade-legacy-schedule-convert.png)

   * Seleccione **[!UICONTROL Usar]** para usar los detalles de la programación heredada. Los detalles de la programación se rellenan previamente en la interfaz [Enviar libro](schedule-reportbuilder.md#schedule-a-workbook).
   * Seleccione **[!UICONTROL No usar]** para no usar los detalles de la programación heredada.
   * Seleccione **[!UICONTROL Cancelar]** para cancelar.

   Seleccione **[!UICONTROL Quitar metadatos heredados del uso futuro]** para no usar los detalles de programación heredados para este libro en el futuro.


## No se admiten las funciones heredadas de Report Builder {#unsupported}

Algunas funciones heredadas de Report Builder ya no están disponibles en el nuevo Report Builder

* Solicitudes en tiempo real.

* Informes de ruta/abandonos.

* Opción de FTP para informes programados.

* Métricas de visitantes. Las siguientes métricas se convierten en *visitantes únicos*, aunque el resultado del informe puede no ser una coincidencia exacta: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` y `visitorsyearly`. Esta conversión también se aplica a `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` y `mobilevisitorsyearly`.
