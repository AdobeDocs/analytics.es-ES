---
title: Configuración de análisis entre dispositivos
description: Configure un grupo de informes virtuales para habilitar CDA.
exl-id: e6d4e0c2-6b85-4f89-b51f-c0eed7a4e3da
feature: CDA
role: Admin
source-git-commit: cfa5cc02ba3a7349b51a904f29bab533c0f1c603
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 87%

---

# Configuración de análisis entre dispositivos

{{available-existing-customers}}

Una vez cumplidos todos los requisitos previos, siga los pasos siguientes para habilitar el análisis entre dispositivos. Debe pertenecer a un grupo de administradores de perfil de producto o tener privilegios de administrador en Adobe Analytics para seguir estos pasos.

>[!IMPORTANT]
>
>Todos los requisitos previos deben cumplirse antes de seguir estos pasos. Si no se cumplen todos los requisitos previos, la función no estará disponible o no funcionará. Consulte la [página de información general](overview.md) y el método de vinculación deseado ([vinculación basada en el campo](field-based-stitching.md) o [gráfico del dispositivo](device-graph.md), respectivamente) para conocer los requisitos previos y las limitaciones.

## 1. Abra un ticket con el Servicio de atención al cliente para que CDA abastezca a su grupo de informes entre dispositivos

El departamento de ingeniería de Adobe ofrece las analíticas de varios dispositivos en el grupo de informes entre dispositivos. Para iniciar este proceso, póngase en contacto con el Servicio de atención al cliente y asegúrese de proporcionar la siguiente información:

* Su ID de organización de Adobe Experience Cloud (la cadena alfanumérica que termina con @AdobeOrg)
* El ID del grupo de informes perteneciente al grupo de informes entre dispositivos que desea habilitar con analíticas de varios dispositivos
* Qué método de análisis multidispositivo desea utilizar (vinculación basada en el campo o gráfico de dispositivos de Adobe)
* Si desea utilizar la vinculación basada en campos, el prop o eVar que contiene el ID de usuario
* Su preferencia de frecuencia de repetición y longitud de retrospectiva. Las opciones incluyen una reproducción una vez a la semana con una ventana retrospectiva de 7 días o una reproducción cada día con una ventana retrospectiva de 1 día.
El valor predeterminado es la reproducción semanal con una ventana retrospectiva de 7 días. En este caso, los datos de la última semana están sujetos a cambios (ya que se identifican y se actualizan progresivamente).

Una vez que haya proporcionado esta información al Servicio de atención al cliente, estos se pondrán en contacto con el departamento de ingeniería de Adobe para habilitar el grupo de informes elegido para el procesamiento de analíticas de varios dispositivos.

## 2. Cree un grupo de informes virtuales entre dispositivos para ver la vista entre dispositivos

Los administradores con acceso para crear grupos de informes virtuales pueden crear grupos de informes virtuales CDA de la siguiente manera:

1. Vaya a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) e inicie sesión con sus credenciales de Adobe ID.
2. Haga clic en el icono de 9 cuadrículas en la parte superior y, a continuación, haga clic en Analytics.
3. Pase el ratón sobre **[!UICONTROL Componentes]** en la parte superior y luego haga clic en **[!UICONTROL Grupos de informes virtuales]**.
4. Haga clic en Agregar.
5. Escriba un nombre para el grupo de informes virtuales y asegúrese de que está seleccionado el grupo de informes habilitado para CDA.
6. (Opcional) Aplique un segmento al grupo de informes virtuales. Por ejemplo, puede aplicar un segmento que limite el grupo de informes virtuales a las fechas después de activar CDA y de iniciar la vinculación. Este segmento permite a los usuarios ver solo intervalos de fechas enlazados dentro del grupo de informes virtuales.
7. Haga clic en la casilla de verificación “Habilitar procesamiento de tiempo de informes”, que permite varias opciones más, incluido Análisis entre dispositivos.
8. Haga clic en la casilla de verificación “Definir puntos para las visitas de usuarios en los dispositivos”.
9. Haga clic en Continuar, termine de configurar el grupo de informes virtuales y, a continuación, haga clic en Guardar.

![Casilla CDA](assets/cda-checkbox.png)

## Adiciones y cambios en los grupos de informes virtuales entre dispositivos

Cuando Análisis entre dispositivos está habilitado en un grupo de informes virtuales, tenga en cuenta los siguientes cambios:

* Aparece un nuevo icono entre dispositivos junto al nombre del grupo de informes virtuales. Este icono es exclusivo para grupos de informes virtuales entre dispositivos.
* Hay una nueva dimensión denominada [Estado identificado](../dimensions/identified-state.md) disponible.
* Hay disponibles nuevas métricas etiquetadas como [Personas](../metrics/people.md), [Dispositivos únicos](../metrics/unique-devices.md), [Personas identificadas](../metrics/identified-people.md), [Personas no identificadas](../metrics/unidentified-people.md) y [Personas con Experience Cloud ID](../metrics/people-with-exp-cloud-id.md).
* La métrica [Visitantes únicos](../metrics/unique-visitors.md) no está disponible, ya que se ha sustituido por Personas y Dispositivos únicos.
* Al generar segmentos, el contenedor de segmentos “Visitante” se reemplaza por un contenedor “Persona”.
