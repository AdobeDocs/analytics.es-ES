---
title: Preguntas frecuentes sobre la implementación
description: Preguntas más frecuentes sobre implementación y vínculos a más información.
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '499'
ht-degree: 100%

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

## ¿Cómo invalido o quito una implementación de Analytics?

A veces, una organización desea quitar una implementación debido a la caducidad del contrato o para reducir el número de llamadas al servidor.

* **Implementaciones mediante Launch**: Deshabilite o desinstale la extensión de Adobe Analytics en la pestaña [!UICONTROL Extensiones] y, a continuación, publique.
* **Implementaciones heredadas de AppMeasurement**: Reemplace todo el contenido del archivo `s_code.js` con la siguiente línea de código:

```js
var s = new Object();
```

>[!WARNING]
>
>No haga lo siguiente:
>
>* Cambiar el grupo de informes por un valor no válido, ya que crea una carga innecesaria en los servidores de Adobe.
>* Eliminar el archivo `s_code.js` por completo, a menos que también quite todas las referencias al archivo en cada página.
>* Cambiar la variable `trackingServer` para que apunte fuera de Adobe. AppMeasurement sigue enviando solicitudes de imagen, lo que devuelve errores 404.


## Ejecuté AppMeasurement a través de un analizador de código y marcó su uso de `Math.random()` como un posible riesgo de seguridad. ¿Se utiliza `Math.random()` con datos confidenciales?

No. Los números que usan `Math.random()` no se utilizan para ocultar, enviar ni recibir datos confidenciales. Los datos enviados a los servidores de recopilación de datos de Adobe dependen de la seguridad de la conexión HTTPS subyacente. <!-- AN-173590 -->

AppMeasurement utiliza `Math.random()` en tres áreas clave:

* **Muestreo**: Según la implementación, parte de la información podría recopilarse para un pequeño porcentaje de visitantes del sitio. `Math.random()` se utiliza para determinar si un visitante en concreto debe enviar datos. La mayoría de las implementaciones no utilizan muestreo.
* **ID de visitante alternativo**: Si el ID de visitante no se puede recuperar de las cookies, se genera un ID de visitante aleatorio. Esta parte de AppMeasurement utiliza dos llamadas a `Math.random()`.
* **Destrucción de caché**: Se agrega un número aleatorio al final de las direcciones URL de solicitud de imagen para ayudar a evitar el almacenamiento en caché del explorador.
