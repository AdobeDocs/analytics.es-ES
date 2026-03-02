---
title: Configuración de Report Builder
description: Obtenga información a través de una guía completa para instalar y configurar Adobe Analytics Report Builder for Excel. Instrucciones de configuración paso a paso para una integración perfecta.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 9d0161a9-ee7b-43a9-92ad-4079cf4b9c6c
source-git-commit: 1e893ce94ee3da46bbf22d7a90573681950d1135
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 39%

---

# Configuración de Report Builder

Este artículo describe los requisitos para usar Report Builder for Adobe Analytics en [!DNL Microsoft] [!DNL Excel]. Y cómo instalar y configurar el complemento.

## Requisitos

Report Builder para Adobe Analytics es compatible con los siguientes sistemas operativos y exploradores web.

### macOS

- macOS versión 10.x o posterior
- Todas las [!DNL Microsoft] [!DNL Excel] versiones

### Windows

- Windows 10, versión 1904 o posterior
- [!DNL Excel] versión 2106 o posterior

  Todos los usuarios del escritorio de Windows [!DNL Excel] deben instalar Microsoft Edge Webview2 para utilizar el complemento. Para instalar el controlador:

   1. Vaya a <https://aka.ms/webview2installer>.
   1. Seleccione y descargue el instalador independiente Evergreen.
   1. Siga las instrucciones de instalación.

### Web Office

- Admite todos los exploradores y versiones


## Complemento de Excel de Report Builder

Debe instalar el complemento de Report Builder [!DNL Excel] para usar [!DNL Report Builder] para Adobe Analytics. Una vez instalado el complemento de Report Builder [!DNL Excel], puede obtener acceso a Report Builder desde un libro de [!DNL Excel] abierto.

### Descarga e instalación del complemento de Report Builder

Para descargar e instalar el complemento de Report Builder

1. Inicie [!DNL Excel] y abra un nuevo libro.

1. Seleccione **[!UICONTROL Insertar]** > **[!UICONTROL Obtener complementos]**.

1. En el cuadro de diálogo Complementos de Office, seleccione la pestaña Tienda.

1. Busque &quot;Report Builder&quot; y haga clic en **[!UICONTROL Agregar]**.

1. En el cuadro de diálogo Términos de licencia y política de privacidad, haga clic en **[!UICONTROL Continuar]**.

**Si no se muestra la pestaña Tienda**

1. En [!DNL Excel], seleccione Archivo > Cuenta > Administrar configuración.

1. Marque la casilla junto a “Habilitar experiencias conectadas opcionales”.

1. Reiniciar [!DNL Excel].

**Si su organización bloquea el acceso a la Microsoft Store**

- Póngase en contacto con su equipo de TI o de seguridad para solicitar la aprobación del complemento de Report Builder. Una vez concedida la aprobación, en el cuadro de diálogo Complementos de Office, seleccione la pestaña **[!UICONTROL Administración administrada]**.

  ![La ficha Administración administrada del cuadro de diálogo Complementos de Office.](./assets/image1.png)

- También puede recuperar manualmente el [archivo de manifiesto](https://reportbuilder.an.adobe.com/manifest.xml) y alojar el archivo en su propia infraestructura de TI. <br/>Siga la [documentación en línea](https://learn.microsoft.com/en-us/office/dev/add-ins/publish/publish) de Microsoft Office para obtener instrucciones sobre cómo instalar un archivo de manifiesto de Excel que no se proporciona desde la Tienda Microsoft.

Después de instalar el complemento de Report Builder, el icono de Report Builder se muestra en la cinta de opciones [!DNL Excel] debajo de la ficha Inicio.

![Icono de Report Builder en Excel](/help/analyze/report-builder/assets/rb_app_icon.png)

## Inicio de sesión en Report Builder

Después de instalar el complemento de Report Builder for Excel para su plataforma operativa o explorador, siga estos pasos para iniciar sesión en Report Builder.

1. Abra un libro de Excel.

1. Haga clic en el icono de Report Builder para iniciar Report Builder.

1. En la barra de herramientas de Adobe Report Builder, haga clic en **[!UICONTROL Iniciar sesión]**.

   ![Haga clic en el botón de inicio de sesión de Report Builder.](/help/analyze/report-builder/assets/rb_login.png)

1. Introduzca la información de la cuenta de Adobe Experience ID. La información de la cuenta debe coincidir con las credenciales de Adobe Analytics.

   ![Su icono de inicio de sesión y organización.](/help/analyze/report-builder/assets/image4.png)

Después de iniciar sesión, el icono de inicio de sesión y la organización aparecen en la parte superior del panel

## Cambio de organizaciones

La primera vez que inicie sesión, iniciará sesión en la organización predeterminada asignada a su perfil.

1. Haga clic en el nombre de la organización que se muestra cuando inicia sesión.

1. Seleccione una organización de la lista de organizaciones disponibles. Solo aparecen en la lista las organizaciones a las que tiene acceso.

   ![Lista de organizaciones a las que puede tener acceso.](/help/analyze/report-builder/assets/image5.png)

## Cerrar sesión

Puede cerrar la sesión de Report Builder desde el perfil de usuario.

1. Guarde los cambios en los libros abiertos.

1. Haga clic en el icono de avatar para mostrar su perfil de usuario.

   ![El avatar de perfil de usuario y el botón Cerrar sesión.](/help/analyze/report-builder/assets/image6.png)

1. Haga clic en **Cerrar sesión**.
