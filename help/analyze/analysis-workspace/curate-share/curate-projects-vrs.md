---
title: Depuración de proyectos y grupos de informes virtuales
description: Obtenga información sobre cómo depurar componentes VRS y proyectos
translation-type: tm+mt
source-git-commit: db983980a6ec3db4d60bbc8fc3ba57a4e1219287

---


# Depuración de proyectos y grupos de informes virtuales

Al depurar proyectos o grupos de informes virtuales, básicamente se filtran los componentes para que la audiencia solo vea esos componentes de proyecto o grupo de informes virtuales (dimensiones, métricas, segmentos e intervalos de fechas) que usted quiera que use.

>[!NOTE]
>
>Los perfiles de productos son el mecanismo principal que controla los componentes que puede ver un usuario. Se administran mediante [Admin Console](https://helpx.adobe.com/es/enterprise/using/manage-products-and-profiles.html#createproductprofiles). La depuración es un filtro secundario.

Recientemente, hemos mejorado la experiencia de depuración. Here is an overview of what the **[!UICONTROL Show All]** button reveals, in addition to the curated components already available, in different curated experiences and by permission level:

| Tipo de depuración | Administradores | Propietarios de proyecto que no son administradores | No administradores |
|---|---|---|---|
| Grupos de informes virtuales depurados | Todos los componentes de grupos de informes virtuales no depurados | Componentes de grupos de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función | Componentes de grupos de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función |
| Proyecto depurado | Todos los componentes de proyecto no depurados | Todos los componentes de proyecto no depurados | Componentes de proyecto no depurados que pertenecen a esta función o que se compartieron con esta función |
| Proyecto depurado en un grupo de informes virtuales depurado | Todos los componentes no depurados siguientes:  **[!UICONTROL Non-Curated Project Components]** y **[!UICONTROL Non-Curated VRS Components]** | Todos los componentes de proyecto sin depurar y los componentes VRS sin depurar de esta función o que se han compartido con ellos | Componentes de proyecto y de grupo de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función |

>[!IMPORTANT]
>
>La depuración de grupos de informes virtuales siempre se aplica antes de la depuración de proyectos. Esto significa que, aunque el proyecto depurado incluya determinados componentes, se filtrarán si los grupos de informes virtuales depurados no los incluyen.
