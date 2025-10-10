---
description: Modifique la configuración y las propiedades de todos los tipos de visualizaciones de superposición en Activity Map.
title: Definición de la configuración de Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: User, Admin
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
source-git-commit: 13ad9d40ad74a8dffe05d899db54f4d77cbcc34c
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 4%

---

# Definición de la configuración de Activity Map

El panel Configuración de Activity Map le permite modificar la configuración y las propiedades de todos los tipos de visualizaciones de superposición.

**[!UICONTROL Superposición de Activity Map]** > **Mostrar configuración (icono de engranaje)** > **[!UICONTROL Configuración]**

## Configuración general

Cambie la configuración general de la extensión y las superposiciones.

* **[!UICONTROL Compañías]**: muestra la organización actual de Analytics en la que inició sesión.
* **[!UICONTROL Nombre de página]**: muestra el nombre de la página actual.
* **[!UICONTROL Idioma]**: cambia el idioma de las etiquetas de extensión de Activity Map. Esta configuración no cambia el contenido del sitio web ni los nombres de los vínculos en los informes. Los idiomas admitidos son inglés, francés, chino (simplificado), chino (tradicional), alemán, japonés, coreano, español y portugués.
* **[!UICONTROL Superposiciones de etiquetas con]**: Determina qué es el texto de degradado o burbuja. La configuración predeterminada es [!UICONTROL Rango]. Las opciones incluyen: 
   * **[!UICONTROL Sin etiqueta]**: no hay texto dentro de las etiquetas, lo que las convierte en cuadros de color
   * **[!UICONTROL Valor]**: muestra el número de clics en vínculos ([Ocurrencias](/help/components/metrics/occurrences.md))
   * **[!UICONTROL Porcentaje]**: muestra la proporción de clics en vínculos en comparación con el número total de clics en vínculos en la página
   * **[!UICONTROL Rango]**: La clasificación numérica del vínculo según el número de clics en el mismo.
* **[!UICONTROL Tamaño de fuente de etiqueta]**: Determina el tamaño del texto dentro de la burbuja o degradado.
* **[!UICONTROL Color de degradado]**: permite cambiar el color de degradado cuando el tipo de visualización es [!UICONTROL Degradado].
* **[!UICONTROL Color de burbuja]**: permite cambiar el color de la burbuja cuando el tipo de visualización es [!UICONTROL Burbuja].
* **[!UICONTROL Degradado de color basado en]**: Determina en qué métrica se basa la intensidad de color de un vínculo cuando el tipo de visualización es [!UICONTROL Degradado].
   * **[!UICONTROL Principales 30 rangos]**: La intensidad del color se normaliza para los 30 vínculos principales.
   * **[!UICONTROL Valor absoluto de métrica]**: la intensidad del color es una función del valor absoluto de la métrica.
* **[!UICONTROL Transparencia de degradado]**: Determina la transparencia de las superposiciones de degradado cuando el tipo de visualización es [!UICONTROL Degradado]. Este control deslizante le permite hacer que la superposición de color sea completamente transparente, completamente opaca o en cualquier lugar intermedio.

## Configuración estándar

Ajuste la configuración de la vista estándar.

* **[!UICONTROL Filtrado dinámico de datos]**: Permite cambiar los vínculos que se muestran.
   * **[!UICONTROL Principales]**: Muestra los vínculos más populares. Utilice la lista desplegable numérica de la derecha para determinar el número de vínculos principales que se mostrarán. Las opciones incluyen 1, 10, 50 y 100.
   * **[!UICONTROL Inferior]**: muestra los vínculos menos populares en función de la lista desplegable de números. Utilice la lista desplegable numérica de la derecha para determinar el número de vínculos inferiores que se mostrarán. Las opciones incluyen 1, 10, 50 y 100.
   * **[!UICONTROL Todos los vínculos]**: no aplique el filtrado dinámico de datos. La lista desplegable numérica no se aplica cuando se selecciona esta opción.
* **[!UICONTROL Ocultar superposiciones de vínculos que no recibieron ninguna visita]**: Los vínculos de la página sin ningún clic en vínculo no muestran ninguna superposición. Estos vínculos se excluyen del filtrado dinámico de datos.

## Configuración de Live

* **[!UICONTROL Mostrar arriba]**: muestra el número superior de ganadores o perdedores en función de la lista desplegable numérica de la izquierda.
* **[!UICONTROL Excluir inferior (%)]**: filtre el porcentaje inferior de cambios de vínculos para ver solamente los vínculos con datos suficientes para mostrar las pérdidas o ganancias relevantes. El porcentaje se calcula basándose en el número de vínculos que haya en la página. Por ejemplo, si se filtra el 10 % inferior de una lista de 200 vínculos, se filtran los 20 vínculos inferiores.
* **[!UICONTROL Actualizar datos automáticamente]**: Determina si los datos de Analytics que se muestran en la superposición se actualizan automáticamente cuando se calcula un nuevo período.
* **[!UICONTROL Período de actualización automática]**: cuando está activada, actualiza la página con cada recuperación de datos nuevos para que los vínculos de la página estén más estrechamente sincronizados con los datos recopilados.
