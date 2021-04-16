---
description: Cree un contenedor básico para la recopilación de datos en Adobe Analytics
title: Crear un grupo de informes
feature: Herramientas de administración
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 77%

---

# Crear un grupo de informes

Un grupo de informes es un silo de datos que Adobe Analytics utiliza para extraer informes. Una organización puede tener muchos grupos de informes, cada uno con diferentes conjuntos de datos. Aunque en el pasado era importante mantener grupos de informes separados, tener un único grupo de informes se ha vuelto más ventajoso. La introducción de [grupos de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en#virtual-report-suites) y el procesamiento del tiempo de los informes permite a los administradores crear sus propios subconjuntos de datos, lo que permite la flexibilidad para obtener datos globales y específicos del sitio.

Este artículo está diseñado para administradores de nivel de sistema o administradores de análisis para prepararse para la recopilación de datos.

## Requisitos previos

[Guía](/help/admin/admin-console/first-admin-guide.md) de administración inicial de Adobe Analytics: Asegúrese de que un administrador de nivel de sistema le haya concedido acceso a Adobe Analytics a través del Admin Console del Experience Cloud.

## Crear un grupo de informes {#create-report-suite}

1. Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]**.
1. Haga clic en **[!UICONTROL Crear nuevo]** > **[!UICONTROL Grupo de informes]**.
1. Para copiar la configuración de un grupo de informes, seleccione en la lista de plantillas un plantilla predefinida o un grupo de informes existente para usar como [plantilla.](/help/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)

   >[!NOTE]
   >
   >Solo puede copiarse la configuración, no los datos. Si el Servicio de atención al cliente va a sobrescribir la configuración, deberá confirmar por escrito el descargo de responsabilidad con el que el Servicio de atención al cliente le informa de los riesgos. Consulte [Configuración que no se copia desde un grupo de informes de origen](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md) para obtener más información.

1. Complete los campos descritos en [Nuevo grupo de informes.](/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
1. Haga clic en **[!UICONTROL Crear grupo de informes]**.

Una ID de grupo de informes tiene una longitud máxima de 40 bytes. Un nombre descriptivo del grupo de informes tiene una longitud máxima de 255 bytes.

## Resolución de problemas

**Tras iniciar sesión en Experience Cloud, el icono de Analytics aparece sombreado.**

Esto significa que no se han concedido a su cuenta los permisos correctos para Analytics. Colabore con un administrador de nivel de sistema de su organización para asegurarse de que cuenta con un perfil con los permisos adecuados para acceder a Adobe Analytics.

**Después de iniciar sesión en Adobe Analytics, falta la ventana emergente de &#39;Bienvenido a Adobe Analytics&#39; y la lista desplegable.**

Asegúrese de haber iniciado sesión a través de Experience Cloud, y no a través de my.omniture.com. Los usuarios que inician sesión a través de my.omniture.com no tienen disponible el asistente para la configuración de grupos de informes.

## Pasos siguientes

[Cree y configure una propiedad para Adobe Analytics en Launch](/help/implement/launch/create-analytics-property.md): Crear un área para administrar la implementación de Analytics
