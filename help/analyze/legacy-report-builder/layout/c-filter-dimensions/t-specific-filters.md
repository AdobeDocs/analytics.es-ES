---
description: Filtros que aplican términos de dimensión específicos.
title: Filtros específicos
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
feature: Report Builder
role: User, Admin
exl-id: e5f2d67c-3add-4d51-8a76-ee3b2a6eef94
TQID: https://experienceleague.adobe.com/yNIeTJwwWtjXkbi47lX1Ve-Rbz6lF1PazD4YxxXa0Ac
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 336
ht-degree: 46%

---

# Filtros específicos

{{legacy-arb}}

Filtros que aplican términos de dimensión específicos.

Puede buscar elementos de dimensión específicos creando un filtro que coincida con criterios exactos. Por ejemplo, puede crear el siguiente tipo de filtro: página en [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Para crear un filtro específico**

1. Cree o edite una solicitud y avance en el [!UICONTROL Asistente para solicitudes: Paso 2].

   ![Captura de pantalla que muestra el filtro por opciones: Aplicación, Usuario y Proyecto.](/help/admin/tools/assets/filter.png)

1. En el [!UICONTROL Asistente para solicitudes: Paso 2], haga clic en el vínculo situado junto a la dimensión en la cuadrícula y, a continuación, seleccione **[!UICONTROL Filtro]**.

1. Habilitar **[!UICONTROL específico]**.

   ![Captura de pantalla del cuadro de diálogo Elegir página con la opción Específica seleccionada.](assets/choose_page_specific01.png)

1. Active una de las siguientes opciones específicas:

   * **Desde rango de celdas:** Permite seleccionar datos de celdas. Puede seleccionar:
      * **Todas las celdas del rango:** Permite asignar todas las celdas del rango. El texto descriptivo explica cuántos grupos de celdas debe seleccionar. Para asignar más de un grupo de celdas, presione la tecla Ctrl mientras realiza selecciones sucesivas. Si el rango que se debe asignar contiene solo una celda, esta es la única opción disponible
      * **Primera celda del rango:** Basta con seleccionar la celda superior izquierda del rango y, a continuación, elegir una dirección para los datos. Además, si la solicitud tiene varios períodos, puede elegir la dirección de los períodos y si desea omitir un número determinado de celdas entre períodos.
   * **De la lista:** Permite seleccionar datos de una lista a la que se pueden agregar datos.
1. Si habilita **[!UICONTROL Desde la lista]**, seleccione cualquier elemento disponible de la lista, o bien haga clic en **[!UICONTROL Añadir]**.

   Al hacer clic en **[!UICONTROL Añadir]**, el formulario [!UICONTROL Seleccionar desde lista] muestra una lista de elementos de dimensión disponibles para el intervalo de fechas de la solicitud actual, con una limitación de los primeros 10 000 elementos. Se puede buscar entre estos elementos o hacer clic en **[!UICONTROL Más...]**, con lo que muestra el [!UICONTROL formulario de búsqueda] para crear una búsqueda más detallada de dimensiones.
1. En [!UICONTROL Seleccionar desde lista], haga clic en **[!UICONTROL Aceptar]**.
1. En el formulario [!UICONTROL Seleccionar página], guarde el filtro específico si lo desea y, a continuación, haga clic en **[!UICONTROL Aceptar]**.
