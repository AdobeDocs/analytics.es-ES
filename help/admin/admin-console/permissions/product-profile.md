---
title: Perfiles de producto para Adobe Analytics
description: Descubra cómo se pueden utilizar los perfiles de producto como ajustes preestablecidos de permisos que los administradores de productos pueden asignar a los usuarios de una organización.
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
feature: Admin Tools
role: Admin
TQID: https://experienceleague.adobe.com/pEMsqMvXmpASV9-DOBoZHzbWp88v5kJioww9H1nJkzY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c67272a6-888e-425e-9e97-a87304637eedid: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: e681610c8238aa4940053a28ee60ea54492cba8b
workflow-type: tm+mt
source-wordcount: 686
ht-degree: 62%

---

# Perfiles de producto para Adobe Analytics

Los perfiles de producto son ajustes preestablecidos de permisos que los administradores de productos pueden asignar a los usuarios de una organización. Si crea un perfil de producto y asigna un usuario de CX Enterprise a ese perfil de producto, heredarán los elementos de permiso contenidos en el perfil de producto.

Para obtener información general sobre los perfiles de producto, incluida la creación de perfiles de producto y la asignación de usuarios, consulte [Administrar perfiles de producto para usuarios empresariales](https://helpx.adobe.com/es/enterprise/using/manage-product-profiles.html?lang=es) en la guía de usuario de Enterprise.

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

Los desarrolladores son similares a los usuarios, pero se les concede la capacidad de usar las API de Experience Cloud en Adobe Developer. Consulte [Administrar desarrolladores](https://helpx.adobe.com/es/enterprise/using/manage-developers.html) en la guía de usuario de empresa para obtener más información. Si se concede a un usuario acceso de desarrollador para cualquier perfil, puede acceder a la consola de desarrollador (console.adobe.io) y editar las integraciones de Adobe Analytics. Las llamadas y respuestas de la API de Analytics autorizadas para el usuario dependen de los permisos de red de todos los perfiles a los que el usuario tiene acceso de desarrollador.

Por ejemplo, con permisos de perfil que incluyen todas las métricas, todas las dimensiones y un grupo de informes, un desarrollador puede hacer llamadas de API relevantes para cualquier componente dentro de ese grupo de informes. Si se añade el elemento de permiso Detección de anomalías, las respuestas de la API pueden incluir datos de anomalías. Como regla general, si un perfil concede acceso a un escenario dentro de la interfaz de Adobe Analytics, el acceso de desarrollador a un perfil definido de forma similar habilitaría las llamadas y respuestas de API correspondientes.
