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
| Compartido | Indica si el tablero se está compartiendo. |
| Programado | Permite programar el tablero para su envío. |
| Ver archivo | Esta funcionalidad ya no está disponible. |
| Insertar en escritorio de usuarios | Permite compartir un tablero. |
| Administrar | Permite editar, copiar y eliminar un tablero. |

## Administrar tableros compartidos

Los pasos describen cómo usar las opciones de administración del tablero compartido.

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
  <td class="chdesc stentry"> <p>Los servidores SiteCatalyst 14 dejarán de responder a las solicitudes de datos de Dashboard Player. Se puede acceder a cualquiera de los tableros que se muestre en Dashboard Player en la interfaz estándar de Reports &amp; Analytics, o bien se pueden volver a crear como un panel de control en tiempo real. Panel de control en tiempo real se han diseñado específicamente para que puedan visualizarse ininterrumpidamente e incluyen un modo de pantalla completa para que se puedan visualizar en TV u otros dispositivos de pantalla grande. </p> <p>Medida que debe tomar el usuario: debe dejar de usar Dashboard Player. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Cópieme</strong></td> 
  <td class="chdesc stentry"> Añade una copia a su lista de tableros, utilizando el mismo nombre que el original. Sin embargo, no puede ver actualizaciones ni cambios realizados por el propietario del tablero. Al copiar un tablero preexistente se abre un tablero en blanco, en el que puede agregar contenido preexistente. <p>Importante: Si los usuarios compartidos de su tablero no pueden ver los cambios realizados en el tablero, controle el Administrador de tableros para ver si los usuarios han elegido la opción <span class="uicontrol">Cópieme</span>. Si lo han hecho, no pueden ver actualizaciones ni cambios realizados por usted. Para ver todos los cambios y todas las actualizaciones, los usuarios compartidos deben seleccionar la opción <span class="uicontrol">En el menú</span> en el Administrador de tableros. </p> </td> 
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

## Migración de tableros preexistentes

Los tableros preexistentes actuales se seguirán ejecutando y aún podrá editarlos, descargarlos y programarlos, pero ya no podrá crear nuevos tableros preexistentes. Se le recomienda encarecidamente que actualice los tableros preexistentes actuales al formato de tablero más reciente.

>[!NOTE]Más adelante, considere la posibilidad de usar los [proyectos de Analysis Workspace](https://marketing.adobe.com/resources/help/es_ES/analytics/analysis-workspace/) y su capacidad para poder descargarlos y programarlos.

Cuando copia el tablero preexistente, el sistema lo abre para editarlo y ahí puede añadir contenido preexistente o nuevo. Al copiar un tablero preexistente, el original se conserva en la lista de tableros preexistentes.

>[!NOTE] Añadir contenido heredado a un panel crea un panel basado en la funcionalidad de panel más reciente. Sin embargo, el informe breve preexistente podría contener datos que estuvieran basados en la plataforma de datos anterior.

**Para migrar un tablero preexistente de la versión 14.x a**

1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. En la [!UICONTROL Manage] columna, en [!UICONTROL Legacy Dashboards], haga clic en **[!UICONTROL Copy to New Dashboard]**.

   El tablero copiado se abre en el editor de diseño de tablero.

   Consulte [Edición de datos de informes breves y tableros](/help/analyze/reports-analytics/dashboard.md).

## Compartir un tablero

Instrucciones sobre cómo un administrador puede compartir un tablero con varios usuarios (o insertarlo en sus escritorios). When you push dashboards to users, the dashboards become available in user&#39;s [!UICONTROL Shared Dashboards] menu.

1. En el [!UICONTROL Dashboard Manager], localice el panel y, a continuación, habilite **[!UICONTROL Shared]**.
1. Haga clic **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. En la [!UICONTROL Push Dashboard] página, seleccione los usuarios de destinatario o haga clic en **[!UICONTROL Check All]**.
1. Haga clic en **[!UICONTROL Save]**.

If shared users of your dashboard cannot see changes you made in the dashboard, check your Dashboard Manager to see if the users have chosen the **[!UICONTROL Copy Me]** option. Si lo han hecho, no pueden ver actualizaciones ni cambios realizados por usted. To see all the changes/updates, shared users need to select the **[!UICONTROL On Menu]** option in the Dashboard Manager.

## Programar un tablero para su envío

In the [!UICONTROL Dashboard Manager], you can see whether a dashboard is scheduled for delivery, and edit the schedule. Las opciones de envío de tableros son idénticas a las opciones de envío de informes.

1. Abra un tablero.
1. Haga clic **[!UICONTROL More]** > **[!UICONTROL Send]**.

   Consulte [Programación y distribución](/help/analyze/reports-analytics/scheduling.md) para obtener más información.

## Archivar un tablero

>[!NOTE] Esta funcionalidad ya no estará disponible en enero de 2020.

Instrucciones sobre cómo archivar cualquier tablero enviado como archivo PDF. El sistema almacena el archivo archivado durante dos años o hasta que llegue al límite máximo de 4 GB de informes archivados, lo que suceda primero.

1. Abra un tablero.
1. Haga clic **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. En el [!UICONTROL Email Report] grupo, habilite **[!UICONTROL Archive]**.
1. Specify delivery options, then click **[!UICONTROL Send]**.

   Puede ver los tableros archivados en el administrador de tableros. También puede abrir un panel y hacer clic en **[!UICONTROL More]** > **[!UICONTROL View Archive]**.
