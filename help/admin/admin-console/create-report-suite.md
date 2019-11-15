---
title: Crear un grupo de informes
description: Cree un contenedor básico para la recopilación de datos en Adobe Analytics.
translation-type: tm+mt
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# Crear un grupo de informes

Un grupo de informes es un silo de datos que Adobe Analytics utiliza para extraer informes. Una organización puede tener muchos grupos de informes, cada uno con diferentes conjuntos de datos. Aunque en el pasado eran importantes los grupos de informes separados, tener un solo grupo de informes se ha vuelto más ventajoso. La introducción a los grupos de informes virtuales y el procesamiento del tiempo de los informes permite al usuario crear sus propios subconjuntos de datos, lo que permite la flexibilidad de obtener datos globales y específicos del sitio.

Este artículo está diseñado para administradores de nivel de sistema o administradores de análisis para prepararse para la recopilación de datos.

## Requisitos previos

[Guía](first-admin-guide.md)de administración de Adobe Analytics: Asegúrese de que un administrador de nivel de sistema le haya concedido acceso a Adobe Analytics a través de la Consola de administración de Experience Cloud

## Crear un grupo de informes

> [!NOTE] También existe una forma de crear un grupo de informes en Adobe Analytics con el administrador heredado. Adobe recomienda utilizar el asistente para la configuración de grupos de informes que se describe aquí.

1. Inicie sesión en [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en el icono de 9 cuadrados en la esquina superior derecha y, a continuación, haga clic en el logotipo de Analytics.
1. Debería ver automáticamente una ventana modal 'Bienvenido a Adobe Analytics'. Si no lo hace, haga clic en el icono de ayuda en la esquina superior derecha y, a continuación, seleccione 'Bienvenido a Adobe Analytics'.
1. En la ventana modal, haga clic en Iniciar configuración.
1. Siga cada mensaje que describa los aspectos básicos como el tipo de propiedad, las industrias y el huso horario. Haga clic en Siguiente.
1. Ahora se crea el grupo de informes. Adobe también recomienda disponer de un grupo de informes de desarrollo, por lo que las pruebas no manchan los datos de los clientes. Haga clic en el icono de ayuda en la esquina superior derecha y, a continuación, seleccione de nuevo 'Bienvenido a Adobe Analytics'.
1. En la ventana modal, haga clic en Iniciar configuración.
Asigne el mismo nombre a este grupo de informes, excepto anexar "- DEV" al final. Dado que este grupo de informes sólo recibirá tráfico interno, el tamaño estimado puede ser el más pequeño.
1. Haga clic en Siguiente para terminar de crear el grupo de informes dev.

## Resolución de problemas

**Tras iniciar sesión en Experience Cloud, el icono de Analytics aparece atenuado.**

Esto significa que a su cuenta no se le han concedido los permisos correctos para Analytics. Trabaje con un administrador de nivel de sistema de su organización para asegurarse de que pertenece a un perfil con los permisos adecuados para acceder a Adobe Analytics.

**Después de iniciar sesión en Adobe Analytics, falta la ventana emergente y la lista desplegable 'Bienvenido a Adobe Analytics'.**

Asegúrese de haber iniciado sesión a través de Experience Cloud, y no a través de my.omniture.com. Los usuarios que inician sesión a través de my.omniture.com no tienen disponible el asistente para la configuración de grupos de informes.

## Pasos siguientes

[Cree y configure una propiedad para Adobe Analytics en Launch](/help/implement/implement-with-launch/create-analytics-property.md): Crear un área para administrar la implementación de Analytics
