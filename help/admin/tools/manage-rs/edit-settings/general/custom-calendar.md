---
description: Opciones de calendario aparte del modelo gregoriano. Las opciones incluyen los modelos de calendario 4-4-5, 4-5-4 y 5-4-4, todos ellos utilizados como estándar en el sector minorista. Los informes también ofrecen un calendario totalmente personalizable que puede configurar usted mismo.
title: Personalizar calendario
feature: Admin Tools
exl-id: 2196c7b7-7183-43a8-bb91-5a1e479819d4
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 91%

---

# Personalizar calendario

Opciones de calendario aparte del modelo gregoriano. Las opciones incluyen los modelos de calendario 4-4-5, 4-5-4 y 5-4-4, todos ellos utilizados como estándar en el sector minorista. Además, los informes ofrecen la opción de usar un calendario totalmente personalizable que puede configurar usted mismo.

**[!UICONTROL Administración]** > **[!UICONTROL Grupo de informes]** > Seleccionar grupo de informes > **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Personalizar calendario]**

>[!CAUTION]
>
>Al modificar el calendario se cambia la forma en que se procesan los datos (es decir, la definición de los visitantes únicos semanales y mensuales). Al cambiar la definición de semanas y meses de un calendario no se modifican los datos históricos. Esta configuración también afecta a los segmentos en función de intervalos de fechas.

El calendario se puede usar para definir el primer día de la semana y del año, y permite elegir un estilo de calendario comercial distinto. Los formatos de calendario se utilizan por distintos motivos, entre los que se incluyen la comparación de ventas y estandarización de la previsión, el análisis del costo en plantilla o la regulación del recuento de inventario físico. Por ejemplo, el sector minorista utiliza el calendario contable 4-5-4 para las temporadas de venta específicas de dicho sector. A continuación, se describe cada formato de calendario.

## Descripción de las opciones de personalización de calendario {#section_B0D224DACB914A378902A4E0E1234889}

| Calendario | Descripción |
|--- |--- |
| Calendario gregoriano | Utiliza el formato de calendario tradicional (de enero a diciembre con 30 o 31 días y un número variable de semanas en cada mes). |
| Calendario gregoriano modificado | Utiliza el calendario gregoriano tradicional, pero permite seleccionar el primer mes del año y el primer día de la semana. |
| Calendario comercial 4-5-4 | Divide cada mes según el número de semanas del mes. Es decir, enero tiene cuatro semanas y así sucesivamente. La National Retail Federation (Federación Nacional Minorista de EE. UU.) utiliza el formato de calendario 4-5-4. |
| Calendario personalizado | Ofrece tres formatos, según el número de semanas de cada mes. El número de semanas de cada mes depende del primer día del año seleccionado.  Un año tiene 52 semanas. Se divide esa cantidad entre 4 trimestres y se obtienen 13 semanas por trimestre. Pero un trimestre tiene 3 meses. Como 13 no es divisible entre 3, se acaba asignando la semana extra a uno de los meses para que el resultado siempre sea coherente.<ul><li>5-4-4 significa que el primer mes del trimestre tiene la semana extra. 4-5-4 significa que el segundo mes del trimestre tiene la semana extra, etc. En el calendario 4-4-5, la semana 53.ª se añade al último trimestre del año.</li><li>4-5-4:January tiene cuatro semanas, febrero tiene cinco, marzo tiene cuatro, y así sucesivamente.</li><li>4-4-5: enero tiene 4 semanas, febrero tiene otras 4, marzo tiene 5, y así sucesivamente.</li><li>5-4-4: enero tiene 5 semanas, febrero tiene 4, marzo tiene otras 4, y así sucesivamente.</li></ul> |

>[!NOTE]
>Estas opciones de calendario son compatibles con todas las herramientas de Adobe Analytics (Analysis Workspace, Report Builder, Activity Map), excepto con Data Warehouse. Data Warehouse solo admite totalmente el calendario gregoriano. Al elegir un calendario no gregoriano, Data Warehouse utilizará el intervalo de fechas esperado del calendario no gregoriano, pero es posible que los desgloses día/semana/mes de las filas del informe no sean lo esperado de un calendario no gregoriano.
