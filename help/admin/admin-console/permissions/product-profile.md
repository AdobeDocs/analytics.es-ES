---
title: Perfiles de producto para Adobe Analytics
description: Descubra cómo se pueden utilizar los perfiles de producto como ajustes preestablecidos de permisos que los administradores de productos pueden asignar a los usuarios de una organización.
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
feature: Admin Tools
role: Admin
source-git-commit: 8f1a17d2b07d5b37ef6d3d3f426234b29be61319
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 65%

---

# Perfiles de producto para Adobe Analytics

Los perfiles de producto son ajustes preestablecidos de permisos que los administradores de productos pueden asignar a los usuarios de una organización. Si crea un perfil de producto y asigna un usuario de Experience Cloud a ese perfil de producto, heredarán los elementos de permiso contenidos en el perfil de producto.

Para obtener información general sobre los perfiles de producto, incluida la creación de perfiles de producto y la asignación de usuarios, consulte [Administrar perfiles de producto para usuarios empresariales](https://helpx.adobe.com/es/enterprise/using/manage-product-profiles.html) en la guía de usuario de Enterprise.

## Administradores de perfil de producto

Los administradores de perfil de producto son un grupo opcional que puede agregar o eliminar usuarios a ese perfil de producto. Tenga en cuenta que un administrador de perfiles de producto no es lo mismo que un administrador de productos:

* Los administradores de perfil de producto no tienen acceso completo a Adobe Analytics. El acceso completo a Adobe Analytics está reservado para los administradores de productos.
* Los administradores de perfil de productos no pueden ajustar los elementos de permisos en el perfil de productos.
* Los administradores de perfil de productos pueden asignar o quitar perfiles de producto a grupos de usuarios.
* Los administradores de perfil de productos son ideales para los líderes o jefes de equipo que necesitan otorgar y administrar el acceso a Adobe Analytics para su equipo. Los usuarios no necesitan molestar a los administradores del sistema o de productos para conceder acceso a Adobe Analytics.

Para obtener información sobre cómo asignar administradores de perfil de producto, consulte la sección “Gestionar administradores de perfil de producto” en el artículo, [Administrar perfiles de producto para usuarios empresariales](https://helpx.adobe.com/es/enterprise/using/manage-product-profiles.html) en la guía de usuario de empresa.

## Elementos de permiso de Adobe Analytics

Los permisos mínimos requeridos en un único perfil de producto para acceder a Adobe Analytics son los siguientes:

* El perfil de producto debe tener acceso al menos a un grupo de informes
* El perfil de producto debe pertenecer al elemento de permiso Herramientas de Analytics **Acceso a proyectos de Workspace**.

### Grupos de informes

Concede acceso a los grupos de informes que pertenecen a su organización de Analytics. Un usuario debe pertenecer al menos a un grupo de informes para que se le conceda acceso para utilizar Adobe Analytics.

### Métricas

Otorga acceso a las métricas del grupo de informes. Las métricas se muestran como sus respectivos componentes en Analysis Workspace.

Las métricas personalizadas están etiquetadas como &#39;Evento personalizado 1-1000&#39; para mantenerlas independientes de los grupos de informes. Si &#39;Evento personalizado 1&#39; es un elemento de permiso habilitado, ese usuario tiene acceso a event1 en todos los grupos de informes del perfil de producto.

### Dimensiones

Otorga acceso a las dimensiones del grupo de informes. Las dimensiones se muestran como sus respectivos componentes en Analysis Workspace.

Las variables personalizadas, como las eVars, están etiquetadas como &#39;Conversión personalizada 1-250&#39; para mantenerlas independientes de los grupos de informes. Si &#39;Conversión personalizada 1&#39; es un elemento de permiso habilitado, ese usuario tiene acceso a eVar1 en todos los grupos de informes del perfil de producto.

### Herramientas de grupos de informes

Los elementos de permiso de las herramientas del grupo de informes otorgan acceso a funciones específicas de los grupos de informes a los que el usuario tiene acceso. Consulte [Herramientas de grupos de informes](report-suite-tools.md) para obtener una lista completa de los elementos y las descripciones de los permisos.

### Herramientas de Analytics

Los elementos de permiso de las herramientas de Analytics conceden acceso a funciones que son independientes de la configuración del grupo de informes. Consulte [Permisos de perfil de productos para las herramientas de Analytics](analytics-tools.md) para obtener una lista completa de los elementos y las descripciones de los permisos.

## Desarrolladores de perfil de producto

Los desarrolladores son similares a los usuarios, pero se les concede la capacidad de utilizar la API de Experience Cloud en Adobe Developer. Consulte [Administrar desarrolladores](https://helpx.adobe.com/es/enterprise/using/manage-developers.html) en la guía de usuario de empresa para obtener más información. Si se concede a un usuario acceso de desarrollador para cualquier perfil, puede acceder a la consola de desarrollador (console.adobe.io) y editar las integraciones de Adobe Analytics. Las llamadas y respuestas de la API de Analytics autorizadas para el usuario dependen de los permisos de red de todos los perfiles a los que el usuario tiene acceso de desarrollador.

Por ejemplo, con permisos de perfil que incluyen todas las métricas, todas las dimensiones y un grupo de informes, un desarrollador puede hacer llamadas de API relevantes para cualquier componente dentro de ese grupo de informes. Si se añade el elemento de permiso Detección de anomalías, las respuestas de la API pueden incluir datos de anomalías. Como regla general, si un perfil concede acceso a un escenario dentro de la interfaz de Adobe Analytics, el acceso de desarrollador a un perfil definido de forma similar habilitaría las llamadas y respuestas de API correspondientes.
