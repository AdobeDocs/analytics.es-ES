---
title: Funciones de administrador en Adobe Analytics
description: Obtenga información sobre cómo empezar con Adobe Analytics, los tipos de funciones generales y el inicio de sesión en la interfaz de usuario.
feature: Admin Tools
exl-id: 9d10716f-5b66-42dc-b288-af34da203c35
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 58%

---

# Funciones de administrador en Adobe Analytics

Adobe Analytics admite varios tipos de administradores. Los administradores de Adobe Analytics completo tienen acceso a todo lo que hay en Adobe Analytics, mientras que otros administradores y usuarios pueden realizar tareas más especializadas.

>[!NOTE]
>
>Antes de poder asignar funciones en Adobe Analytics a cualquier usuario, este debe asignarse como primer administrador en Experience Cloud. El primer administrador puede proporcionar a los usuarios de la organización otras funciones clave, tal como se describe en este artículo. Para obtener más información sobre el primer administrador, consulte [Guía del primer administrador de Adobe Analytics](/help/admin/admin-console/first-admin-guide.md).


## Funciones principales en Experience Cloud y Adobe Analytics

Tenga en cuenta las siguientes funciones clave al utilizar Adobe Analytics:

* **Administradores completos de Adobe Analytics:** Estos usuarios tienen acceso completo a todo lo que hay en Adobe Analytics, incluida la configuración del grupo de informes y los permisos de usuario. Según la estructura de su organización, diferentes personas o equipos pueden ser responsables de diferentes facetas de la administración de Analytics. Por ejemplo, una persona es responsable de designar qué variables utilizar en una implementación. Otra persona puede ser responsable de permitir que los usuarios extraigan correctamente los informes, asegurándose de que todos los usuarios tengan los permisos correctos. Identifique al menos a un usuario que sea responsable de la configuración del grupo de informes y los permisos de usuario de Analytics y que pueda invitar a otros administradores de Analytics desde allí.
* **Administradores de recopilación de datos:** Estos usuarios tienen acceso completo a todo lo que hay en la recopilación de datos de Adobe Experience Platform, incluidos permisos de publicación, creación de contenedores y permisos de usuario. Estos usuarios no son necesariamente programadores, pero es útil tener al menos un conocimiento básico de HTML, CSS y JavaScript. Son responsables de trabajar con los propietarios del sitio web de su organización para implementar las etiquetas en su sitio. Identifique al menos un usuario que sea responsable de la implementación de su organización y que pueda invitar a otros administradores de recopilación de datos desde allí.
* **Administradores de perfil de producto:** Estos usuarios pueden agregar o eliminar usuarios a un perfil de producto, ajustar los elementos de permisos en su perfil de producto y asignar o quitar perfiles de producto a grupos de usuarios. Los administradores de perfil de producto no tienen acceso completo a Adobe Analytics. Sin embargo, son ideales para los jefes de equipo o los administradores que necesitan conceder y administrar el acceso a Adobe Analytics para su equipo. Para obtener más información sobre los perfiles de producto, consulte [Perfiles de producto para Adobe Analytics](/help/admin/admin-console/permissions/product-profile.md).
* **Delegados de asistencia**: También conocidos como usuarios de asistencia técnica, no tienen privilegios adicionales en la interfaz de Analytics. En su lugar, reciben privilegios adicionales al comunicarse con el Servicio de atención al cliente de Adobe. Estos usuarios son casi siempre administradores de Analytics, ya que ayudan al Servicio de atención al cliente a solucionar problemas. Identifique al menos a un administrador de Analytics responsable de facilitar las interacciones entre los usuarios finales y el Servicio de atención al cliente de Adobe.
* **Propietarios de sitios web:** Estos usuarios individuales o equipos son responsables de la codificación y el desarrollo de su sitio web. No requieren cuentas, pero es recomendable que colaboren con administradores de recopilación de datos para obtener el código de las etiquetas e implementarlo en el sitio web.
* **Usuarios finales:** Estos usuarios generalmente ven los informes y buscan respuestas a preguntas comerciales. Los administradores de Analytics conceden a estos usuarios permisos para trabajar en el producto.

## Conceder acceso completo de administrador de productos a Analytics

Los administradores de nivel de sistema no tienen acceso directo a los productos; sin embargo, pueden darse acceso añadiéndose como administradores de nivel de producto.

Para proporcionar a Adobe Analytics acceso a usted o a otros:

1. Inicie sesión en [Admin Console](https://adminconsole.adobe.com/) con sus credenciales de Adobe ID.
1. Haga clic en la pestaña **[!UICONTROL Productos]** en la parte superior. Todos los productos comprados por su organización están a la izquierda. Haga clic en **[!UICONTROL Adobe Analytics]** y, a continuación, haga clic en el botón **[!UICONTROL Nuevo perfil]** botón.
1. Asigne a este perfil el nombre &quot;Acceso completo de administrador de Analytics&quot; y, a continuación, haga clic en **[!UICONTROL Siguiente]** > **[!UICONTROL Guardar]**.
1. Vuelva a la página Perfiles de producto, haga clic en el perfil recién creado y, a continuación, vaya a la pestaña **[!UICONTROL Permisos]**.
1. Haga clic en uno de los elementos de la línea de permisos. Si la **[!UICONTROL inclusión automática]** está disponible, habilite la opción. If **[!UICONTROL Inclusión automática]** no está disponible, haga clic en **[!UICONTROL Agregar todo]**. Ambas opciones mueven todos los elementos de permiso a la columna derecha.
1. Haga clic en **[!UICONTROL Guardar]**.
Repita el paso anterior para todas las categorías de permisos.
1. Una vez concedidas todas las categorías de permisos al perfil, vuelva a la página Productos haciendo clic en **[!UICONTROL Product]** en la parte superior.
1. En el mosaico Adobe Analytics , haga clic en **[!UICONTROL Asignar usuarios]**.
1. Introduzca la dirección de correo electrónico a la que desea otorgar acceso completo a Analytics y asígneles el perfil de acceso de administrador completo recién creado. Haga clic en **[!UICONTROL Guardar]**.

Ahora el usuario tiene acceso completo a Adobe Analytics.

## Conceder acceso de administrador de producto para la recopilación de datos en el Experience Platform

El acceso de administrador de productos para la recopilación de datos en Experience Platform es casi idéntico al acceso de administrador de productos para Analytics.

1. Inicie sesión en [Adobe Admin Console](https://adminconsole.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la pestaña **[!UICONTROL Productos]** en la parte superior. Todos los productos comprados por su organización están a la izquierda. Haga clic en **[!UICONTROL Experience Platform Launch]** y, a continuación, haga clic en **[!UICONTROL Nuevo perfil]**.
1. Asigne a este perfil el nombre “Acceso completo de administrador de recopilación de datos” y, a continuación, haga clic en **[!UICONTROL Listo]**.
1. Vuelva a la página **[!UICONTROL Perfiles de producto]**, haga clic en el perfil recién creado y, a continuación, vaya a la pestaña **[!UICONTROL Permisos]**.
1. Haga clic en uno de los elementos de la línea de permisos. Si la **[!UICONTROL inclusión automática]** está disponible, habilite la opción. Si la inclusión automática no está disponible, haga clic en **[!UICONTROL Añadir todo]**. Ambas opciones mueven todos los elementos de permiso a la columna derecha.
1. Haga clic en **[!UICONTROL Guardar]**. Repita el paso anterior para todas las categorías de permisos.
1. Una vez que todas las categorías de permisos se hayan concedido al perfil, vuelva a la página Información general haciendo clic en **[!UICONTROL Información general]** en la parte superior.
1. En el mosaico de [!UICONTROL Experience Platform Launch], haga clic en **[!UICONTROL Asignar usuarios]**.
1. Introduzca la dirección de correo electrónico a la que desea otorgar acceso completo a Analytics y asígneles el perfil de acceso de administrador completo recién creado. Haga clic en **[!UICONTROL Guardar]**.
1. Ahora el usuario tiene acceso completo a la recopilación de datos de Experience Platform.

## Conceder acceso de administrador de producto para perfiles de producto

Para obtener información sobre la asignación de usuarios como administradores de perfil de producto, consulte la sección &quot;Administrar administradores de perfil de producto&quot; en el artículo, [Administrar perfiles de producto para usuarios empresariales](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) en la guía de usuario de Enterprise.

## Pasos siguientes

[Crear un grupo de informes](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Pida al administrador de Analytics que inicie sesión en la herramienta y cree un grupo de informes para la recopilación de datos

[Crear una propiedad de etiquetas de Analytics](/help/implement/launch/create-analytics-property.md): Pida al administrador de recopilación de datos que inicie sesión en la herramienta y cree una propiedad para implementarla en el sitio

Antes de poder asignar funciones en Adobe Analytics a cualquier usuario, este debe asignarse como primer administrador en Experience Cloud. El primer administrador puede proporcionar a los usuarios de la organización otras funciones clave, tal como se describe en este artículo.

Un primer administrador es el punto de partida para permitir que el resto de la organización utilice cada solución de Experience Cloud.

Después de firmar un contrato

1. El equipo de aprovisionamiento de la Adobe se prepara para la creación de la cuenta.

1. El primer administrador recibe un correo electrónico con credenciales de inicio de sesión antes de la fecha de inicio del contrato.

>[!IMPORTANT]
>
>   Se recomienda que verifique que la información de contacto del primer administrador se proporcione a Adobe y que sea precisa antes de firmar el contrato.
