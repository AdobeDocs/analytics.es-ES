---
description: Habilite permisos de usuario para elementos generales (facturación, registros, etc.), administración de la empresa, herramientas, acceso a servicios web, Report Builder e integración de Data Connectors.
keywords: grupos;permisos
seo-description: Habilite permisos de usuario para elementos generales (facturación, registros, etc.), administración de la empresa, herramientas, acceso a servicios web, Report Builder e integración de Data Connectors.
seo-title: Personalizar permisos para las herramientas de Analytics
solution: Analytics
subtopic: Usuarios y grupos
title: Personalizar permisos para las herramientas de Analytics
topic: Herramientas de administración
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
translation-type: tm+mt
source-git-commit: 31222a67cae860e5e914eea1c0c2fd82296d3704

---


# Personalizar permisos para las herramientas de Analytics

>[!IMPORTANT]
>
>La administración de usuarios y productos se ha trasladado a la [Consola](https://helpx.adobe.com/enterprise/using/admin-console.html)de administración. Adobe le avisará cuando deba migrar a sus usuarios. After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** will be retired.

Habilite permisos de usuario para elementos generales (facturación, registros, etc.), administración de la empresa, herramientas, acceso a servicios web, Report Builder e integración de Data Connectors.

**[!UICONTROL Administración]** de usuarios &gt; **[!UICONTROL Grupos]** &gt; **[!UICONTROL Acceso]** a todos los informes &gt; Herramientas **** de Analytics &gt; **[!UICONTROL Personalizar]**

>[!NOTE]
>
>La versión de otoño de 2016 (20 de octubre) introdujo cambios en la administración de grupos. See [Administrative Changes - Fall 2016](../../../admin/user-management2/c-user-management/permissions-changes.md#concept_86581595B86B47D5B8F90282FC3E31EF) for a summary of changes.

## Acceso a los informes - Herramientas de Analytics

![](assets/report-access-analytics-tools.png)

Haga clic en **[!UICONTROL Personalizar]para seleccionar los elementos a los que tendrá acceso este grupo.**

## Descripciones de los campos

Las opciones de esta página pertenecen a los grupos de informes seleccionados en la página [!UICONTROL Definir grupos de usuarios].

| Elemento | Descripción |
|--- |--- |
| **General** |  |
| [Administrador de códigos](../../../admin/admin/code-manager-admin.md) | Habilita el permiso para descargar el código de recopilación de datos para plataformas móviles y web. |
| Administrador de códigos - Servicios Web | Permite a los usuarios que no son administradores acceder al Administrador de códigos por medio de Servicios Web. |
| [Registros](../../../admin/admin/logs.md) | Habilita el permiso para acceder a los archivos de registro, los cuales ayudan a saber cuándo inician sesión los usuarios, el uso que se hace del sistema, los accesos, los grupos de informes y los cambios de administración. |
| Registros - Servicios Web | Permite a los usuarios que no son administradores acceder a los registros de las herramientas de administración por medio de Servicios Web. |
| [Administración del tráfico](../../../admin/c-traffic-management/traffic-management.md) | La página Administración del tráfico permite especificar los cambios esperados en el volumen del tráfico. |
| Administración de permisos | Otorga acceso a las páginas de administración de usuarios en las herramientas de administración a los usuarios que no son administradores. Estos usuarios disponen de permisos de lectura, pero no de escritura. |
| Permisos (escritura) - Servicios Web | Permite a los usuarios que no son administradores leer y escribir la configuración de permisos en Administración de usuarios, dentro de Servicios Web.<br>Esta configuración se refiere específicamente a las acciones de permisos indicadas en la API de administración. |
| Permisos (lectura) - Servicios Web | Permite a los usuarios que no son administradores ver la configuración de permisos bajo Administración de usuarios, en Servicios Web.<br>Esta configuración se refiere específicamente a las acciones de permisos indicadas en la API de administración. |
| **Administración de la empresa** |  |
| [Seguridad](../../../admin/company/security-manager.md) | Otorga permiso para acceder a la página Administrador de seguridad para controlar el acceso a los datos de los informes. Las opciones incluyen contraseñas seguras, caducidad de las contraseñas, restricciones de inicio de sesión de direcciones IP y restricciones de dominio de correo electrónico. |
| Información sobre asistencia | Otorga permiso para acceder a Información de soporte técnico en Configuración de la empresa. |
| [Servicios Web](../../../admin/company/web-services-admin.md) | Permite acceder a la página Servicios Web dentro de la interfaz de las herramientas de administración ([!UICONTROL Configuración de la empresa] &gt; [!UICONTROL Servicios Web]).<br>La API de Servicios Web proporciona acceso programático a servicios de Adobe Analytics que le permiten duplicar y aumentar la funcionalidad disponible por medio de la interfaz de usuario. |
| Inicio de sesión único (heredado) | Otorga acceso a la página de inicio de sesión único en las herramientas de administración.<br>**Nota**: El inicio de sesión único en Adobe Experience Cloud se implementa mediante la [vinculación de cuentas](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html) entre Experience Cloud y las correspondientes soluciones. |
| [Acciones pendientes](../../../admin/company/pending-actions-admin.md) | Concede permiso para administrar las acciones pendientes en [!UICONTROL Configuración de la empresa]. |
| [Promoción conjunta de marca](../../../admin/company/co-branding-admin.md) | Concede permiso para promocionar Analytics de manera conjunta. |
| [Preferencias](../../../admin/admin/preferences-manager.md) | Otorga permiso para acceder a [!UICONTROL Administrador de preferencias]. |
| [Ocultar grupos de informes](../../../admin/company/c-hide-report-suites.md) | Concede permiso para ocultar grupos de informes en la interfaz de usuario de Adobe Analytics. |
| **Herramientas** | Estas opciones otorgan acceso a las herramientas de Analytics (interfaces y aplicaciones), así como a funciones avanzadas, como segmentación y métricas calculadas. |
| [Datos actuales](https://marketing.adobe.com/resources/help/en_US/reference/data_latency.html) | Concede permiso para usar la función Datos actuales en la generación de informes. |
| Usuarios con licencias para [Ad Hoc Analysis](https://marketing.adobe.com/resources/help/en_US/dsc/) | Otorga permiso para acceder a [!UICONTROL Ad Hoc Analysis]. |
| Acceso a Servicio Web | Permite a los usuarios que no son administradores acceder a Servicios Web. Genera credenciales para Servicios Web. |
| [Report Builder](https://marketing.adobe.com/resources/help/en_US/arb/setup.html) | Otorga a los miembros de este grupo acceso a licencias para el [!UICONTROL Report Builder]. |
| Acceso a [Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) | Concede a los usuarios acceso a Analysis Workspace, la interfaz de generación de informes recomendada para [!DNL Adobe Analytics]. |
| [Reports &amp; Analytics](https://marketing.adobe.com/resources/help/en_US/sc/user/) | Concede a los usuarios acceso a Reports &amp; Analytics. |
| [Creación de métricas calculadas](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) | Concede a los usuarios permiso para crear métricas calculadas. |
| [Creación de segmentos](https://marketing.adobe.com/resources/help/en_US/analytics/segment/) | Otorga a los usuarios permiso para crear segmentos. |
| **Data Connectors** |  |
| Integraciones (Crear, Actualizar o Eliminar) | Concede permiso para crear, actualizar y eliminar integraciones de conector de datos. |
