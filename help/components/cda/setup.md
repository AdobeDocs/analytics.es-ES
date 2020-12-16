---
title: Configuración de análisis entre dispositivos
description: Configure un grupo de informes virtuales para habilitar CDA.
translation-type: tm+mt
source-git-commit: da4f4d843e02865c006df2190d19a85306dbf2d0
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 68%

---


# Configuración de análisis entre dispositivos

Una vez cumplidos todos los requisitos previos, siga los pasos siguientes para habilitar el análisis entre dispositivos. Debe pertenecer a un grupo de administradores de perfil de producto o tener privilegios de administrador en Adobe Analytics para seguir estos pasos.

>[!IMPORTANT]
>
>Todos los requisitos previos deben cumplirse antes de seguir estos pasos. Si no se cumplen todos los requisitos previos, la función no estará disponible o no funcionará. Consulte la [página de información general](overview.md) y el método de vinculación deseado ([vinculación basada en el campo](field-based-stitching.md) o [gráfico del dispositivo](device-graph.md), respectivamente) para conocer los requisitos previos y las limitaciones.

## Póngase en contacto con el administrador de éxito del cliente para que le aprovisione CDA en el grupo de informes entre dispositivos

CDA se aprovisiona en el grupo de informes entre dispositivos mediante ingeniería de Adobes. Póngase en contacto con el administrador de éxito del cliente con la siguiente información:

* Su ID de organización de Adobe Experience Cloud (una cadena alfanumérica que termina con @AdobeOrg)
* La ID del grupo de informes para el grupo de informes entre dispositivos que desea habilitar con CDA
* Qué método de CDA desea utilizar (costura basada en campo, gráfico privado de Adobe o gráfico de cooperación de Adobes)
* Si desea utilizar la vinculación basada en campos, la propiedad o el eVar que contiene el ID de usuario

Una vez que haya proporcionado esta información al CSM, trabajarán con el departamento de ingeniería de Adobe para habilitar el grupo de informes elegido para el procesamiento de CDA.

## Crear un grupo de informes virtuales entre dispositivos para ver la vista entre dispositivos

Los administradores con acceso para crear grupos de informes virtuales pueden crear grupos de informes virtuales CDA de la siguiente manera:

1. Vaya a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) e inicie sesión con sus credenciales de Adobe ID.
2. Haga clic en el icono de 9 cuadrículas en la parte superior y, a continuación, haga clic en Analytics.
3. Pase el ratón sobre los componentes en la parte superior y, a continuación, haga clic en Grupos de informes virtuales.
4. Haga clic en Agregar.
5. Escriba un nombre para el grupo de informes virtuales y asegúrese de que está seleccionado el grupo de informes habilitado para CDA.
6. (Opcional) Aplique un segmento al grupo de informes virtuales. Por ejemplo, puede aplicar un segmento que limite el grupo de informes virtuales a las fechas después de activar CDA y de iniciar la vinculación. Este segmento permite a los usuarios ver solamente intervalos de fechas enlazados dentro del VRS.
7. Haga clic en la casilla de verificación “Habilitar procesamiento de tiempo de informes”, que permite varias opciones más, incluido Análisis entre dispositivos.
8. Haga clic en la casilla de verificación “Definir puntos para las visitas de usuarios en los dispositivos”.
9. Haga clic en Continuar, termine de configurar el grupo de informes virtuales y, a continuación, haga clic en Guardar.

![Casilla CDA](assets/cda-checkbox.png)

## Adiciones y cambios en los grupos de informes virtuales entre dispositivos

Cuando Análisis entre dispositivos está habilitado en un grupo de informes virtuales, tenga en cuenta los siguientes cambios:

* Aparece un nuevo icono entre dispositivos junto al nombre del grupo de informes virtuales. Este icono es exclusivo para grupos de informes virtuales entre dispositivos.
* Hay disponible una nueva dimensión con la etiqueta [Estado identificado](../dimensions/identified-state.md). Esta dimensión determina si el gráfico del dispositivo conoce el Experience Cloud ID de esa visita en ese momento.
* Hay disponibles nuevas métricas etiquetadas [Personas](../metrics/people.md) y [Dispositivos únicos](../metrics/unique-devices.md).
* La métrica [Visitantes únicos](../metrics/unique-visitors.md) no está disponible, ya que se sustituye por &#39;Personas&#39; y &#39;Dispositivos únicos&#39;.
* Al generar segmentos, el contenedor de segmentos “Visitante” se reemplaza por un contenedor “Persona”.
