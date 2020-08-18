---
title: Preguntas más frecuentes sobre la implementación
description: Preguntas más frecuentes sobre implementación y vínculos a más información.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 67%

---


# Preguntas frecuentes acerca de la implementación de Analytics

Preguntas más frecuentes sobre implementación y vínculos a más información.

## ¿Cuál es la diferencia entre el ID del visitante de Experience Cloud y el ID del visitante de Analytics?

El servicio de identidad asigna un identificador único y persistente que se puede compartir con otras soluciones de Experience Cloud. El ID de visitante de Analytics solo lo utiliza Analytics. Adobe recomienda utilizar el servicio de ID de visitante de Experience Cloud en la implementación.

## ¿Cómo implemento Seguimiento de vídeos de Heartbeat?

Consulte [Medición de audio y vídeo en Adobe Analytics](https://docs.adobe.com/content/help/es-ES/media-analytics/using/media-overview.html).

## ¿Puede una interrupción del servicio en Adobe afectar al rendimiento?

No. El archivo de JavaScript no se aloja en servidores de Adobe, por lo que una interrupción en Adobe no afectará a su biblioteca de AppMeasurement. Si utiliza Adobe Experience Platform Launch, el archivo JavaScript se aloja en Akamai o en una ubicación de servidor determinada por su organización.

## ¿Puede reducir el rendimiento el envío de datos desde el explorador a los servicios de Adobe?

AppMeasurement crea un objeto de imagen en la página HTML y, a continuación, el explorador solicita el objeto de imagen de los servidores de recopilación de datos de Adobe. Si los servidores de recopilación de datos van lentos o no responden, el proceso que administra esa solicitud se retrasará hasta que se devuelva la imagen o se agote el tiempo de espera. Como los exploradores administran las imágenes con varios procesos, una interrupción de Adobe tendría un impacto mínimo en el tiempo de carga de la página y bloquearía un proceso mientras los otros continúan funcionando.

## ¿Cómo invalido o elimino una implementación de Analytics?

A veces, una organización desea eliminar una implementación debido a la caducidad del contrato o reducir el número de llamadas al servidor.

* **Implementaciones mediante Launch**: Deshabilite o desinstale la extensión de Adobe Analytics en la ficha [!UICONTROL Extensiones] y, a continuación, publique.
* **Implementaciones** heredadas de AppMeasurement: Reemplace todo el contenido del `s_code.js` archivo con la siguiente línea de código:

```js
var s = new Object();
```

>[!WARNING]
>
>No:
>
>* Cambie el grupo de informes a un valor no válido, ya que crea una carga innecesaria en los servidores de Adobe.
>* Elimine el `s_code.js` archivo por completo, a menos que también elimine todas las referencias al archivo en cada página.
>* Cambie la `trackingServer` variable para que apunte lejos del Adobe. AppMeasurement sigue enviando solicitudes de imagen, que devuelven errores 404.

