---
title: Crear un grupo de informes
description: Cree un contenedor básico para la recopilación de datos en Adobe Analytics.
translation-type: tm+mt
source-git-commit: 6efb60ae2f565e67426c78bf830ada655e29b3af
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 100%

---


# Crear un grupo de informes

Un grupo de informes es un silo de datos que Adobe Analytics utiliza para extraer informes. Una organización puede tener muchos grupos de informes, cada uno con diferentes conjuntos de datos. Aunque en el pasado era importante mantener grupos de informes separados, tener un único grupo de informes se ha vuelto más ventajoso. La introducción a los grupos de informes virtuales y el procesamiento del tiempo de los informes permite al usuario crear sus propios subconjuntos de datos, lo que permite la flexibilidad de obtener datos globales y específicos del sitio.

Este artículo está diseñado para administradores de nivel de sistema o administradores de análisis para prepararse para la recopilación de datos.

## Requisitos previos

[Guía de administración de Adobe Analytics](first-admin-guide.md): Asegúrese de que un administrador de nivel de sistema le haya concedido acceso a Adobe Analytics a través de la Admin Console de Experience Cloud

## Crear un grupo de informes {#create-report-suite}

>[!NOTE]
>
>También existe una forma de crear un grupo de informes en Adobe Analytics con el administrador heredado. Adobe recomienda utilizar el asistente para la configuración de grupos de informes que se describe aquí.

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en el icono de 9 cuadrados en la esquina superior derecha y, a continuación, haga clic en el logotipo de Analytics.
1. Debería ver automáticamente una ventana modal con &#39;Bienvenido a Adobe Analytics&#39;. Si no lo hace, haga clic en el icono de ayuda en la esquina superior derecha y, a continuación, seleccione &#39;Bienvenido a Adobe Analytics&#39;.
1. En la ventana modal, haga clic en Iniciar configuración.
1. Siga cada mensaje que describa los conceptos básicos como tipo de propiedad, industrias y zona horaria. Haga clic en Siguiente.
1. Se crea el grupo de informes. Adobe también recomienda disponer de un grupo de informes de desarrollo para que las pruebas no afecten a los datos de los clientes. Haga clic en el icono de ayuda en la esquina superior derecha y, a continuación, seleccione de nuevo &#39;Bienvenido a Adobe Analytics&#39;.
1. En la ventana modal, haga clic en Iniciar configuración.
Asigne el mismo nombre a este grupo de informes, excepto con el sufijo “- DEV” al final. Dado que este grupo de informes solo recibirá tráfico interno, el tamaño estimado puede ser el más pequeño.
1. Haga clic en Siguiente para terminar de crear el grupo de informes dev.

Para obtener más información sobre los pasos de esta ventana modal, consulte [Implementación modal](/help/implement/prepare/implementation-modal.md) en la Guía del usuario de implementación.

## Resolución de problemas

**Tras iniciar sesión en Experience Cloud, el icono de Analytics aparece sombreado.**

Esto significa que no se han concedido a su cuenta los permisos correctos para Analytics. Colabore con un administrador de nivel de sistema de su organización para asegurarse de que cuenta con un perfil con los permisos adecuados para acceder a Adobe Analytics.

**Después de iniciar sesión en Adobe Analytics, falta la ventana emergente de &#39;Bienvenido a Adobe Analytics&#39; y la lista desplegable.**

Asegúrese de haber iniciado sesión a través de Experience Cloud, y no a través de my.omniture.com. Los usuarios que inician sesión a través de my.omniture.com no tienen disponible el asistente para la configuración de grupos de informes.

## Pasos siguientes

[Cree y configure una propiedad para Adobe Analytics en Launch](/help/implement/launch/create-analytics-property.md): Crear un área para administrar la implementación de Analytics
