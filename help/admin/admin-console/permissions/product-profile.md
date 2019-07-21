---
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566
translation-type: tm+mt

---
# Perfiles de producto en Adobe Analytics

Los perfiles de producto son un ajuste preestablecido de permiso que los administradores de productos pueden asignar a los usuarios de una organización. Si crea un perfil de producto y asigna un usuario de Experience Cloud a dicho perfil de producto, heredará los elementos de permisos contenidos en el perfil de producto.

See [Manage products and profiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) in the Enterprise user guide for general information on product profiles.

## Administradores de perfil de producto

Los administradores de perfil de producto son un grupo opcional que puede agregar o eliminar usuarios a dicho perfil de producto. Tenga en cuenta que un administrador de perfil de producto no es lo mismo que un administrador de producto:

* Los administradores de perfil de producto son simplemente responsables de la lista de usuarios de un perfil de producto.
* Los administradores de perfil de producto no tienen acceso completo a Adobe Analytics. Se reserva acceso completo a Adobe Analytics para administradores de productos.
* Los administradores de perfil de producto no pueden ajustar los elementos de permisos en su perfil de producto; un administrador de producto debe realizar ajustes de elementos de permisos.
* Los administradores de perfil de producto son ideales para administradores o responsables de equipo que solo necesitan conceder y administrar el acceso a Adobe Analytics para su equipo. Las personas no necesitarían que los administradores del sistema o administradores de productos concedieran acceso a Adobe Analytics.

## Elementos de permiso de Adobe Analytics

Los permisos mínimos requeridos en un perfil de producto para acceder a Adobe Analytics son los siguientes:

* El perfil de producto debe tener acceso a al menos un grupo de informes
* The product profile must belong to the Analytics Tools permission item **Analysis Workspace Access** (or **Reports &amp; Analytics Access**)

### Grupos de informes

Otorga acceso a los grupos de informes que pertenecen a su organización de Analytics. Un usuario debe pertenecer a al menos un grupo de informes para que tenga acceso a usar Adobe Analytics.

### Métricas

Otorga acceso a las métricas del grupo de informes. Las métricas se enumeran como su respectivo componente en Analysis Workspace o si la métrica está disponible en Informes y análisis, disponible como elemento de menú en Métricas del sitio.

Las métricas personalizadas tienen la etiqueta «Evento personalizado 1-1000» para mantenerlas independientes de los grupos de informes. Si «Evento personalizado 1» es un elemento de permiso habilitado, ese usuario tiene acceso al evento 1 en todos los grupos de informes del perfil de producto.

### Dimensiones

Otorga acceso a dimensiones en su grupo de informes. Las dimensiones se enumeran como su componente respectivo en Analysis Workspace o si la dimensión está disponible en Informes y análisis, disponible como elemento de menú.

Las variables personalizadas, como las evars, tienen la etiqueta «Conversión personalizada 1-250» para mantenerlas independientes de los grupos de informes. Si la «Conversión personalizada 1» es un elemento de permiso habilitado, ese usuario tiene acceso a evar 1 en todos los grupos de informes del perfil de producto.

### Herramientas de grupos de informes

Los elementos de los permisos de las herramientas del grupo de informes otorgan acceso a las funciones específicas de los grupos de informes a los que el usuario tiene acceso. See [Report Suite Tools](report-suite-tools.md) for a full list of permission items and descriptions.

### Herramientas de Analytics

Los elementos de permiso de herramientas de Analytics otorgan acceso a funciones que dependen de la configuración del grupo de informes. See [Analytics Tools](analytics-tools.md) for a full list of permission items and descriptions.

## Desarrolladores de perfiles de producto

Developers are similar to users, except they are granted the ability to use the Experience Cloud API on Adobe I/O. See [Manage Developers](https://helpx.adobe.com/enterprise/using/manage-developers.html) in the Enterprise user guide for more information.
