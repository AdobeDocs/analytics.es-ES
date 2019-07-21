---
title: Depuración de proyectos y grupos de informes virtuales
seo-title: Depurar proyectos y grupos de informes virtuales en Analysis Workspace
description: Aprenda a depurar los componentes y proyectos de vrs
seo-description: Depurar VRS y depurar proyectos
translation-type: tm+mt
source-git-commit: 0b56838e966aaf4cfa5c2685dd8335adbbbf11a7

---


# Depuración de proyectos y grupos de informes virtuales

Al depurar proyectos o grupos de informes virtuales, básicamente se filtran los componentes para que la audiencia solo vea esos componentes de proyecto o grupo de informes virtuales (dimensiones, métricas, segmentos e intervalos de fechas) que usted quiera que use.

>[!Note]
>Los permisos de componentes son el mecanismo principal que rige los componentes que un usuario puede ver. Se administran mediante las Herramientas de administración. La depuración es un filtro secundario.

Recientemente, hemos mejorado la experiencia de depuración. Aquí encontrará información general del contenido que se muestra con el botón **[!UICONTROL Mostrar todo]además de los componentes depurados ya disponibles, en diferentes experiencias depuradas y por nivel de permisos:**

| Tipo de depuración | Administradores | Propietarios de proyecto que no son administradores | No administradores |
|---|---|---|---|
| Grupos de informes virtuales depurados | Todos los componentes de grupos de informes virtuales no depurados | Componentes de grupos de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función | Componentes de grupos de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función |
| Proyecto depurado | Todos los componentes de proyecto no depurados | Todos los componentes de proyecto no depurados | Componentes de proyecto no depurados que pertenecen a esta función o que se compartieron con esta función |
| Proyecto depurado en un grupo de informes virtuales depurado | Todos los componentes no depurados siguientes: **[Componentes del proyecto no depurados UICONTROL]** y **[componentes de VRS no depurados de UICONTROL]** | Todos los componentes del proyecto NO depurados y los componentes de VRS no depurados que posee esta función o que se han compartido con ellos | Componentes de proyecto y de grupo de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función |

>[!IMPORTANT]
>La depuración de VRS siempre se aplica antes de la depuración del proyecto, por lo que aunque el proyecto depurado incluya determinados componentes, se filtrarán si el VRS depurado no los incluye.
