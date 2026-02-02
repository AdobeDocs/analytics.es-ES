---
title: Configuración De Report Builder
description: Obtenga información sobre cómo establecer la configuración de Report Builder.
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 28%

---

# Configuración de Report Builder


Utilice la variable **Configuración** para configurar los ajustes de nivel de aplicación, como el idioma mostrado por la IU o si se va a trabajar o no en modo sin conexión. La configuración se aplica inmediatamente y se establece para todas las sesiones futuras hasta que se cambia.

Para cambiar la configuración de Report Builder

1. Seleccione el icono **Configuración**.

1. Realice cambios en [habilitar el modo sin conexión de deshabilitación](#off-line-mode), [seleccionar un idioma](#language) o [habilitar solución de problemas](#troubleshooting).

1. Seleccione **[!UICONTROL Aplicar]**.

   ![Panel de intervalo de fechas de Report Builder que muestra el botón Cancelar y aplicar.](./assets/report-builder-settings.png){zoomable="yes"}

## Modo sin conexión

Cuando se crea y edita un bloque de datos en modo sin conexión, los datos no se recuperan. En su lugar, se utilizan datos de simulación para que pueda trabajar rápidamente sin esperar a que se ejecute la solicitud. Cuando vuelva a estar en línea, seleccione ![Actualizar](/help/assets/icons/Refresh.svg) **[!UICONTROL Actualizar el bloque de datos]** o ![ActualizarDocumento](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Actualizar todos los bloques de datos]** para actualizar los bloques de datos con datos reales.

Para habilitar el modo sin conexión

1. Seleccione ![Configuración](/help/assets/icons/Setting.svg).

1. Active **[!UICONTROL Activar el modo sin conexión]**.

1. Escriba un entero positivo en el campo **[!UICONTROL Mostrar datos de métricas]** como.

1. Seleccione **[!UICONTROL Aplicar]**.


## Idioma

Puede elegir el idioma de la interfaz de Report Builder. Todos los idiomas de Customer Journey Analytics admitidos están disponibles.

Para seleccionar el idioma utilizado en la interfaz de Report Builder:

1. Seleccione un idioma en el menú desplegable **[!UICONTROL Idioma]**.

1. Seleccionar **Aplicar.**

## Resolución de problemas

La configuración **[!UICONTROL registros de solución de problemas]** registra todos los datos de cliente/servidor en un archivo local. Utilice esta opción para resolver los tickets de asistencia.

Para habilitar los registros de solución de problemas, marque **[!UICONTROL Registrar la solicitud del Report Builder en el archivo local]**.

<!--
Use the **Settings** pane to configure application-level settings such as the language displayed by the UI or whether or not to work in off-line mode. The settings are applied immediately and they are set for all future sessions until they're changed.

To change Report Builder settings

1. Click the **Settings** icon.

1. Make changes to Enable off-line mode, select a Language, or enable Troubleshooting log settings.

1. Click **Apply**.

    ![Report Builder settings.](./assets/image38.png)

## Off-line mode

When creating and editing a data block in off-line mode, data is not retrieved. Instead, simulation data is used so that you can quickly create and edit a data block without waiting for the request to run. When you are back online, the *Refresh data block* command or *Refresh all data blocks* command refreshes the data blocks that you created with actual data.

To enable off-line mode

1. Click the **[!UICONTROL Settings]** icon.

1. Select **[!UICONTROL Enable off-line mod]e**.

1. Enter a positive integer in the **[!UICONTROL Display metric data as]** field.

1. Click **[!UICONTROL Apply]**.

## Language

You can choose the language for the Report Builder UI. All supported Adobe Analytics languages are available.

To select the language used in the Report Builder UI

 1. Click Settings.

 1. Select a language from the **[!UICONTROL Language]** drop down menu.

     ![Report Builder date range pane showing the Language list with English selected.](./assets/image39.png)

 1. Click **[!UICONTROL Apply].**

## Troubleshooting

Use the Troubleshooting setting to log all client/server data to a local file. Use this option to help resolve support tickets.

To enable the Troubleshooting option, select **[!UICONTROL Log report builder data block to web console]**.
-->