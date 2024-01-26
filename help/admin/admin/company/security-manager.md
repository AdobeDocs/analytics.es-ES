---
description: Permite controlar el acceso a los datos de los informes. Las opciones incluyen contraseñas seguras, caducidad de las contraseñas, restricciones de inicio de sesión de direcciones IP y restricciones de dominio de correo electrónico.
title: Administrador de seguridad
feature: Company Settings
exl-id: 6dcf0354-4b4a-4bd5-ba6c-ae42c7b9e4df
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 95%

---

# Administrador de seguridad

El Administrador de seguridad permite controlar el acceso a los datos de informes. Las opciones incluyen contraseñas seguras, caducidad de las contraseñas, restricciones de inicio de sesión de direcciones IP y restricciones de dominio de correo electrónico.

## Configuración

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Configuración de la compañía]** > **[!UICONTROL Servicios web]**

| Configuración | Descripción |
| --- | --- |
| Requiere contraseñas sólidas | Obliga a los usuarios a crear contraseñas más seguras conforme a las reglas siguientes: <ul><li>Tener al menos ocho caracteres.</li><li>Debe tener al menos un símbolo o número entre los caracteres primero y último.</li><li>Debe tener al menos un carácter alfa.</li><li>No figurar en un diccionario ni contener palabras del diccionario (inglés).</li><li>No incluir tres (3) caracteres consecutivos del nombre de usuario.</li><li>Ser diferente de las 10 contraseñas anteriores.</li></ul>**Nota**: Esta función se refuerza en las nuevas contraseñas a partir de este momento. No comprueba las contraseñas anteriores ni obliga a los usuarios a cambiar sus contraseñas actuales. Por este motivo, considere la posibilidad de habilitar la caducidad de la contraseña para obligar a los usuarios a cambiar sus contraseñas y adherirse a las reglas de contraseña segura. |
| Caducidad de la contraseña | Obliga a los usuarios a cambiar la contraseña de cuenta de usuario periódicamente. Puede especificarse el intervalo en el que deben caducar las contraseñas y forzar su caducidad inmediata. |
| Aplicar restricciones de inicio de sesión IP | (Esta función ya no está disponible a partir de enero de 2021).<br> Limita el acceso a los informes para direcciones IP individuales o en intervalos. Se pueden agregar hasta 100 entradas en la lista de filtro de direcciones IP, y cada una de ellas puede ser una dirección determinada o un rango de direcciones. Aplicar restricciones de inicio de sesión IP no se aplicará mientras no haya al menos una entrada en la lista de filtro de direcciones IP. Dirección IP aceptada: para especificar un intervalo de direcciones IP, este debe escribirse entre corchetes (por ejemplo, `192.168.10.[20-240]`). También pueden utilizarse caracteres comodín para especificar cualquier número del 0 al 255 (por ejemplo, `192.168.[10-14].*8`) Los inicios de sesión que generan errores se registran y pueden verse desde el [Registro de uso y acceso](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=es#section_6FBAF92D9EA244809C45A78A2F0A7232). |
| Aplicar restricciones de dominio de correo electrónico | Filtra las direcciones de correo electrónico y los dominios a los que Analytics envía marcadores, informes descargables y alertas. La lista de filtro de correo electrónico admite hasta 100 entradas, y cada una de ellas puede ser una dirección o un dominio completo de correo electrónico. Si un informe programado tiene un destino de correo electrónico no autorizado, Analytics enviará una notificación sobre el problema por correo electrónico, con un vínculo para anular la programación del informe. **[!UICONTROL Aplicar restricciones de dominio de correo electrónico]** no se aplicará mientras no haya al menos una entrada en la lista de filtro de dominio de correo electrónico aceptado. **[!UICONTROL Direcciones de correo electrónico y dominios aceptados]**: para especificar un intervalo de direcciones IP, este debe escribirse entre corchetes (por ejemplo, `192.168.10.[20-240]`). También pueden utilizarse caracteres comodín para especificar cualquier número del 0 al 255 (por ejemplo, `192.168.[10-14].*`) |
| Notificación de recuperación de contraseña | Avisa a los administradores especificados cuando los usuarios intentan restablecer contraseñas de cuenta de usuario. **[!UICONTROL Administradores disponibles]**: muestra todos los administradores. Con las combinaciones Ctrl+clic y Mayús+clic pueden seleccionarse varios administradores. **[!UICONTROL Miembros de correo electrónico]**: muestra el grupo de correo electrónico definido actualmente. |
