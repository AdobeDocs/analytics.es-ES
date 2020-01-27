---
title: Depuración de proyectos y grupos de informes virtuales
description: Obtenga información sobre cómo depurar componentes VRS y proyectos
translation-type: tm+mt
source-git-commit: 02f9106d7b8b42c1aca46682736b94f5cde519ef

---


# Depuración de proyectos y grupos de informes virtuales

Al depurar proyectos o grupos de informes virtuales, básicamente se filtran los componentes para que la audiencia solo vea esos componentes de proyecto o grupo de informes virtuales (dimensiones, métricas, segmentos e intervalos de fechas) que usted quiera que use.

>[!Note]
>
>Los perfiles de producto son el mecanismo principal que rige los componentes que puede ver un usuario. They are managed through the [Admin Console](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html#createproductprofiles). La depuración es un filtro secundario.

Recientemente, hemos mejorado la experiencia de depuración. Aquí encontrará información general del contenido que se muestra con el botón **[!UICONTROL Mostrar todo]**además de los componentes depurados ya disponibles, en diferentes experiencias depuradas y por nivel de permisos:

| Tipo de depuración | Administradores | Propietarios de proyecto que no son administradores | No administradores |
|---|---|---|---|
| Grupos de informes virtuales depurados | Todos los componentes de grupos de informes virtuales no depurados | Componentes de grupos de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función | Componentes de grupos de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función |
| Proyecto depurado | Todos los componentes de proyecto no depurados | Todos los componentes de proyecto no depurados | Componentes de proyecto no depurados que pertenecen a esta función o que se compartieron con esta función |
| Proyecto depurado en un grupo de informes virtuales depurado | Todos los componentes no depurados siguientes: **[!UICONTROL Non-Curated Project Components]**and**[!UICONTROL  Non-Curated VRS Components]** | Todos los componentes de proyecto sin depurar y los componentes VRS sin depurar de esta función o que se han compartido con ellos | Componentes de proyecto y de grupo de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función |

>[!IMPORTANT]
>
>La curación del VRS siempre se aplica antes de la curación del proyecto. Esto significa que, aunque el proyecto depurado incluya determinados componentes, se filtrarán si el VRS depurado no los incluye.
