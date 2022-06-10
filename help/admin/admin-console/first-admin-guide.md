---
title: Guía de administración inicial de Adobe Analytics
description: Obtenga información sobre cómo empezar con Adobe Analytics, los tipos de funciones generales y el inicio de sesión en la interfaz de usuario.
exl-id: fbbbd335-0d22-473e-adef-f92f8eab7bf0
feature: Admin Tools
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 95%

---

# Guía de administración inicial de Adobe Analytics

Un primer administrador es el punto de partida para permitir que el resto de la organización utilice cada solución de Experience Cloud. Una vez firmado el contrato, un equipo de aprovisionamiento de Adobe se prepara para la creación de la cuenta. El primer administrador recibe un correo electrónico con credenciales de inicio de sesión antes de la fecha de inicio del contrato. Se recomienda que verifique que la información de contacto del primer administrador se proporcione a Adobe y que sea precisa antes de firmar el contrato.

## Funciones clave en el uso de Experience Cloud

Si su organización ha adquirido Adobe Analytics, hay que tener en cuenta varias funciones clave:

* **Administradores de Adobe Analytics:** Estos usuarios tienen acceso completo a todo lo que hay en Adobe Analytics, incluida la configuración del grupo de informes y de los permisos de usuario. Según la estructura de su organización, diferentes personas o equipos pueden ser responsables de diferentes facetas de la administración de Analytics. Por ejemplo, una persona es responsable de designar qué variables utilizar en una implementación. Otra persona puede ser responsable de permitir que los usuarios extraigan correctamente los informes, asegurándose de que todos los usuarios tengan los permisos correctos. Identifique al menos a un usuario que sea responsable de la configuración del grupo de informes y los permisos de usuario de Analytics y que pueda invitar a otros administradores de Analytics desde allí.
* **Administradores de recopilación de datos:** Estos usuarios tienen acceso completo a todo lo que hay en la recopilación de datos de Adobe Experience Platform, incluidos permisos de publicación, creación de contenedores y permisos de usuario. Estos usuarios no son necesariamente programadores, pero es útil tener al menos un conocimiento básico de HTML, CSS y JavaScript. Son responsables de trabajar con los propietarios del sitio web de su organización para implementar las etiquetas en su sitio. Identifique al menos un usuario que sea responsable de la implementación de su organización y que pueda invitar a otros administradores de recopilación de datos desde allí.
* **Delegados de asistencia**: También conocidos como usuarios de asistencia técnica, no tienen privilegios adicionales en la interfaz de Analytics. En su lugar, reciben privilegios adicionales al comunicarse con el Servicio de atención al cliente de Adobe. Estos usuarios son casi siempre administradores de Analytics, ya que ayudan al Servicio de atención al cliente a solucionar problemas. Identifique al menos a un administrador de Analytics responsable de facilitar las interacciones entre los usuarios finales y el Servicio de atención al cliente de Adobe.
* **Propietarios de sitios web:** Estos usuarios individuales o equipos son responsables de la codificación y el desarrollo de su sitio web. No requieren cuentas, pero es recomendable que colaboren con administradores de recopilación de datos para obtener el código de las etiquetas e implementarlo en el sitio web.
* **Usuarios finales:** Estos usuarios generalmente ven los informes y buscan respuestas a preguntas comerciales. Los administradores de Analytics conceden a estos usuarios permisos para trabajar en el producto.

Como primer administrador, su función puede superponerse en una o varias de estas funciones. Siempre y cuando se cubran estas responsabilidades básicas, puede otorgar permisos para ayudar en la puesta a punto de otros miembros de su organización.

## Concesión de acceso de administrador de producto para Analytics

Los administradores de nivel de sistema no tienen acceso directo a los productos; sin embargo, pueden concederse acceso a ellos mismos añadiéndose como administradores de nivel de producto. Si desea que usted u otros usuarios tengan acceso a Adobe Analytics, puede seguir estos pasos.

1. Inicie sesión en [Admin Console](https://adminconsole.adobe.com/) con sus credenciales de Adobe ID.
1. Haga clic en la pestaña Productos en la parte superior. Todos los productos comprados por su organización están a la izquierda. Haga clic en Adobe Analytics y, a continuación, en el botón Nuevo perfil.
1. Asigne a este perfil el nombre “Acceso completo de administrador de Analytics” y, a continuación, haga clic en Finalizado.
1. Vuelva a la página Perfiles de producto, haga clic en el perfil recién creado y, a continuación, haga clic en la pestaña Permisos.
1. Haga clic en uno de los elementos de la línea de permisos. Si la inclusión automática está disponible, habilite la opción. Si la inclusión automática no está disponible, haga clic en Agregar todo. Ambas opciones mueven todos los elementos de permiso a la columna derecha.
1. Haga clic en Guardar. Repita el paso anterior para todas las categorías de permisos.
1. Una vez que todas las categorías de permisos se hayan concedido al perfil, vuelva a la página Información general haciendo clic en Información general en la parte superior.
1. En el icono de Adobe Analytics, haga clic en &#39;Asignar usuarios&#39;.
1. Introduzca la dirección de correo electrónico a la que desea otorgar acceso completo a Analytics y asígneles el perfil de acceso de administrador completo recién creado. Haga clic en Guardar.
1. Ahora el usuario tiene acceso completo a Adobe Analytics.

## Concesión de acceso de administrador de producto para la recopilación de datos en Experience Platform

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

## Pasos siguientes

[Crear un grupo de informes](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Haga que el administrador de Analytics inicie sesión en la herramienta y cree un grupo de informes para la recopilación de datos

[Crear una propiedad de etiquetas de Analytics](/help/implement/launch/create-analytics-property.md): Pida al administrador de recopilación de datos que inicie sesión en la herramienta y cree una propiedad para implementarla en el sitio
