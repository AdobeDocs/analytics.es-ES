---
description: Cuando se programa un informe, se puede seleccionar una lista de publicación para utilizarla en la distribución.
title: Permitir anulaciones de la lista de publicación
feature: Report Builder
role: User, Admin
exl-id: a7bd6cdb-397a-45ba-88ff-c3b3c7062005
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: ht
source-wordcount: '162'
ht-degree: 100%

---

# Permitir anulaciones de la lista de publicación

Cuando se programa un informe, se puede seleccionar una lista de publicación para utilizarla en la distribución.

Las listas de publicaciones se configuran en las Herramientas de administración de Analytics.

Consulte el [Administrador de la Lista de publicaciones](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/publishing-list.html?lang=es) en la referencia de Analytics.

Para activar esta función, desplácese a la ventana [!UICONTROL Asistente para solicitudes: Paso 1].

Si activa [!UICONTROL Permitir anulación de la lista de publicación], el grupo de informes asignado a cada destinatario en la lista de publicación sustituye al grupo de informes para esta solicitud. Asimismo, si el libro contiene varios grupos de informes, se utilizará el ID del grupo de informes asociado a la lista de publicación.

Esta opción no está disponible para los grupos de informes que se seleccionen desde las celdas.

>[!NOTE]
>
>Si el informe programado se envía a varias listas de publicación, el informe se ejecuta una vez para cada lista. Los grupos de informes variables se reemplazan por el grupo de informes asignado a la lista de publicación.
