---
description: Utilice el administrador de paneles para copiar, compartir, archivar y programar tableros para su envío.
subtopic: Dashboards
title: Administrador de tableros
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
feature: Reports & Analytics Basics
role: User, Admin
exl-id: abd5acf5-f743-4c94-81fb-fc6cc69e8f26
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 94%

---

# Administrador de tableros

{{ra-eol}}

Utilice el administrador de paneles para copiar, compartir, archivar y programar tableros para su envío.

>[!IMPORTANT]
>
>La práctica recomendada al utilizar el administrador de paneles es no tener más de 300 paneles para un solo usuario. Además, tenga en cuenta que el administrador carga todos los paneles compartidos a continuación, por lo que debe ser prudente al compartir los paneles.

Clic **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Todos los componentes]** > **[!UICONTROL Paneles]**.

| Elemento | Descripción |
|--- |--- |
| Compartido | Indica si el tablero se está compartiendo. |
| Programado | Permite programar el tablero para su envío. |
| Ver archivo | Esta funcionalidad ya no se encuentra disponible. |
| Insertar en escritorio de usuarios | Permite compartir un tablero. |
| Administrar | Permite editar, copiar y eliminar un tablero. |

## Administrar tableros compartidos

Para administrar paneles compartidos:

1. Ir a **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Todos los componentes]** > **[!UICONTROL Paneles]**.
1. En [!UICONTROL Tableros compartidos], localice el tablero compartido (o tablero preexistente) que desee administrar y elija una o más de las siguientes opciones:

<table id="choicetable_857E0E816D63404683D4E24DC8D7FC69"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> Opción </th> 
  <th class="chdeschd"> Descripción </th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Ver archivo</strong></td> 
  <td class="chdesc stentry"> Esta funcionalidad ya no se encuentra disponible. </td> 
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

>[!NOTE]
>
>Más adelante, considere la posibilidad de usar los [proyectos de Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es) y su capacidad para poder descargarlos y programarlos.

Cuando copia el tablero preexistente, el sistema lo abre para editarlo y ahí puede añadir contenido preexistente o nuevo. Al copiar un tablero preexistente, el original se conserva en la lista de tableros preexistentes.

>[!NOTE]
>
>Añadir contenido heredado a un panel crea un panel basado en la funcionalidad de panel más reciente. Sin embargo, el informe breve preexistente podría contener datos que estuvieran basados en la plataforma de datos anterior.

**Para migrar un tablero preexistente de la versión 14.x a**

1. Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Administrar tableros]**.
1. En la columna [!UICONTROL Administrar], en [!UICONTROL Tableros preexistentes], haga clic en **[!UICONTROL Copiar a nuevo tablero]**.

   El tablero copiado se abre en el editor de diseño de tablero.

   Consulte [Edición de datos de informes breves y tableros](/help/analyze/reports-analytics/dashboard.md).

## Compartir un tablero

Los administradores de Analytics pueden compartir un tablero con varios usuarios (o insertarlo). Al insertar los tableros en el escritorio de los usuarios, esos tableros pasan a estar disponibles en el menú [!UICONTROL Tableros compartidos] del usuario.

Para compartir un tablero con varios usuarios:

1. En el [!UICONTROL Administrador de tableros], busque el tablero y, a continuación, active **[!UICONTROL Compartido]**.
1. Haga clic en **[!UICONTROL Insertar en escritorio de usuarios]**.  ![](assets/push.png)

1. En la página [!UICONTROL Insertar tablero], seleccione los usuarios objetivo o haga clic en **[!UICONTROL Marcar todos]**.
1. Haga clic en **[!UICONTROL Guardar]**.

Si los usuarios compartidos de su tablero no pueden ver los cambios realizados en el tablero, controle el Administrador de tableros para ver si los usuarios han elegido la opción **[!UICONTROL Cópieme]**. Si lo han hecho, no pueden ver actualizaciones ni cambios realizados por usted. Para ver todos los cambios y todas las actualizaciones, los usuarios compartidos deben seleccionar la opción **[!UICONTROL En el menú]** en el Administrador de tableros.

## Programar un tablero para su envío

En el [!UICONTROL Administrador de tableros], puede ver si un tablero está programado para su envío y editar la programación. Las opciones de envío de tableros son idénticas a las opciones de envío de informes.

1. Abra un tablero.
1. Haga clic en **[!UICONTROL Más]** > **[!UICONTROL Enviar]**.

   Consulte [Programación y distribución](/help/analyze/reports-analytics/scheduling.md) para obtener más información.
