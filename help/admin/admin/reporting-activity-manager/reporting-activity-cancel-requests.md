---
description: Obtenga más información sobre cómo utilizar el Administrador de actividades de creación de informes para diagnosticar y corregir problemas de capacidad durante las horas de mayor actividad en la creación de informes.
title: Cancelar solicitudes de creación de informes en el Administrador de actividades de creación de informes
feature: Admin Tools
source-git-commit: 743bd30f8606b05d799f9089d2f14863fcb18feb
workflow-type: tm+mt
source-wordcount: '1417'
ht-degree: 15%

---

# Cancelar solicitudes de creación de informes en el Administrador de actividades de creación de informes

El [!UICONTROL Administrador de actividades de informes] permite a los administradores diagnosticar y cancelar rápidamente las solicitudes de creación de informes a fin de corregir los problemas de capacidad de creación de informes durante las horas de mayor actividad en la creación de informes.

Tenga en cuenta lo siguiente al cancelar las solicitudes de creación de informes:

* Puede cancelar solicitudes específicas, cancelar todas las solicitudes de un usuario específico o cancelar todas las solicitudes relacionadas con un proyecto específico.

  Cuando cancela una solicitud, la acción se registra en el [Registros](/help/admin/admin/logs.md). El [!UICONTROL **Tipo de evento**] se muestra como [!UICONTROL **Acción de administrador**], y una descripción de la cancelación está disponible en la [!UICONTROL **Evento**] columna.

* Al cancelar las solicitudes, también puede optar por restringir las solicitudes posteriores durante un período de tiempo determinado.

  Cuando restringe una solicitud posterior, la acción se registra en la variable [Registros](/help/admin/admin/logs.md). El [!UICONTROL **Tipo de evento**] se muestra como [!UICONTROL **Acción de administrador**], y una descripción de la restricción está disponible en la [!UICONTROL **Evento**] columna.

* No puede cancelar una solicitud si [!UICONTROL **Usuario**] de una solicitud se muestra como [!UICONTROL **No reconocido**]. Cuando esto sucede, significa que el usuario se encuentra en una empresa de inicio de sesión en la que no tiene permisos administrativos.

Para obtener más información sobre el Administrador de actividades de creación de informes, incluidas las ventajas clave y los requisitos de permisos, consulte [Información general del Administrador de actividades de creación de informes](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Cancelar solicitudes específicas

Puede cancelar solicitudes individuales que consuman una gran cantidad de capacidad de creación de informes.

1. En Adobe Analytics, vaya a **[!UICONTROL Administrador]** > **[!UICONTROL Administrador de actividades de informes]**.

1. Seleccione el grupo de informes donde desea cancelar las solicitudes de creación de informes. <!--double-check this step-->

   Para obtener más información sobre los datos disponibles en esta página, consulte [Ver la actividad de creación de informes en el Administrador de actividades de informes](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Seleccione el [!UICONTROL **Solicitudes**] y, a continuación, seleccione una o varias solicitudes.

   <!-- add screenshot -->

1. Seleccionar [!UICONTROL **Cancelar solicitudes**].

   El [!UICONTROL **Cancelar _x_ solicitudes de informe**] aparece el cuadro de diálogo.

1. El campo Cancelación muestra el mensaje que se muestra a los usuarios cuando se cancelan sus solicitudes. Se proporciona un mensaje predeterminado. Puede actualizar el mensaje predeterminado para proporcionar detalles adicionales.

1. (Opcional) Para restringir solicitudes futuras durante un período de tiempo determinado:

   1. Active la opción para lo siguiente [!UICONTROL **Restringir solicitudes posteriores**]

      ![Restringir las solicitudes posteriores](assets/restrict-subsequent-requests.png)

   1. Elija entre las siguientes opciones:

      | Opción | Función |
      |---------|----------|
      | [!UICONTROL **Usuario y proyecto**] | Los usuarios asociados a las solicitudes seleccionadas tendrán restringida temporalmente la ejecución de solicitudes de creación de informes para los proyectos asociados. |
      | [!UICONTROL **Usuario**] | A los usuarios asociados a las solicitudes seleccionadas se les restringirá temporalmente la realización de solicitudes de creación de informes. |
      | [!UICONTROL **Proyecto**] | Los proyectos asociados a las solicitudes seleccionadas quedarán temporalmente restringidos de todas las solicitudes de creación de informes. |
      | [!UICONTROL **Restringido para**] | Elija cuánto tiempo se restringirán las solicitudes. Puede elegir 1 minuto (predeterminado), 5 minutos, 10 minutos, 15 minutos o 30 minutos. <!-- double-check this --><p>Una restricción no se puede eliminar antes de que se haya establecido.</p> |

      {style="table-layout:auto"}

1. Seleccionar [!UICONTROL **Continuar con la cancelación**].

   Se muestra una notificación en Analysis Workspace que informa a los usuarios de que se ha cancelado la solicitud. Para obtener más información sobre cómo aparece esto en Analysis Workspace, consulte [Experiencia cuando los usuarios acceden a un informe cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitudes de usuario

Puede cancelar todas las solicitudes que estén asociadas con uno o más usuarios.

1. En Adobe Analytics, vaya a **[!UICONTROL Administrador]** > **[!UICONTROL Administrador de actividades de informes]**.

1. Seleccione el grupo de informes donde desea cancelar las solicitudes de creación de informes. <!--double-check this step-->

   Para obtener más información sobre los datos disponibles en esta página, consulte [Ver la actividad de creación de informes en el Administrador de actividades de informes](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Seleccione el [!UICONTROL **Usuarios**] y, a continuación, seleccione uno o varios usuarios.

   <!-- add screenshot -->

1. Seleccionar [!UICONTROL **Cancelar solicitudes**].

   El [!UICONTROL **Cancelar _x_ solicitudes de informes de usuarios x**] aparece el cuadro de diálogo.

1. El campo Cancelación muestra el mensaje que se muestra a los usuarios cuando se cancelan sus solicitudes. Se proporciona un mensaje predeterminado. Puede actualizar el mensaje predeterminado para proporcionar detalles adicionales.

1. (Opcional) Para restringir solicitudes futuras durante un período de tiempo determinado:

   1. Active la opción para lo siguiente [!UICONTROL **Restringir solicitudes posteriores**].

      ![Restringir solicitudes posteriores por usuario](assets/restrict-subsequent-requests-user.png)

   1. Elija entre las siguientes opciones:

      | Opción | Función |
      |---------|----------|
      | [!UICONTROL **Usuario y proyecto**] | Se restringirá temporalmente a los usuarios seleccionados la posibilidad de realizar solicitudes de creación de informes para los proyectos asociados. |
      | [!UICONTROL **Usuario**] | Se restringirá temporalmente a los usuarios seleccionados la posibilidad de solicitar la creación de informes. |
      | [!UICONTROL **Proyecto**] | Los proyectos asociados a los usuarios seleccionados estarán restringidos a cualquier solicitud de creación de informes realizada por cualquier usuario. |
      | [!UICONTROL **Restringido para**] | Elija cuánto tiempo se restringirán las solicitudes. Puede elegir 1 minuto (predeterminado), 5 minutos, 10 minutos, 15 minutos o 30 minutos. <!--double-check this--> <p>Una restricción no se puede eliminar antes de que se haya establecido.</p> |

      {style="table-layout:auto"}

1. Seleccionar [!UICONTROL **Continuar con la cancelación**].

   Se muestra una notificación en Analysis Workspace que informa a los usuarios de que se ha cancelado la solicitud. Para obtener más información sobre cómo aparece esto en Analysis Workspace, consulte [Experiencia cuando los usuarios acceden a un informe cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitudes por proyecto

Puede cancelar todas las solicitudes que estén asociadas con uno o más proyectos.

1. En Adobe Analytics, vaya a **[!UICONTROL Administrador]** > **[!UICONTROL Administrador de actividades de informes]**.

1. Seleccione el grupo de informes donde desea cancelar las solicitudes de creación de informes. <!--double-check this step-->

   Para obtener más información sobre los datos disponibles en esta página, consulte [Ver la actividad de creación de informes en el Administrador de actividades de informes](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Seleccione el [!UICONTROL **Proyectos**] y, a continuación, seleccione uno o varios proyectos.

   <!-- add screenshot -->

1. Seleccionar [!UICONTROL **Cancelar solicitudes**].

   El [!UICONTROL **Cancelar _x_ solicitudes de informes de x proyectos**] aparece el cuadro de diálogo.

1. El campo Cancelación muestra el mensaje que se muestra a los usuarios cuando se cancelan sus solicitudes. Se proporciona un mensaje predeterminado. Puede actualizar el mensaje predeterminado para proporcionar detalles adicionales.

1. (Opcional) Para restringir solicitudes futuras durante un período de tiempo determinado:

   1. Active la opción para lo siguiente [!UICONTROL **Restringir solicitudes posteriores**].

      ![Restringir solicitudes posteriores por proyecto](assets/restrict-subsequent-requests-project.png)

   1. Elija entre las siguientes opciones:

      | Opción | Función |
      |---------|----------|
      | [!UICONTROL **Usuario y proyecto**] | Los proyectos seleccionados quedarán temporalmente excluidos de cualquier solicitud de información realizada por los usuarios asociados. |
      | [!UICONTROL **Usuario**] | Se restringirá a los usuarios asociados a los proyectos seleccionados la posibilidad de solicitar la creación de informes. |
      | [!UICONTROL **Proyecto**] | Los proyectos seleccionados se restringirán temporalmente de cualquier solicitud de creación de informes realizada por cualquier usuario. |
      | [!UICONTROL **Restringido para**] | Elija cuánto tiempo se restringirán las solicitudes. Puede elegir 1 minuto (predeterminado), 5 minutos, 10 minutos, 15 minutos o 30 minutos. <!--double-check this--> <p>Una restricción no se puede eliminar antes de que se haya establecido.</p> |

      {style="table-layout:auto"}

1. Seleccionar [!UICONTROL **Continuar con la cancelación**].

   Se muestra una notificación en Analysis Workspace que informa a los usuarios de que se ha cancelado la solicitud. Para obtener más información sobre cómo aparece esto en Analysis Workspace, consulte [Experiencia cuando los usuarios acceden a un informe cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitudes por aplicación

Puede cancelar todas las solicitudes asociadas con una o más aplicaciones. Al cancelar las solicitudes asociadas a una aplicación, puede optar por restringir aún más las solicitudes asociadas a esa aplicación durante un período de tiempo determinado.

Las aplicaciones incluyen lo siguiente:

* IU de Analysis Workspace
* Proyectos programados de Workspace
* Report Builder
* IU del generador: Segmento, Métricas calculadas, Anotaciones, Audiencias, etc.
* Llamadas de API desde la API 1.4 o 2.0
* Alertas inteligentes
* Compartir vínculos con cualquiera
* Cualquier otra aplicación que consulte el motor de informes de Analytics.

Para cancelar solicitudes por aplicación:

1. En Adobe Analytics, vaya a **[!UICONTROL Administrador]** > **[!UICONTROL Administrador de actividades de informes]**.

1. Seleccione la conexión en la que desea cancelar las solicitudes de creación de informes. <!--double-check this step-->

   Para obtener más información sobre los datos disponibles en esta página, consulte [Ver la actividad de creación de informes en el Administrador de actividades de informes](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Seleccione el [!UICONTROL **Aplicaciones**] y, a continuación, seleccione una o varias aplicaciones.

   <!-- add screenshot -->

1. Seleccionar [!UICONTROL **Cancelar solicitudes**].

   El [!UICONTROL **Cancelar _x_ solicitudes de informes de x proyectos**] aparece el cuadro de diálogo.

1. El campo Cancelación muestra el mensaje que se muestra a los usuarios cuando se cancelan sus solicitudes. Se proporciona un mensaje predeterminado. Puede actualizar el mensaje predeterminado para proporcionar detalles adicionales.

1. (Opcional) Para restringir solicitudes futuras durante un período de tiempo determinado:

   1. Active la opción para lo siguiente [!UICONTROL **Restringir solicitudes posteriores**]

      ![Restringir solicitudes posteriores por aplicación](assets/restrict-subsequent-requests-application.png)

   1. Elija entre las siguientes opciones:

      | Opción | Función |
      |---------|----------|
      | [!UICONTROL **Usuario y proyecto**] | Las aplicaciones seleccionadas se restringirán temporalmente de cualquier solicitud de creación de informes realizada por los usuarios y proyectos asociados.<p>Esta es la opción menos restrictiva.</p> |
      | [!UICONTROL **Usuario**] | Los usuarios asociados con las aplicaciones seleccionadas no podrán realizar solicitudes de informes. |
      | [!UICONTROL **Proyecto**] | Los proyectos asociados con las aplicaciones seleccionadas se restringirán de cualquier solicitud de creación de informes realizada por cualquier usuario. |
      | [!UICONTROL **Restringido para**] | Elija cuánto tiempo se restringirán las solicitudes. Puede elegir 1 minuto (predeterminado), 5 minutos, 10 minutos, 15 minutos o 30 minutos. <!--double-check this--> <p>Una restricción no se puede eliminar antes de que se haya establecido.</p> |

      {style="table-layout:auto"}

1. Seleccionar [!UICONTROL **Continuar con la cancelación**].

   Se muestra una notificación en la aplicación (como en Analysis Workspace) que informa a los usuarios de que la solicitud se ha cancelado. Para obtener más información sobre cómo aparece esto en Analysis Workspace, consulte [Experiencia cuando los usuarios acceden a un informe cancelado](#experience-when-users-access-a-cancelled-report).

## Experiencia cuando los usuarios acceden a un informe cancelado

En Analysis Workspace, los usuarios ven los siguientes mensajes cuando intentan acceder a un informe o una visualización afectados por una cancelación:

### Mensaje en el proyecto

Cuando los usuarios intentan acceder a un proyecto afectado por una cancelación, ven un mensaje que les informa de que el informe está restringido temporalmente:

![Mensaje de cancelación del proyecto](assets/workspace-canceled-report.png)

### Mensaje en la visualización

Cuando los usuarios intentan acceder a una visualización afectada por una cancelación, ven un mensaje que les informa de que el procesamiento de datos para el informe está restringido temporalmente:

![Mensaje de cancelación de visualización](assets/workspace-cancelled-visualization.png)