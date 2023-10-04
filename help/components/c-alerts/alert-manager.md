---
description: Gestionar alertas.
title: Información general de Alert Manager
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: cfae0661dfa9c61daea33c3a52204793ce3d35c1
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 41%

---

# Administrador de alertas

El Administrador de alertas está estructurado de la misma manera que [Administrador de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=es) y el [Administrador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=es).

![](assets/alert-manager.png)

## Acceso al Administrador de alertas

1. En Adobe Analytics, seleccione [!UICONTROL **Componentes**] > [!UICONTROL **Alertas**].

## Acciones disponibles en el Administrador de alertas

En el Administrador de alertas, puede:

* Acceda al Generador de alertas haciendo clic en **[!UICONTROL + Añadir]**.
* Etiquetar alertas. Esto permite organizarlas para facilitar su uso.
* Eliminar alertas.
* Cambiar el nombre de alertas.
* Aprobar alertas.
* Copiar alertas.
* Habilitar/deshabilitar alertas.
* **Renovar** una fecha de caducidad para la alerta. Es posible renovar una o más alertas seleccionándolas y haciendo clic en **[!UICONTROL Renovar]**. Esto hace que su fecha de caducidad pase a ser 1 año desde el día en que se hace clic en **[!UICONTROL Renovar]**, fuera cual fuera la fecha de caducidad original.
* Exportar una alerta a un archivo .CSV.
* Editar alertas haciendo doble clic en su título.
* Buscar alertas.
* Añadir alertas a otros grupos de informes.
* Especificar/cambiar el propietario de una alerta.
* Añadir otros filtros.
* Definir una **fecha de caducidad** para la alerta.

## Configuración de columnas

Puede configurar la información mostrada para cada alerta en el Administrador de alertas configurando las columnas que se muestran.

Para configurar las columnas visibles en el Administrador de alertas:

1. En Adobe Analytics, seleccione la **[!UICONTROL Componentes]** pestaña, luego seleccione **[!UICONTROL Alertas]**.

1. En el Administrador de alertas, seleccione **Personalizar columnas** icono ![Icono Personalizar columnas](assets/customize-columns-icon.png), luego seleccione las columnas que desea mostrar en el Administrador de alertas.

   Las columnas disponibles son las siguientes:

   | Título de columna | Descripción |
   |---|---|
   | Favoritos | Muestra iconos de estrella junto a cada alerta, lo que permite marcar las alertas como favoritas. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Título y descripción | Estos valores se proporcionan en el Generador de alertas. Para editar el título y la descripción, seleccione el vínculo del título para abrir el Generador de alertas. |
   | Grupo de informes | Indica en qué grupo de informes se guardó por última vez la alerta. |
   | Propietario | Indica a quién pertenece la alerta. Si no es el administrador, solo podrá ver las alertas que le pertenecen o que compartieron con usted. |
   | Etiquetas | Muestra las etiquetas aplicadas a la alerta, tanto por su parte como por parte de las personas que han compartido la alerta con usted. |
   | Compartido con | Enumera las personas o grupos (solo administrador) o todos (solo administrador) con los que compartió la alerta. |
   | Fecha de modificación | Indica la fecha de la última modificación de la alerta. |
   | Último uso | Muestra la fecha en la que se utilizó la alerta por última vez. <p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización, dónde se utiliza y si debe eliminarse o modificarse.</p><p>Esta información no incluye el uso de la API, el Report Builder o la Data Warehouse.</p> |

   {style="table-layout:auto"}
