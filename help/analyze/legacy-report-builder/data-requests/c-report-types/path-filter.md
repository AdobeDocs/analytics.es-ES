---
description: Describe los pasos involucrados en la aplicación de filtros a un informe de ruta.
title: Filtrado de un informe de rutas mediante el Asistente para solicitudes
feature: Report Builder
role: User, Admin
exl-id: 085351b3-4d9c-45cf-b2a8-379f05932b26
TQID: https://experienceleague.adobe.com/DQ75Rl9mhTocg9aDfBfTYvwUZxb875iEynjc7BCcy90
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 427
ht-degree: 57%

---

# Filtrado de un informe de rutas mediante el Asistente para solicitudes

{{legacy-arb}}

Describe los pasos involucrados en la aplicación de filtros a un informe de ruta.

Este ejemplo utiliza las rutas de sección del sitio.

1. En Report Builder de Adobe, haga clic en **[!UICONTROL Crear]** para abrir el Asistente para solicitudes.
1. Seleccione el grupo de informes adecuado.
1. En la vista de árbol a la izquierda, seleccione **[!UICONTROL Rutas]** > **[!UICONTROL Sección del sitio]** > **[!UICONTROL Sección del sitio Rutas]**.

   ![Captura de pantalla que muestra las rutas de sección del sitio seleccionadas.](assets/site_section_path_1.png)

1. Especifique las fechas adecuadas.

1. Haga clic en **[!UICONTROL Siguiente]**.

1. En el paso 2 del asistente, en **[!UICONTROL Rótulos de fila]**, haga clic en el vínculo **[!UICONTROL 1-10 principales (patrón aplicado)]**. En un informe de ruta, se aplica un patrón de forma predeterminada.

   ![Captura de pantalla que muestra el patrón de ruta predeterminado.](assets/site_section_path_2.png)

1. Seleccione la opción **[!UICONTROL Filtro]**.

   ![Captura de pantalla que resalta la opción Filtro.](assets/filter_option.png)

1. En el cuadro de diálogo **[!UICONTROL Definir el patrón de la ruta de &quot;Rutas de sección del sitio&quot;]**, podrá especificar
   * La clasificación inicial del primer informe.
   * El número de entradas que desea que se muestren en este informe.
1. Haga clic en **[!UICONTROL Editar]** para definir un patrón de ruta.

1. Si desea un patrón personalizado, arrastre y suelte cualquier **[!UICONTROL Objeto de patrón]** de la lista izquierda en el **[!UICONTROL Lienzo generador de patrones]** a la derecha.

   ![](assets/custom_pattern.png)

1. También puede seleccionar un patrón predefinido de la lista desplegable de **[!UICONTROL Seleccionar un patrón]** y modificarlo. A continuación verá los patrones disponibles:

   ![](assets/select_a_pattern.png)

   Algunos de estos patrones son específicos de Report Builder: patrón de elemento siguiente de la ruta de entrada, patrón de elemento anterior de la ruta de salida, patrón de elemento siguiente.

## Para editar un patrón predefinido

Puede editar un patrón predefinido después de seleccionar un patrón.

1. Siguiendo los pasos anteriores, seleccione el patrón. Por ejemplo, seleccione el **[!UICONTROL Patrón de sitio de salida]**:

   ![Captura de pantalla que resalta el patrón seleccionado.](assets/exited_site_pattern.png)

1. Defina la ruta de la sección del sitio que sigue el usuario antes de salir. Haga clic en **[!UICONTROL Elemento(s) específico(s): 0 seleccionados]**. Puede definir esta ruta seleccionándola entre un rango de celdas si edita una solicitud existente o seleccionándola de una lista de secciones.

1. Para seleccionar entre un rango de celdas de una solicitud anterior, seleccione **[!UICONTROL Desde el rango de celdas]** y haga clic en el icono de selector de celdas. A continuación, seleccione las celdas del informe.

   ![Captura de pantalla que muestra las opciones para elegir de un rango de celdas o de una lista.](assets/choose_site_section_paths.png)

1. Para seleccionar entre una lista de secciones de sitio, seleccione **[!UICONTROL Desde la lista]** y haga clic en **[!UICONTROL Añadir]**.

1. Para mover elementos desde la columna de **[!UICONTROL Elementos disponibles]** a la columna de **[!UICONTROL Elementos seleccionados]**, selecciónelos y haga clic en la flecha naranja. Haga clic en **[!UICONTROL Aceptar]**.

   ![Captura de pantalla que muestra los elementos disponibles y los elementos seleccionados.](assets/move_site_section_elements.png)

1. Para guardar el patrón que acaba de establecer, haga clic en **[!UICONTROL Guardar]**.

1. Haga clic en **[!UICONTROL Aceptar]** tres veces y, a continuación, haga clic en **[!UICONTROL Finalizar]** para generar la ruta filtrada.
