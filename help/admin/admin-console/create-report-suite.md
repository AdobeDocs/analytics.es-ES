---
title: Crear un grupo de informes
seo-title: Crear un grupo de informes en Adobe Analytics
description: Cree un contenedor básico para la recopilación de datos en Adobe Analytics.
seo-description: Cree un contenedor básico para la recopilación de datos en Adobe Analytics.
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# Crear un grupo de informes

Un grupo de informes es un silo de datos que Adobe Analytics utiliza para extraer informes. Una organización puede tener muchos grupos de informes, cada uno con conjuntos de datos diferentes. Aunque los grupos de informes separados eran importantes en el pasado, tener un solo grupo de informes resultaba más ventajoso. La introducción a los grupos de informes virtuales y al procesamiento de intervalo de tiempo permite al usuario crear sus propios subconjuntos de datos, permitiendo la flexibilidad para obtener datos globales y específicos del sitio.

Este artículo está diseñado para administradores de nivel de sistema o administradores de Analytics para prepararse para la recopilación de datos.

## Requisitos previos

[Guía de primera administración de Adobe Analytics](first-admin-guide.md): Asegúrese de que un administrador de nivel de sistema le haya concedido acceso a Adobe Analytics a través de la Consola de administración de Experience Cloud.

## Crear un grupo de informes

> [!NOTE]Nota: También existe una forma de crear un grupo de informes en Adobe Analytics con el administrador heredado. Adobe recomienda utilizar el asistente de configuración de grupos de informes aquí descrito.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. Haga clic en el icono 9 cuadrado en la esquina superior derecha y, a continuación, haga clic en el logotipo de color de color.
1. Debería ver la ventana modal «Bienvenido a Adobe Analytics» automáticamente. Si no lo hace, haga clic en el icono de ayuda situado en la esquina superior derecha y seleccione'Bienvenido a Adobe Analytics '.
1. En la ventana modal, haga clic en Configuración de inicio.
1. Siga cada solicitud que describa los conceptos básicos como tipo de propiedad, industria y zona horaria. Haga clic en Siguiente.
1. Ahora se crea el grupo de informes. Adobe recomienda también tener un grupo de informes de desarrollo, por lo que las pruebas no marcan datos de clientes. Haga clic en el icono de ayuda situado en la esquina superior derecha y seleccione nuevamente Bienvenido a Adobe Analytics.
1. En la ventana modal, haga clic en Configuración de inicio.
Asigne a este grupo de informes el mismo nombre, excepto "- DEV" al final. Dado que este grupo de informes solo recibirá tráfico interno, el tamaño estimado puede ser el más pequeño.
1. Haga clic en Siguiente para terminar de crear el grupo de informes dev.

## Resolución de problemas

**Después de iniciar sesión en Experience Cloud, el icono de Analytics aparece atenuado.**

Esto significa que no se ha concedido a su cuenta los permisos correctos para Analytics. Trabaje con un administrador de nivel de sistema de su organización para asegurarse de pertenecer a un perfil con permisos adecuados para acceder a Adobe Analytics.

**Después de iniciar sesión en Adobe Analytics, falta la ventana emergente «Bienvenido a Adobe Analytics» y la lista desplegable.**

Asegúrese de haber iniciado sesión a través de Experience Cloud, y no mediante my. omniture. com. El usuario que inicie sesión en my.omniture.com no tiene disponible el asistente de configuración de grupos de informes.

## Pasos siguientes

[Cree y configure una propiedad para Adobe Analytics en Launch](../../implement/implement-with-launch/create-analytics-property.md): Cree un área para administrar su implementación de Analytics
