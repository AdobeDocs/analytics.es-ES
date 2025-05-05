---
description: Una depuración le permite limitar los componentes antes de compartir un proyecto.
keywords: Revisión de Analysis Workspace
title: Depurar proyectos de
feature: Curate and Share
role: User, Admin
exl-id: 5e23be83-586a-4543-9be9-65c631b8b0b7
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 98%

---

# Depurar proyectos de

La depuración permite limitar los componentes (dimensiones, métricas, segmentos e intervalos de fechas) antes de compartir un proyecto. Cuando un destinatario abre el proyecto, verá un conjunto limitado de componentes que ha seleccionado para ellos. La depuración es un paso opcional pero recomendado antes de compartir un proyecto.

>[!NOTE]
> Los perfiles de productos son el mecanismo principal que controla los componentes que puede ver un usuario. Se administran a través de Admin Console en Adobe Experience Cloud. La depuración es un filtro secundario.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Depurar proyectos](https://video.tv.adobe.com/v/328104?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Aplicar depuración de proyecto

1. Haga clic en **[!UICONTROL Compartir]** > **[!UICONTROL Depurar datos del proyecto]**.
Los componentes que se utilizan en el proyecto se añadirán automáticamente.
   **Nota**: Si un proyecto tiene varios grupos de informes, verá un campo de selección para cada grupo de informes en el proyecto.
1. (Opcional) Para agregar más componentes, arrastre los componentes que desee compartir desde el carril izquierdo al campo [!UICONTROL Depurar componentes].
1. Haga clic en **[!UICONTROL Finalizado]**.

La depuración también se puede aplicar desde el menú [!UICONTROL Compartir] haciendo clic en **[!UICONTROL Depurar y Compartir]**. Esta opción depura automáticamente el proyecto en los componentes que se utilizan en el proyecto. Puede agregar componentes adicionales siguiendo los pasos anteriores.

![](assets/curation-field.png)

## Vista de un proyecto depurado

Cuando un destinatario abre un proyecto depurado, solo verá el conjunto depurado de componentes que haya definido:

![](assets/curate-project.png)

## Eliminar depuración del proyecto

Para eliminar la depuración del proyecto y restaurar el conjunto completo de componentes en el carril izquierdo:

1. Haga clic en **[!UICONTROL Compartir]** > **[!UICONTROL Depurar datos del proyecto]**.
1. Haga clic en **[!UICONTROL Eliminar depuración]**.
1. Haga clic en **[!UICONTROL Finalizado]**.

## Depuración del grupo de informes virtuales

Para aplicar la depuración a nivel de grupo de informes, de modo que se aplique a muchos proyectos a la vez, puede [depurar componentes en un grupo de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-components.html?lang=es).

>[!NOTE]
> La depuración de grupos de informes virtuales siempre se aplica antes de la depuración de proyectos. Esto significa que, aunque el proyecto depurado incluya determinados componentes, se filtrarán si los grupos de informes virtuales depurados no los incluyen.

## Opción Mostrar todos los componentes

En un proyecto depurado o grupo de informes virtual, el destinatario tendrá la opción de **[!UICONTROL Mostrar todos]** los componentes en el carril izquierdo. [!UICONTROL Mostrar todo] revela diferentes conjuntos de componentes, según:

* Nivel de permiso del usuario (administrador o no administrador)
* Función del proyecto (propietario/editor o no)
* Tipo de depuración aplicada (grupo de informes virtual o proyecto)
* Componentes propiedad del usuario o que el usuario ha compartido. Entre los componentes propios o compartidos se incluyen los segmentos, las métricas calculadas y los intervalos de fechas. No incluyen componentes implementados como, por ejemplo, eVars, props y eventos personalizados.

Nota: Las funciones de vista que no son de administración no tendrán acceso al carril izquierdo del proyecto, por lo que se han omitido de la tabla siguiente.

| Tipo de depuración | Administradores | Propietario del proyecto no administrador o función de edición | Función duplicada no perteneciente a administración |
|---|---|---|---|
| Grupo de informes virtuales depurado | Todos los componentes no depurados del grupo de informes virtuales | Componentes de grupo de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función | Componentes de grupo de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función |
| Proyecto depurado | Todos los componentes de proyecto no depurados | Todos los componentes de proyecto no depurados | Componentes de proyecto no depurados que pertenecen a esta función o que se compartieron con esta función |
| Proyecto depurado en un grupo de informes virtuales depurado | Todos los componentes no depurados, mostrados bajo **[!UICONTROL Componentes de proyecto no depurados]** y **[!UICONTROL Componentes de grupos de informes virtuales no depurados]** | Todos los componentes no depurados del proyecto Y los componentes no depurados del grupo de informes virtuales que pertenezcan a esta función o que hayan sido compartidos con ellos | Grupo de informes virtuales y componentes de proyecto no depurados que pertenecen a esta función o que han sido compartidos con ellos |
