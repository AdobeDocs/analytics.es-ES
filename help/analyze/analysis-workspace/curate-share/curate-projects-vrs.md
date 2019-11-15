---
title: Depuración de proyectos y grupos de informes virtuales
description: Obtenga información sobre cómo depurar componentes y proyectos de vrs
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Depuración de proyectos y grupos de informes virtuales

Al depurar proyectos o grupos de informes virtuales, básicamente se filtran los componentes para que la audiencia solo vea esos componentes de proyecto o grupo de informes virtuales (dimensiones, métricas, segmentos e intervalos de fechas) que usted quiera que use.

>[!Note]
>Los permisos de componentes son el mecanismo principal que rige los componentes que puede ver un usuario. Se administran a través de las Herramientas de administración. La depuración es un filtro secundario.

Recientemente, hemos mejorado la experiencia de depuración. Aquí encontrará información general del contenido que se muestra con el botón **[!UICONTROL Mostrar todo]además de los componentes depurados ya disponibles, en diferentes experiencias depuradas y por nivel de permisos:**

| Tipo de depuración | Administradores | Propietarios de proyecto que no son administradores | No administradores |
|---|---|---|---|
| Grupos de informes virtuales depurados | Todos los componentes de grupos de informes virtuales no depurados | Componentes de grupos de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función | Componentes de grupos de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función |
| Proyecto depurado | Todos los componentes de proyecto no depurados | Todos los componentes de proyecto no depurados | Componentes de proyecto no depurados que pertenecen a esta función o que se compartieron con esta función |
| Proyecto depurado en un grupo de informes virtuales depurado | Todos los componentes no depurados siguientes: Componentes **[de proyecto no depurados]** UICONTROL y componentes de VRS no depurados **[UICONTROL]** | Todos los componentes de proyecto sin depurar Y los componentes de VRS sin depurar que esta función posee o que se han compartido con ellos | Componentes de proyecto y de grupo de informes virtuales no depurados que pertenecen a esta función o que se compartieron con esta función |

>[!IMPORTANT]
>La curación del VRS siempre se aplica antes de la curación del proyecto, por lo que incluso si el proyecto depurado incluye determinados componentes, se filtrarán si el VRS conservado no los incluye.
