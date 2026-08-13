---
description: Filtros condicionales y de clasificación que se configuran mediante la lógica booleana con las expresiones de búsqueda Y/O.
title: Filtros más utilizados
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
feature: Report Builder
role: User, Admin
exl-id: 31587740-6caa-40cb-bb24-d7a15181f642
TQID: https://experienceleague.adobe.com/TLo2RytIM7ZQlpFMqXsTdoz7vFAXnwqoTJGHDG7gWLg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 633
ht-degree: 33%

---

# Filtros más utilizados

{{legacy-arb}}

Filtros condicionales y de clasificación que se configuran mediante la lógica booleana con las expresiones de búsqueda Y/O.

Los filtros más utilizados son filtros de expresión que se configuran mediante la lógica booleana con las condiciones AND/OR como, por ejemplo, [!UICONTROL La página no contiene &#x200B;]*`<product name>`* con condiciones o grupos de condiciones como [!UICONTROL Incluye todo], [!UICONTROL Incluye cualquiera] o [!UICONTROL Excluye todo]. Puede [guardar](/help/analyze/legacy-report-builder/layout/c-filter-dimensions/saved-filters.md) estas expresiones para otra solicitud de este libro u otros libros de trabajo.

**Para crear un filtro de este tipo**

1. Cree o edite una solicitud y avance en el [!UICONTROL Asistente para solicitudes: Paso 2].

1. En el [!UICONTROL Asistente para solicitudes: Paso 2], haga clic en el vínculo situado junto a la dimensión en la cuadrícula y, a continuación, seleccione **[!UICONTROL Filtro]**.

   ![Captura de pantalla que muestra el cuadro de diálogo Definir filtro con opciones para filtrar por aplicación, usuario y proyecto.](/help/admin/tools/assets/filter.png)

1. En el formulario [!UICONTROL Elegir página], habilite **[!UICONTROL Más populares]** y después configure las siguientes opciones:

   **Clasificación inicial:** Clasificación inicial de una dimensión. Una clasificación predeterminada de 1 indica el elemento principal de la lista de datos de los que se informa. Por ejemplo, para la dimensión [!UICONTROL Página], una marca de inicio de 1 indica la página más solicitada del sitio. Puede especificar 10 u otro valor como celda de rango inicial, lo que genera un informe que comience por 10 como celda más alta. Las métricas se organizan en orden descendente, de modo que los elementos de línea con la mayor actividad se informen primero en la lista. Si necesita más de 50 000 nombres de página en una solicitud, pero tiene miles de páginas sobre las que informar, puede copiar la solicitud y cambiar la clasificación inicial para recuperar los datos adecuados en bloques de 50 000.

   **Número de entradas:** (Solo [!UICONTROL diseño de tabla dinámica]) Define la cantidad de elementos obtenidos para una métrica concreta respecto a un intervalo de fechas. Algunas métricas pueden enumerar cientos de entradas para una métrica, mientras que otras pueden mostrar solo algunas. Por ejemplo, para la dimensión [!UICONTROL Sección del sitio], un número de entradas de 25 indica que el informe muestra las 25 páginas más visitadas.

   Las flechas permiten cambiar el [!UICONTROL Rango inicial] y el [!UICONTROL Número de entradas] del primer punto de datos de la hoja. De manera predeterminada, [!UICONTROL Rango inicial] está establecido en 1 y [!UICONTROL Número de entradas] en 10. Estos valores se pueden ajustar de un mínimo de uno a un máximo de 50 000 para determinadas métricas. Cada métrica tiene su propio límite en [!UICONTROL Número de entradas]. En estos campos no se permiten valores negativos ni cero. Si elige [!UICONTROL Clasificación inicial] como 15 y [!UICONTROL Número de entradas] como 10, las solicitudes de datos para la métrica devolverán las 10 páginas más visitadas, donde la primera página más visitada es la número 15 en la lista para el intervalo de fechas específico. Todas las páginas más solicitadas clasificadas del 15 al 25 se muestran en orden descendente.

   >[!NOTE]
   >
   >La aplicación de filtros a solicitudes existentes produce cambios en los datos presentados. Supongamos que ha asignado las diez [!UICONTROL Páginas] principales a las celdas de $A$1 a $A$10, con 1 para [!UICONTROL Rango inicial] y 10 para [!UICONTROL Número de entradas]. Si cambia estos valores para mostrar 1 para [!UICONTROL Rango inicial] y solo 3 para [!UICONTROL Número de entradas], dejarán de aparecer los datos que antes rellenaban las celdas de $A$4 a $A$10.

1. Para crear una expresión de búsqueda, haga clic en **[!UICONTROL Añadir]**.

1. En el formulario [!UICONTROL Definir filtro], configure las condiciones adecuadas para sus necesidades.


   ![Captura de pantalla que muestra el cuadro de diálogo Definir filtro.](assets/expressions_define_filter.png)

   El icono de selección de celda permite localizar una condición definida en el valor de una celda. ![Icono de seleccionar celda.](assets/select_cell_icon.png)

   El vínculo **Agregar condición** le permite agregar una condición a la expresión. No existe límite en la cantidad de condiciones que se pueden añadir.

1. Haga clic en **[!UICONTROL Aceptar]**.

   ![Captura de pantalla del cuadro de diálogo Definir filtro con el botón Aceptar en la parte inferior derecha.](assets/choose_page_02.png)

1. En el formulario [!UICONTROL Seleccionar página], haga clic en **[!UICONTROL Guardar]** para guardar la expresión.
1. Haga clic en **[!UICONTROL Aceptar]**.
