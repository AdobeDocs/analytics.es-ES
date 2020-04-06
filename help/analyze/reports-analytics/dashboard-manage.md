---
description: Utilice el administrador de paneles para copiar, compartir, archivar y programar tableros para su envío.
subtopic: Dashboards
title: Administrador de tableros
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Administrador de tableros

Utilice el administrador de paneles para copiar, compartir, archivar y programar tableros para su envío.

>[!IMPORTANT]
>
>La práctica recomendada al utilizar el administrador de paneles es no tener más de 300 paneles para un solo usuario. Además, tenga en cuenta que el administrador carga todos los paneles compartidos a continuación, por lo que debe ser prudente al compartir los paneles.

## Administrador de tableros

Utilice el administrador de paneles para copiar, compartir, archivar y programar tableros para su envío.

Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.

| Elemento | Descripción |
|--- |--- |
| Compartido | Muestra si se comparte el panel. |
| Programado | Permite programar el panel para el envío. |
| Ver archivo | Esta funcionalidad ya no está disponible. |
| Insertar en escritorio de usuarios | Permite compartir un panel. |
| Administrar | Permite editar, copiar y eliminar un panel. |

## Administrar paneles compartidos

Instrucciones sobre cómo utilizar las opciones de administración de paneles compartidos.

1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.
1. Under [!UICONTROL Shared Dashboards], locate the shared dashboard (or legacy dashboard) you want to manage and choose one or more of the following options:

<table id="choicetable_857E0E816D63404683D4E24DC8D7FC69"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> Opción </th> 
  <th class="chdeschd"> Descripción </th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Ver archivo</strong></td> 
  <td class="chdesc stentry"> Esta funcionalidad ya no está disponible. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Dashboard Player</strong></td> 
  <td class="chdesc stentry"> <p>Los servidores de SiteCatalyst 14 ya no responderán a las solicitudes de datos de Panel Player. Se puede acceder a todos los paneles que se estén mostrando en Panel Player en la interfaz estándar de Informes y análisis o se pueden volver a crear como Paneles en tiempo real. Los paneles en tiempo real están diseñados específicamente para una visualización continua e incluyen un modo de pantalla completa que permite la visualización en televisores u otros dispositivos de pantalla grande. </p> <p>Se requiere la acción del usuario: Debe interrumpir el uso de Panel Player. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Cópieme</strong></td> 
  <td class="chdesc stentry"> Añade una copia a la lista de paneles, utilizando el mismo nombre que el original. Sin embargo, no puede ver ninguna actualización o cambio realizado por el propietario del panel. Al copiar un panel heredado, se abre un panel en blanco, en el que puede agregar contenido heredado. <p>Importante: Si los usuarios compartidos de su tablero no pueden ver los cambios realizados en el tablero, controle el Administrador de tableros para ver si los usuarios han elegido la opción <span class="uicontrol">Cópieme</span>. Si lo han hecho, no pueden ver actualizaciones ni cambios realizados por usted. Para ver todos los cambios y todas las actualizaciones, los usuarios compartidos deben seleccionar la opción <span class="uicontrol">En el menú</span> en el Administrador de tableros. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>En el menú</strong></td> 
  <td class="chdesc stentry"> Le permite ver los cambios/actualizaciones realizados por el propietario del tablero. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Dejar de compartir</strong></td> 
  <td class="chdesc stentry"> Elimina el tablero de su lista de tableros compartidos. </td> 
 </tr> 
</table>

## Migración de un panel heredado

Los paneles heredados existentes se seguirán ejecutando y aún podrá editarlos, descargarlos y programarlos; sin embargo, ya no puede crear nuevos paneles heredados. Se le recomienda encarecidamente que actualice los paneles heredados existentes al formato de panel más reciente.

>[!NOTE]Más adelante, considere la posibilidad de usar los [proyectos de Analysis Workspace](https://marketing.adobe.com/resources/help/es_ES/analytics/analysis-workspace/) y su capacidad para poder descargarlos y programarlos.

Al copiar el panel preexistente, el sistema abre el panel preexistente para su edición, donde puede agregar contenido preexistente o nuevo. Al copiar un panel heredado, el original se conserva en la lista de paneles heredados.

>[!NOTE] Añadir contenido heredado a un panel crea un panel basado en la funcionalidad de panel más reciente. Sin embargo, el informe breve preexistente puede contener datos basados en la plataforma de datos anterior.

**Para migrar un panel heredado de la versión 14.x**

1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. En la [!UICONTROL Manage] columna, en [!UICONTROL Legacy Dashboards], haga clic en **[!UICONTROL Copy to New Dashboard]**.

   El panel copiado se abre en el editor de diseño de panel.

   See [Editing Dashboard and Reportlet Data](/help/analyze/reports-analytics/dashboard.md).

## Compartir un panel

Instrucciones sobre cómo un administrador puede compartir (o insertar) un panel en varios usuarios. Al insertar paneles en el menú de los usuarios, los paneles pasan a estar disponibles en el [!UICONTROL Shared Dashboards] menú del usuario.

1. En el [!UICONTROL Dashboard Manager], localice el panel y, a continuación, habilite **[!UICONTROL Shared]**.
1. Haga clic **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. En la [!UICONTROL Push Dashboard] página, seleccione los usuarios de destinatario o haga clic en **[!UICONTROL Check All]**.
1. Haga clic en **[!UICONTROL Save]**.

If shared users of your dashboard cannot see changes you made in the dashboard, check your Dashboard Manager to see if the users have chosen the **[!UICONTROL Copy Me]** option. Si lo han hecho, no pueden ver actualizaciones ni cambios realizados por usted. To see all the changes/updates, shared users need to select the **[!UICONTROL On Menu]** option in the Dashboard Manager.

## Programar un panel para envío

En la [!UICONTROL Dashboard Manager], puede ver si un panel está programado para el envío y editar la programación. Las opciones de envío de panel son idénticas a las opciones de envío de informes.

1. Abra un tablero.
1. Haga clic **[!UICONTROL More]** > **[!UICONTROL Send]**.

   Consulte [Programación y distribución](/help/analyze/reports-analytics/scheduling.md) para obtener más información.

## Archivar un tablero

>[!NOTE] Esta funcionalidad ya no estará disponible en enero de 2020.

Instrucciones sobre cómo archivar cualquier panel enviado como archivo PDF. El sistema almacena el archivo archivado durante dos años o hasta que se alcance un límite máximo de 4 GB de informes archivados, lo que suceda primero.

1. Abra un tablero.
1. Haga clic **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. En el [!UICONTROL Email Report] grupo, habilite **[!UICONTROL Archive]**.
1. Specify delivery options, then click **[!UICONTROL Send]**.

   Puede vista de paneles archivados en el Administrador de Paneles. También puede abrir un panel y hacer clic en **[!UICONTROL More]** > **[!UICONTROL View Archive]**.
