---
description: Habilite permisos de usuario para elementos generales (facturación, registros, etc.), administración de la empresa, herramientas, acceso a servicios web, Report Builder e integración de Data Connectors.
keywords: groups;permissions
subtopic: Users and groups
title: Personalizar permisos para las herramientas de Analytics
topic: Admin tools
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Personalizar permisos para las herramientas de Analytics

>[!IMPORTANT]
>
>La administración de usuarios y productos se ha trasladado a la [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Adobe le avisará cuando deba migrar a sus usuarios. After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** will be retired.

Habilite permisos de usuario para elementos generales (facturación, registros, etc.), administración de la empresa, herramientas, acceso a servicios web, Report Builder e integración de Data Connectors.

**[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL All Report Access]** > **[!UICONTROL Analytics Tools]** > **[!UICONTROL Customize]**

>[!NOTE] En la versión de otoño de 2016 (20 de octubre) se añadieron cambios en la administración de grupos. Consulte [Cambios administrativos: Otoño de 2016](/help/admin/user-management2/c-user-management/permissions-changes.md) para ver un resumen de los cambios.

## Acceso a los informes - Herramientas de Analytics

![](assets/report-access-analytics-tools.png)

Click **[!UICONTROL Customize]** to select items to which this group will have access.

## Descripciones de los campos

La configuración de esta página corresponde a los grupos de informes seleccionados en la [!UICONTROL Define User Groups] página.

| Elemento | Descripción |
|--- |--- |
| **General** |  |
| [Administrador de códigos](/help/admin/admin/code-manager-admin.md) | Habilita el permiso para descargar código de recopilación de datos para plataformas web y móviles. |
| Administrador de códigos - Servicios Web | Permite que un usuario no administrativo acceda al Administrador de códigos a través de los servicios Web. |
| [Registros](/help/admin/admin/logs.md) | Habilita el permiso para registrar archivos, lo que le ayuda a ver cuándo inician sesión los usuarios, el uso, el acceso, los grupos de informes y los cambios de administración. |
| Registros - Servicios Web | Permite que un usuario no administrativo acceda a los registros de las Herramientas de administración a través de los servicios Web. |
| [Administración del tráfico](/help/admin/c-traffic-management/traffic-management.md) | La página Administración del tráfico permite especificar los cambios esperados en el volumen de tráfico. |
| Administración de permisos | Concede a los usuarios que no son administradores acceso a las páginas de Administración de usuarios en las Herramientas de administración. Estos usuarios tienen permisos de lectura pero no de escritura. |
| Permisos (escritura) - Servicios Web | Otorga a los usuarios que no son administradores la posibilidad de leer y escribir la configuración de permisos en Administración de usuarios en Servicios Web.<br>Esta configuración se refiere específicamente a las acciones de permisos indicadas en la API de administración. |
| Permisos (lectura) - Servicios Web | Permite que un usuario que no es administrador realice la vista de la configuración de permisos en Administración de usuarios en Servicios Web.<br>Esta configuración se refiere específicamente a las acciones de permisos indicadas en la API de administración. |
| **Administración de la empresa** |  |
| [Seguridad](/help/admin/company/security-manager.md) | Otorga permiso para acceder a la página Administrador de seguridad para controlar el acceso a los datos de los informes. Las opciones incluyen contraseñas seguras, caducidad de las contraseñas, restricciones de inicio de sesión de direcciones IP y restricciones de dominio de correo electrónico. |
| Información de asistencia técnica | Otorga permiso para acceder a Información de soporte técnico en Configuración de la empresa. |
| [Servicios Web](/help/admin/company/web-services-admin.md) | Permite acceder a la página Servicios Web en la interfaz Herramientas de administración ([!UICONTROL Company Settings] > [!UICONTROL Web Services]).<br>La API de Servicios Web proporciona acceso programático a servicios de Adobe Analytics que le permiten duplicar y aumentar la funcionalidad disponible por medio de la interfaz de usuario. |
| Inicio de sesión único (heredado) | Otorga acceso a la página de inicio de sesión único en las Herramientas de administración.<br>**Nota:**El inicio de sesión único en Adobe Experience Cloud se implementa mediante la[vinculación de cuentas](https://marketing.adobe.com/resources/help/es_ES/mcloud/organizations.html)entre Experience Cloud y las correspondientes soluciones. |
| [Acciones pendientes](/help/admin/company/pending-actions-admin.md) | Grants permission to manage pending actions in [!UICONTROL Company Settings]. |
| [Promoción conjunta de marca](/help/admin/company/co-branding-admin.md) | Concede permiso para promocionar Analytics de manera conjunta. |
| [Preferencias](/help/admin/admin/preferences-manager.md) | Otorga permiso para acceder al [!UICONTROL Preference Manager]. |
| [Ocultar grupos de informes](/help/admin/company/c-hide-report-suites.md) | Concede permiso para ocultar grupos de informes en la interfaz de usuario de Adobe Analytics. |
| **Herramientas** | Esta configuración otorga acceso a las herramientas de Analytics (interfaces y aplicaciones) y a las funciones avanzadas como la segmentación y las métricas calculadas. |
| [Datos actuales](https://marketing.adobe.com/resources/help/es_ES/reference/data_latency.html) | Otorga permiso para utilizar la función Datos actuales en sistema de informes. |
| [Usuarios con licencias para Ad Hoc Analysis](https://marketing.adobe.com/resources/help/es_ES/dsc/) | Otorga permiso para acceder a [!UICONTROL Ad Hoc Analysis]. |
| Acceso a Servicio Web | Habilita el acceso a los servicios Web para los no administradores. Genera credenciales de servicio Web. |
| [Report Builder](https://marketing.adobe.com/resources/help/es_ES/arb/setup.html) | Concede a los miembros de este grupo acceso a [!UICONTROL Report Builder] licencias. |
| [Acceso a Analysis Workspace](https://marketing.adobe.com/resources/help/es_ES/analytics/analysis-workspace/) | Concede a los usuarios acceso a Analysis Workspace, la interfaz de generación de informes recomendada para [!DNL Adobe Analytics]. |
| [Reports &amp; Analytics](https://marketing.adobe.com/resources/help/es_ES/sc/user/) | Concede a los usuarios acceso a Reports &amp; Analytics. |
| [Creación de métricas calculadas](https://marketing.adobe.com/resources/help/es_ES/analytics/calcmetrics/) | Concede a los usuarios permiso para crear métricas calculadas. |
| [Creación de segmentos](https://marketing.adobe.com/resources/help/es_ES/analytics/segment/) | Otorga a los usuarios permiso para crear segmentos. |
| **Data Connectors** |  |
| Integraciones (Crear, actualizar o eliminar) | Concede permiso para crear, actualizar y eliminar integraciones de conector de datos. |
