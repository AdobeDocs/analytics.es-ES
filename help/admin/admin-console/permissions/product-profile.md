---
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566
translation-type: tm+mt

---
# Perfiles de producto en Adobe Analytics

Los perfiles de producto son un ajuste preestablecido de permisos que los administradores de productos pueden asignar a los usuarios de una organización. Si crea un perfil de producto y asigna un usuario de Experience Cloud a ese perfil de producto, heredarán los elementos de permiso contenidos en el perfil de producto.

Consulte [Administrar productos y perfiles](https://helpx.adobe.com/es/enterprise/using/manage-products-and-profiles.html) en la guía de usuario de Enterprise para obtener información general sobre los perfiles de producto.

## Administradores de perfil de producto

Los administradores de perfil de producto son un grupo opcional que puede agregar o eliminar usuarios a ese perfil de producto. Tenga en cuenta que un administrador de perfiles de producto no es lo mismo que un administrador de productos:

* Los administradores de perfil de producto son responsables solo de la lista de usuarios de un perfil de producto.
* Los administradores de perfil de producto no tienen acceso completo a Adobe Analytics. El acceso completo a Adobe Analytics está reservado para los administradores de productos.
* Los administradores de perfiles de producto no pueden ajustar los elementos de permisos en su perfil de producto; un administrador de productos debe realizar ajustes en los elementos de permisos.
* Los administradores de perfil de producto son ideales para los gerentes o jefes de equipo que solo necesitan otorgar y administrar el acceso a Adobe Analytics para su equipo. Los usuarios no necesitan molestar a los administradores del sistema o de productos para conceder acceso a Adobe Analytics.

## Elementos de permiso de Adobe Analytics

Los permisos mínimos requeridos en un perfil de producto para acceder a Adobe Analytics son los siguientes:

* El perfil de producto debe tener acceso al menos a un grupo de informes
* El perfil de producto debe pertenecer al elemento de permiso Herramientas de Analytics **Acceso a Analysis Workspace** (o **Acceso a Reports &amp; Analytics**)

### Grupos de informes

Concede acceso a los grupos de informes que pertenecen a su organización de Analytics. Un usuario debe pertenecer al menos a un grupo de informes para que se le conceda acceso para utilizar Adobe Analytics.

### Métricas

Otorga acceso a las métricas del grupo de informes. Las métricas se muestran como su componente respectivo en Analysis Workspace o si la métrica está disponible en Reports &amp; Analytics, disponible como un elemento de menú en Métricas del sitio.

Las métricas personalizadas están etiquetadas como &#39;Evento personalizado 1-1000&#39; para mantenerlas independientes de los grupos de informes. Si &#39;Evento personalizado 1&#39; es un elemento de permiso habilitado, ese usuario tiene acceso a event1 en todos los grupos de informes del perfil de producto.

### Dimensiones

Otorga acceso a las dimensiones del grupo de informes. Las dimensiones se muestran como sus respectivos componentes en Analysis Workspace o si están disponibles en Reports &amp; Analytics, disponibles como elemento de menú.

Las variables personalizadas, como las eVars, están etiquetadas como &#39;Conversión personalizada 1-250&#39; para mantenerlas independientes de los grupos de informes. Si &#39;Conversión personalizada 1&#39; es un elemento de permiso habilitado, ese usuario tiene acceso a eVar1 en todos los grupos de informes del perfil de producto.

### Herramientas de grupos de informes

Los elementos de permiso de las herramientas del grupo de informes otorgan acceso a funciones específicas de los grupos de informes a los que el usuario tiene acceso. Consulte [Herramientas de grupos de informes](report-suite-tools.md) para obtener una lista completa de los elementos y las descripciones de los permisos.

### Herramientas de Analytics

Los elementos de permiso de las herramientas de Analytics conceden acceso a funciones que son independientes de la configuración del grupo de informes. Consulte [Herramientas de Analytics](analytics-tools.md) para obtener una lista completa de los elementos y las descripciones de los permisos.

## Desarrolladores de perfil de producto

Los desarrolladores son similares a los usuarios, pero se les concede la capacidad de usar la API de Experience Cloud en Adobe I/O. Consulte [Administrar desarrolladores](https://helpx.adobe.com/es/enterprise/using/manage-developers.html) en la guía de usuario de Enterprise para obtener más información.
