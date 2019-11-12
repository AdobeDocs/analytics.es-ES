---
description: AppMeasurement 3.x para ios
seo-description: Documentación heredada de AppMeasurement 3.x para ios
seo-title: AppMeasurement 3.x para ios
solution: Analytics
subtopic: Marcadores
title: AppMeasurement 3.x para ios
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 4907b2930d894525b93b02f743c095f824a61a3b

---


# AppMeasurement 3.x para iOS

*Nota: Este documento contiene información heredada de versiones anteriores de AppMeasurement, específicamente para las versiones 3.x para iOS.
Para obtener información sobre la implementación actual de AppMeasurement, consulte[Acerca de AppMeasurement para JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).*

*Última actualización: 15/03/2018 AppMeasurement 3.x para iOS*

Adobe AppMeasurement para iOS permite medir aplicaciones nativas de Apple para iPhone y iPad en Adobe Experience Cloud.

Esta guía se divide en dos secciones: una sección para los analistas que tienen experiencia en Adobe Analytics y otra sección para los desarrolladores de iOS con experiencia en el desarrollo de aplicaciones móviles.

**Versiones** admitidas: iOS 4.3 o posterior.

**Descargue las instrucciones y vínculos de descarga de biblioteca** para todas las plataformas móviles de AppMeasurement disponibles en la página Medición y optimización de aplicaciones móviles de Developer Connection. Debe tener una cuenta gratuita de Developer Connection o credenciales de inicio de sesión en informes y análisis para descargar las bibliotecas. Los vínculos de descarga no aparecerán hasta que haya iniciado sesión.

## Inicio rápido para analistas

Esta sección lo acompaña durante la implementación de la biblioteca de iOS y en el momento de agregar el código requerido para una implementación estándar. Se incluyen pasos para mostrarle cómo enviar eventos personalizados y otros datos.

Como analista, debe habilitar los informes de aplicaciones móviles para su grupo de informes. Si tiene que capturar métricas adicionales, debe proporcionar a su programador una descripción de las variables de datos de contexto que debería enviar la aplicación. Por ejemplo, para recopilar un nombre de usuario tras el inicio de sesión, su programador podría configurar el nombre de usuario en una variable de datos de contexto denominada `myco.username`.

### Habilitación de informes de aplicaciones móviles en Analytics

Analytics proporciona una interfaz para habilitar el seguimiento de ciclo de vida de aplicaciones móviles. Esta asignación permite a Analytics generar automáticamente los informes de aplicaciones móviles.

1. Abra Consola de administración &gt; Grupos de informes &gt; Editar configuración &gt; Administración de móviles &gt; Informes de aplicaciones móviles.
1. Haga clic en Habilitar el seguimiento del ciclo vital de las aplicaciones móviles.

Ahora se han capturado las métricas del ciclo vital, e Informes de aplicaciones móviles aparece en el menú Informes de SiteCatalyst.

### Captura de métricas adicionales mediante reglas de procesamiento

Si al realizar la implementación se envían eventos y dimensiones adicionales mediante datos de contexto, debe configurar las reglas de procesamiento para capturar esos datos.

Para poder crear las reglas de procesamiento, alguien de la organización debe obtener la certificación. Para obtener más información, consulte la Ayuda sobre las reglas de procesamiento.

Cuando las reglas de procesamiento estén habilitadas, en el ejemplo Copia de una variable de datos de contexto se muestra el proceso necesario para asignar datos de contexto.

### (Opcional) Habilitación del seguimiento sin conexión

Si planea almacenar visitas cuando el dispositivo esté sin conexión, su grupo de informes debe admitir la marca de fecha y hora.

Una vez que habilite el seguimiento sin conexión, todas las visitas deben admitir la marca de fecha y hora o no se recopilarán. Si en este momento está enviando datos de AppMeasurement a un grupo de informes que también recopila datos de JavaScript, tal vez necesite establecer un grupo de informes independiente para datos móviles y así evitar una pérdida de datos. También puede incluir una marca de fecha y hora personalizada en las visitas de JavaScript usando la variable s.timestamp.

Si no está seguro de que el grupo de informes admita la marca de hora, póngase en contacto con Atención al cliente.

## Inicio rápido para desarrolladores

Esta sección lo acompaña a través de los pasos para implementar la biblioteca de iOS y empezar a enviar datos de medición, incluidos:

* Obtención de la biblioteca
* Añadir la biblioteca al proyecto
* Unas palabras sobre TrackingHelper
* Implementación


### Obtención de la biblioteca

Visite Medición y optimización de las aplicaciones móviles en Developer Connection para descargar la biblioteca de Android. Una vez descomprimido el archivo descargado, tendrá los siguientes componentes de software:

* admsAppLibrary.jar: biblioteca diseñada para utilizarse con los simuladores y dispositivos Android. Requiere Android 2.0 o una versión posterior.
* Examples\TrackingHelper.java: clase opcional diseñada para mantener el código de seguimiento separado de la lógica de aplicación.

### Añadir la biblioteca al proyecto

1. En Eclipse IDE, haga clic con el botón secundario en el nombre del proyecto.
1. Seleccione Ruta de compilación &gt; Agregar archivos externos.
1. Select `admsAppLibrary.jar`.
1. Haga clic en Abrir.
1. Vuelva a hacer clic con el botón secundario en el proyecto y, a continuación, seleccione Ruta de compilación &gt; Configurar ruta de compilación.
1. Haga clic en la ficha Order and Export (Pedir y exportar).
1. Asegúrese de seleccionar `admsAppLibrary.jar`.

La aplicación puede importar las clases e interfaces de la biblioteca admsAppLibrary.jar mediante import com.adobe.ADMS.*;

### Añadir permisos de aplicaciones

La biblioteca AppMeasurement requiere los siguientes permisos para enviar datos y registrar llamadas de seguimiento sin conexión:

* INTERNET
* ACCESS_NETWORK_STATE

Para agregar estos permisos, agregue las siguientes líneas al archivo AndroidManifest.xml (en el directorio del proyecto de la aplicación):
`<uses-permission android:name="android.permission.INTERNET" />`
`<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />`

### Unas palabras sobre TrackingHelper

El SDK incluye una clase adicional y opcional llamada TrackingHelper. TrackingHelper proporciona una forma de separar su código de medición de su lógica de aplicación.

Considere el siguiente ejemplo: en la aplicación, quiere enviar un evento que rastree cada inicio de sesión. Puede agregar el siguiente código directamente después del código de inicio de sesión para enviar este evento (no se preocupe por los detalles del código, de eso trataremos más adelante):

```
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", "username_value");
measure.trackEvents("event1", contextData);
```

Se acepta este método directo, pero ¿no preferiría poner este código en algún otro lugar donde no le moleste durante el desarrollo de la aplicación? El TrackingHelper es ese "otro lugar". Dentro de TrackingHelper, puede colocar este código en un método denominado trackLogonEvent:

```
public static void trackLogonEvent (String username_value) {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", username_value);
measure.trackEvents("event1", contextData);
}
```

Ahora, en el código de la aplicación, puede rastrear un evento de inicio de sesión con una simple llamada a trackLogonEvent:

TrackingHelper.trackLogonEvent("username");

La llamada de medición en el código de la aplicación se ha reducido a una sola línea. Además, si tiene que cambiar la lógica de medición subyacente, deberá actualizar solo TrackingHelper. Si otro programador agrega algo al código, utilizará los métodos simplificados que usted haya definido sin hacer un curso intensivo sobre la biblioteca de AppMeasurement.

Creemos que preferirá utilizar TrackingHelper para nuevas implementaciones, aunque la configuración tarde uno o dos minutos más. Los pasos restantes de esta guía le indicarán cómo configurar TrackingHelper y empezar a enviar datos de medición.

Asegúrese de copiar TrackingHelper.java en un directorio que incluya archivos de clase para su aplicación y sustituya el nombre del paquete en la parte superior de este archivo para que coincida con la estructura del paquete (com.company.application). Si desea realizar la implementación sin TrackingHelper, puede encontrar varios ejemplos dentro de TrackingHelper que puede copiar en la aplicación.

### Implementación

1. Abra TrackingHelper.java y actualice TRACKING_RSID y TRACKING_SERVER con su ID de grupo de informes y el servidor de seguimiento. Por ejemplo:

   ```
   private static final String TRACKING_RSID = "rsid";
   private static final String TRACKING_SERVER = "server";
   ```

   Se requieren estos valores y deberán ser correctos o la medición no funcionará. Si no está seguro de estos valores, consulte con su experto en SiteCatalyst.

2. Busque el método configureAppMeasurement. Es allí donde habilitará SSL, el seguimiento sin conexión y hará otros cambios globales en la configuración. Por ahora, quite el comentario de la línea para habilitar debugLogging hasta que funcione tal como esperaba.

3. Agregue una llamada a configureAppMeasurement desde la actividad de raíz en la aplicación.

```
@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.main);
TrackingHelper.configureAppMeasurement(this);
}
```

Este es todo el código que necesita para iniciar el seguimiento de métricas personalizadas. Sin embargo, con algunas líneas adicionales en el código, puede habilitar el seguimiento del ciclo vital para enviar automáticamente métricas del ciclo vital, entre las que se incluyen inicios, actualizaciones, y usuarios diarios y mensuales. 

La biblioteca de AppMeasurement hace el trabajo pesado, el usuario solo tiene que agregar un par de llamadas de método a cada una de las clases de actividades de la aplicación.

### (Recomendado) Seguimiento de eventos del ciclo vital

Cuando se habilita el seguimiento del ciclo vital, cada vez que se inicia la aplicación, se envía una sola visita para realizar un seguimiento de las instalaciones, las actualizaciones, los días ocupados y las demás métricas del ciclo vital.

Para iniciar el seguimiento de los eventos de ciclo vital, en la aplicación, agregue llamadas a los métodos onResume() y onPause() en cada actividad dentro de la aplicación, tal y como se muestra en el siguiente ejemplo. También recomendamos pasar la actividad o servicio como el objeto de contexto en lugar de como el contexto de la aplicación.

```
@Override
protected void onResume() {
super.onResume();
TrackingHelper.startActivity(this);
}
@Override
protected void onPause() {
super.onPause();
TrackingHelper.stopActivity();
}
```

¡Ya está! Ya ha implementado el seguimiento del ciclo vital básico en la aplicación de Android. Una vez que su analista web haya configurado SiteCatalyst para procesar las métricas de AppMeasurement de los informes que genere, su grupo de informes SiteCatalyst contendrán las métricas del ciclo vital predeterminadas.

Hacia dónde puede ir desde aquí:

* (Opcional) Seguimiento de eventos personalizados. Agregue métodos personalizados a TrackingHelper para rastrear todos los eventos que quiera medir en la aplicación. Puede agregar métodos para rastrear inicios, compras en la aplicación, y así sucesivamente.
* (Opcional) Seguimiento de estados de aplicación. El estado de una aplicación es similar a una vista de página. Esta sección le muestra cómo agregar un método personalizado a TrackingHelper para rastrear el estado de una aplicación.
* Inicio rápido de medición de vídeo. Agregue código para rastrear métricas de vídeo, que incluyen vistas de vídeo, el total de tiempo de reproducción y los vídeos más populares.

### (Opcional) Seguimiento de eventos personalizados

Los eventos personalizados son métricas que son únicas para su aplicación. Puede enviar un evento personalizado cuando un usuario inicie sesión, inicie una compra en la aplicación o haga clic en un vínculo a su página de Facebook. La clase del asistente de seguimiento contiene un ejemplo que muestra cómo rastrear un evento personalizado. Puede utilizar este método como una plantilla para añadir métodos de seguimiento de eventos adicionales.

En TrackingHelper.java, defina un método de seguimiento de eventos personalizado:

```
public static void trackCustomEvents () {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("contextKey", "value");
measure.trackEvents("event1, event2", contextData);
}
```

En todo el código, puede llamar este método para hacer el seguimiento de un evento personalizado:

`TrackingHelper.trackCustomEvents();`

Use este proceso para agregar todos los métodos de seguimiento de eventos que necesite. Unas palabras sobre TrackingHelper contiene un método de ejemplo para rastrear un evento de inicio de sesión.

### (Opcional) Seguimiento de estados de aplicación

La clase del asistente de seguimiento también contiene un ejemplo que muestra cómo rastrear el estado de una aplicación. Hacer el seguimiento de un estado personalizado es muy parecido a hacer el seguimiento de un evento. La única diferencia es que utilizará el método trackAppState en lugar de trackEvents.

```
measure.trackAppState("name", contextData);
```

Desde el punto de vista de la generación de informes, trackAppState aumenta las vistas de páginas, mientras que trackEvents no lo hace.

## Inicio rápido de medición de vídeo

La medición de vídeo se describe en la guía Medición de vídeo en SiteCatalyst. En general, el proceso para medir vídeos es muy similar en todas las plataformas de AppMeasurement. Esta sección de inicio rápido contiene información general básica de las tareas de los programadores junto con ejemplos de código.

La misma biblioteca, admsAppLibrary.jar, se utiliza para el seguimiento de aplicaciones y vídeos. Estos métodos se denominan módulo de medios en la documentación por razones de claridad en todas las plataformas.

Antes de poder utilizar el módulo de medios, debe configurar una instancia de medición.

Para implementar el seguimiento de vídeos en Android, realice las siguientes tareas:

* Asigne eventos del reproductor a las variables de SiteCatalyst
* Configure hitos, segmentos y frecuencia de llamadas
* Seguimiento de eventos del reproductor

### Asigne eventos del reproductor a las variables de SiteCatalyst

Para configurar la medición de vídeo, debe asignar los eventos y las eVars de SiteCatalyst que haya seleccionado para el seguimiento de vídeos a las variables de datos de contexto. Para obtener más información, consulte Configuración de vídeo de SiteCatalyst.

Su analista web debería proporcionarle una hoja de cálculo de implementación de vídeo con la lista de las variables de SiteCatalyst que configuró para recibir datos de vídeo:

* Nombre del video (eVar): eVar2
* Nombre Del Vídeo (Prop): prop2
* Segmentos (eVar): eVar3
* Tipo de contenido (eVar): eVar1
* Tiempo de vídeo (evento): event3
* Vistas de vídeos (evento): event1
* Vídeos completados (evento): event7
* Vistas de segmentos de vídeo (evento): event2

1. Agregue el siguiente código después del código que ha agregado en Implementación, de modo que reemplace la variable de SiteCatalyst que ha seleccionado por el ejemplo en el código:

   ```
   ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();
   Hashtable<String, Object> contextDataMapping = new Hashtable<String, Object>();
   contextDataMapping.put("a.media.name", "eVar2,prop2");
   contextDataMapping.put("a.media.segment", "eVar3");
   contextDataMapping.put("a.contentType", "eVar1"); //note that this is not in the .media
   namespace
   contextDataMapping.put("a.media.timePlayed", "event3");
   contextDataMapping.put("a.media.view", "event1");
   contextDataMapping.put("a.media.segmentView", "event2");
   contextDataMapping.put("a.media.complete", "event7");
   mediaMeasure.ContextDataMapping = contextDataMapping;
   ```

2. Configure hitos, segmentos y frecuencia de llamadas.

3. Seguimiento de eventos del reproductor.


### Configure hitos, segmentos y frecuencia de llamadas

Los hitos le permiten enviar un evento al llegar a un punto específico del vídeo. Los segmentos le permiten dividir el vídeo en secciones para un seguimiento más granular. La frecuencia de llamada le permite enviar llamadas de medición con el tiempo de visualización en intervalos específicos. Para obtener más información, consulte Métricas de vídeo.

### Asigne hitos

Puede definir hitos en función de un porcentaje de la duración total o en función de los segundos transcurridos. En este ejemplo se definen los hitos como un porcentaje de la duración total. Para un vídeo de 2 minutos, el siguiente código envía eventos de hitos al llegar a los 30 segundos, 60 segundos y 90 segundos.

```
Hashtable<String, Object> milestoneMapping = new Hashtable<String, Object>();
milestoneMapping.put("25", "event4");
milestoneMapping.put("50", "event5");
milestoneMapping.put("75", "event6");
contextDataMapping.put("a.media.milestones", milestoneMapping);
```


### Asigne hitos de desplazamiento

En este ejemplo se definen los hitos por los segundos transcurridos desde el comienzo del vídeo. Para un vídeo de 2 minutos, el siguiente código envía eventos de hitos al llegar a los 20 segundos, 40 segundos y 60 segundos independientemente de la duración total del vídeo.

```
Hashtable<String, Object> offsetMilestoneMapping = new Hashtable<String, Object>();
offsetMilestoneMapping.put("20", "event8");
offsetMilestoneMapping.put("40", "event9");
offsetMilestoneMapping.put("60", "event10");

contextDataMapping.put("a.media.offsetMilestones", offsetMilestoneMapping);
```

### Ejemplos

```
//get sharedInstance
ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();

//Track By Milestones:
mediaMeasure.trackMilestones = "25,50,75";

// track Milestones & segmentByMilestones:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;

// track by seconds:
mediaMeasure.trackSeconds = 15;

// track Milestones & segmentByMilestones & seconds:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;
mediaMeasure.trackSeconds = 15;

// track offsetMilestones & segmentByOffsetMilestones:
mediaMeasure.trackOffsetMilestones = "15,30,45,60,75,90";
mediaMeasure.segmentByOffsetMilestones = true;

// track offsetMilestones:
mediaMeasure.trackOffsetMilestones = "5,15,45";
```

### Seguimiento de eventos del reproductor

Para medir un vídeo, debe agregar código que indique al módulo de medios cuándo se producen eventos en el reproductor (mediante los métodos open, play, stop y close). Cuando un usuario empiece a reproducir un vídeo, deberá llamar al método play para que el módulo de medios empiece a contar los segundos vistos.

Si el usuario pone en pausa un vídeo, deberá llamar a stop para que el contador quede en pausa. Esto se realiza generalmente mediante administradores de eventos que están expuestos por el reproductor.

Por ejemplo:

Cargar: llama a open y a play

Pausa: llama a stop. Por ejemplo, si un usuario pone en pausa un vídeo después de 15 segundos, llama a stop("Video1",15).

Búfer: llama a stop mientras el vídeo se almacena en el búfer. Llama a play cuando se reanude la reproducción.

Reanudar: llama a play. Por ejemplo, cuando un usuario reanuda un vídeo después de 15 segundos de reproducción inicial, llama a s.play("Video1",15).

Anulación (deslizador): cuando el usuario arrastra el deslizador del vídeo, llama a stop. Cuando el usuario libera el deslizador del vídeo, llama a play.

Finalizar: llama a stop y luego a close. Por ejemplo, al finalizar un vídeo de 100 segundos, llama a stop("Video1",100) y luego a close("Video1").

Para que esto suceda, puede definir cuatro funciones personalizadas que puede invocar desde el administrador de eventos del reproductor de medios. Los distintos parámetros que se pasan a open, play, stop y close proceden del reproductor. El siguiente ejemplo de código muestra cómo se puede realizar:

```
function startMovie(){
mediaMeasure.open(mediaName,mediaLength,mediaPlayerName);
playMovie();
}
/*Call on video resume from pause and slider release*/
function playMovie(){
mediaMeasure.play(mediaName,mediaOffset);
}
/*Call on video pause and slider grab*/
function stopMovie(){
mediaMeasure.stop(mediaName,mediaOffset);
}
/*Call on video end*/
function endMovie(){
stopMovie();
mediaMeasure.close(mediaName);
Video Measurement Quick Start 12
```

## Métricas del ciclo vital

Esta hoja de cálculo contiene una lista de las métricas y las dimensiones que se miden cuando se habilita el seguimiento automático de ciclo vital.

### Métricas y dimensiones del ciclo vital

Cuando se configuran, las métricas del ciclo vital se envían en parámetros de datos contextuales a Analytics, parámetros a Target con cada llamada de mbox y como señal para la gestión de público. Analytics y Target usan el mismo formato, mientras que la gestión de público utiliza un prefijo distinto para cada métrica.

En Analytics, los datos contextuales que se envían con cada llamada de seguimiento del ciclo vital se capturan automáticamente y se registran usando la métrica o la dimensión de la primera columna (con las excepciones indicadas en la columna de la descripción).

| Métrica | Contexto de Analytics | Descripción de la señal de Analytics Context Audience Manager | Parámetro Data/Target |
|--- |--- |--- |--- |
| Primeros inicios | a.InstallEvent | c_a_InstallEvent | Se activa la primera vez que se ejecuta después de la instalación (o reinstalación). |
| Actualizaciones | a.UpgradeEvent | c_a_UpgradeEvent | Se activa la primera vez que se ejecuta después de las actualizaciones (cada vez que cambia el número de versión). |
| Usuarios comprometidos diariamente | a.DailyEngUserEvent | c_a_DailyEngUserEvent | Se activa cuando la aplicación se utiliza en un día concreto. |
| Usuarios comprometidos mensualmente | Usuarios comprometidos mensualmente | a.MonthlyEngUserEvent | Se activa cuando la aplicación se utiliza en un mes concreto. |
| Inicios | a.LaunchEvent | c_a_LaunchEvent | Se activa con cada ejecución, incluidos los bloqueos y las instalaciones. | Inicios También se activan al reanudar desde segundo plano cuando se ha excedido el tiempo de espera de sesión del ciclo vital. |
| Bloqueos | a.CrashEvent | c_a_CrashEvent | Se activa cuando la aplicación no realiza la salida de un modo adecuado. Se envía un evento al inicio de la aplicación después de un bloqueo (se considera que la aplicación está bloqueada si no llama a la salida). |
| Duración de la sesión anterior | a.PreviousSessionLength | Cc_a_PreviousSessionLength | Total de la duración de la sesión anterior en segundos. |

*Nota: Los usuarios **comprometidos**diariamente y los usuarios **comprometidos**mensualmente no se almacenan automáticamente en una métrica de Analytics. Debe crear una regla de procesamiento que configure un evento personalizado para capturar estas métricas.*

### Dimensiones

| Métrica | Parámetro de Target/dato contextual de Analytics | Señal de Analytics Context Audience Manager | Descripción |
|--- |--- |--- |--- |
| Fecha de instalación | a.InstallDate | c_a_InstallDate | Fecha del primer inicio después de la instalación. MM/DD/AAAA |
| Actualizaciones | a.UpgradeEvent | c_a_UpgradeEvent | Se activa la primera vez que se ejecuta después de las actualizaciones (cada vez que cambia el número de versión). |
| ID de la aplicación | a.AppID | c_a_AppID | Almacena el nombre y la versión de la aplicación en el siguiente formato:`[AppName] [BundleVersion]`. Por ejemplo, myapp 1.1. |
| Días transcurridos desde el primer uso | a.DaysSinceFirstUse | c_a_DaysSinceFirstUse | Número de días transcurridos desde que se ejecutó por primera vez. |
| Usuarios comprometidos mensualmente | Usuarios comprometidos mensualmente | a.MonthlyEngUserEvent | Se activa cuando la aplicación se utiliza en un mes concreto. |
| Inicios | a.LaunchEvent | c_a_LaunchEvent | Se activa con cada ejecución, incluidos los bloqueos y las instalaciones. | Inicios También se activan al reanudar desde segundo plano cuando se ha excedido el tiempo de espera de sesión del ciclo vital. |
| Bloqueos | a.CrashEvent | c_a_CrashEvent | Se activa cuando la aplicación no realiza la salida de un modo adecuado. Se envía un evento al inicio de la aplicación después de un bloqueo (se considera que la aplicación está bloqueada si no llama a la salida). |
| Duración de la sesión anterior | a.PreviousSessionLength | Cc_a_PreviousSessionLength | Total de la duración de la sesión anterior en segundos. |
| Días transcurridos desde el último uso | a.DaysSinceLastUse | c_a_DaysSinceLastUse | Número de días transcurridos desde que se ejecutó por última vez. |
| Día de la semana | a.DayOfWeek | c_a_DayOfWeek | Número del día de la semana en el que se inició la aplicación. |
| Hora del día | a.HourOfDay | c_a_HourOfDay | Mide la hora en la que se inició la aplicación. Formato numérico de 24 horas. Se utiliza en la partición de tiempo para determinar las horas de mayor uso. |
| Versión del sistema operativo | a.OSVersion | c_a_OSVersion | Versión del SO. |
| Días transcurridos desde la última actualización | a.DaysSinceLastUpgrade | c_a_DaysSinceLastUpgrade | Número de días transcurridos desde que se cambió el número de versión de la aplicación. |
| Inicios transcurridos desde la última actualización | a.LaunchesSinceUpgrade | c_a_LaunchesSinceUpgrade | Número de inicios realizados desde que se cambió el número de versión de la aplicación. |
| Nombre del dispositivo | a.DeviceName | c_a_DeviceName | Almacena el nombre del dispositivo. | iOS: cadena de dos dígitos separados por comas que identifica el dispositivo iOS. El primer número representa generalmente la generación del dispositivo y el segundo número representa generalmente versiones de miembros diferentes de la familia del dispositivo. Consulte Versiones de dispositivo iOS para tener una lista de nombres de dispositivos comunes. |
| Nombre del operador de telefonía móvil | a.CarrierName | c_a_CarrierName | Almacena el nombre del proveedor de servicios móviles indicado en el dispositivo. |
| Resolución | a.Resolution | c_a_Resolution | Anchura por altura en píxeles reales |

*Nota:**Días transcurridos desde la última actualización**,**los inicios desde la última actualización**y el nombre **de**operador de telefonía móvil no se almacenan automáticamente en una variable de Analytics. You must create a processing rule to copy these values to an Analytics variable for reporting.*

## Datos de contexto

Los datos de contexto son el método preferido para enviar los datos de aplicaciones a los servidores de recopilación.

En lugar de asignar explícitamente valores a props y eVars, puede utilizar las variables de datos de contexto para enviar pares nombre/valor asignados en SiteCatalyst. En función de estos pares de valor clave, puede establecer eventos, copiar valores en eVars y props y ejecutar afirmaciones condicionales adicionales. Así puede a evitar tener que hacer actualizaciones del código para admitir configuraciones de grupos de informes distintas.

Hay dos maneras de enviar datos de contexto con los métodos de seguimiento. Todos los datos de contexto configurados directamente en el objeto PersistentContextData se envían con cada llamada. También puede pasar datos de contexto como un parámetro a una sola llamada que se envía solo con esa llamada.

### Datos de contexto persistentes

Los valores colocados en los datos de contexto persistentes se envían con cada llamada al servidor. En el siguiente ejemplo, "clave" y "valor" se envían con todas las llamadas trackAppState:

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
measure.trackAppState("state1");
measure.trackAppState("state2");
measure.trackAppState("state3");
```

### Datos de contexto de una sola llamada

Para enviar datos de contexto en una sola llamada, envíe datos de contexto como parámetro para la llamada de seguimiento (trackAppState, trackEvents, etc.).

En el siguiente ejemplo, "clave" y "valor" se envían con las tres llamadas trackAppState: Sin embargo, "key2" y "value2" se envían solo con la segunda llamada trackAppState:

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData = contextData;
Hashtable<String, Object> contextDataState = new HashTable<String,Object>();
contextDataState.put("key2", "value2");
measure.trackAppState("state1");
measure.trackAppState("state2", contextDataState);
measure.trackAppState("state3");
```

## Variables de configuración

Las siguientes variables se configuran cuando se inicia la aplicación.:

*Nota: Todas las variables de configuración son opcionales, excepto ReportSuiteID y trackingServer.*

**Instancia compartida**

Antes de hacer llamadas de medición, debe recuperar una instancia de la biblioteca para cada método que llame en la biblioteca de medición:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*Nota: Las variables de configuración son privadas. Utilice los métodos obtener y configurar para cambiar estos valores.*

### Variables de configuración

**reportSuiteIDs**: (Requerido) El grupo de informes o los grupos de informes (etiquetado de grupos múltiples) que desea rastrear. Para rastrear grupos de informes múltiples, pase una lista delimitada por comas de los nombres de cada grupo de informes.

No puede sobrescribir esta variable para una sola llamada, debe cambiar el valor persistente.

Sintaxis:

```
String getReportSuiteIDs()
void setReportSuiteIDs(String reportSuiteIDs)
```

Ejemplos:

`measure.setReportSuiteIDs("rsid");`

Etiquetado de grupos múltiples:
`measure.setReportSuiteIDs("rsid1, rsid2");`

**trackingServer**: (Requerido) Identifica el servidor de recopilación.

Esta variable se debe rellenar con el dominio de su servidor de seguimiento sin incluir el prefijo de protocolo “http://” ni “https://”. El prefijo de protocolo lo gestiona automáticamente la biblioteca basándose en la variable ssl.

Si ssl es true, se establece una conexión segura con el servidor. Si ssl es false, se establece una conexión con el servidor que no es segura.

No puede sobrescribir esta variable para una sola llamada, debe cambiar el valor persistente.

Sintaxis:

```
String getTrackingServer()
void setTrackingServer(String trackingServer)
```

Ejemplos:

`measure.setTrackingServer("metrics.corp1.com");`

**visitorID**: Predeterminado: identificador uuidUnique para cada visitante. Si no configura una visitorID, se generará una visitorID única.

Recomendamos usar el valor predeterminado, a no ser que disponga de un caso de uso específico para configurar la visitorID. Si se configura una visitorID personalizada se pueden generar visitas duplicadas al usar el seguimiento de ciclo vital. Para evitarlo, defina la ID de visitante antes de configurar la medición de la aplicación.

**characterSet**: El valor predeterminado es UTF-8

Sintaxis:

```
String getCharSet()
void setCharSet(String charSet)
```

Ejemplos:
`[measure.setCharacterSet("UTF-8");`

**currencyCode**:El valor predeterminado es ninguno (se utiliza el valor definido para el grupo de informes)

El código de divisa usado para compras o eventos de divisa que se rastrean en la aplicación Android.

Sintaxis:

```
String getCurrencyCode()
void setCurrencyCode(String currencyCode)
```

Ejemplos:
`measure.setCurrencyCode("USD");`

**lifecycleSessionTimeout**: El valor predeterminado es 5 minutos

Especifica la duración, en segundos, que debe transcurrir entre cada inicio de aplicación antes de que el inicio se considere como una nueva sesión. Este tiempo de espera también se aplica cuando su aplicación se envía al segundo plano y se reactiva. El tiempo que la aplicación permanece en segundo plano no se incluye en la duración de la sesión.

Sintaxis:

```
int getLifecycleSessionTimeout()
void setLifecycleSessionTimeout(int sessionLength)
```

Ejemplos:

`measure.setLifecycleSessionTimeout(600); //10 minute session`

**ssl**: El valor predeterminado es false

Habilita (true) o deshabilita (false) el envío de datos de medición a través de SSL (HTTPS). No puede sobrescribir esta variable para una sola llamada, debe cambiar el valor persistente.

Sintaxis:

`void setSSL(boolean ssl)`

Ejemplos:

`measure.setSSL(true);`

**debugLogging** Default is false

Habilita (true) o deshabilita (false) la vista de información de depuración y la versión de la biblioteca en la consola de salida. De manera predeterminada, esta variable tiene el valor false. No puede sobrescribir esta variable para una sola llamada, debe cambiar el valor persistente.

Sintaxis:

`void setDebugLogging(boolean debugLogging)`

Ejemplos:

`measure.setDebugLogging(true);`

## Variables de seguimiento

**Instancia compartida**

Antes de hacer llamadas de medición, debe recuperar una instancia de la biblioteca para cada método que llame en la biblioteca de medición:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*Nota: Las variables de configuración son privadas. Utilice los métodos obtener y configurar para cambiar estos valores.*

### Variables de seguimiento persistentes

**Evar**: Establece la eVar especificada en el valor proporcionado. La eVar se envía con todas las llamadas de seguimiento hasta que se borra al configurarla en una cadena vacía o al llamar a clearVars.

Sintaxis:

`void setEvar(int evarNum, String evarValue)`

Ejemplo:
`measure.setEvar(1, "value");`

**Prop**: Establece la prop especificada en el valor proporcionado. La prop se envía con todas las llamadas de seguimiento hasta que se borra al configurarla en una cadena vacía o al llamar a clearVars.

Sintaxis:

`void setProp(int propNum, String propValue)`

Ejemplo:

`measure.setProp(1, "value");`

**Hier**: Establece la variable hier especificada en el valor proporcionado. La variable hier se envía con todas las llamadas de seguimiento hasta que se borra al configurarla en una cadena vacía o al llamar a clearVars.

Sintaxis:

`void setHier(int hierNum, String hierValue)`

Ejemplo:

`measure.setHier(1, "value");`


**ListVar**: Establece la listVar especificada en el valor proporcionado. La listVar se envía con todas las llamadas de seguimiento hasta que se borra al configurarla en una cadena vacía o al llamar a clearVars.

Sintaxis:

`void setListVar(int listNum, String listValue)`

Ejemplo:

`measure.setListVar(1, "value");`

**purchaseID**: La variable purchaseID se utiliza para evitar que SiteCatalyst cuente un pedido varias veces.

Cuando se usa un evento de compra en su sitio, debería asignar a esta compra una ID única usando la variable purchaseID.

`measure.setPurchaseID("unique_id");`

**transactionID**: Las fuentes de datos de integración utilizan un ID de transacción para enlazar los datos sin conexión con una transacción en línea (como un posible cliente o una compra generada en línea).

Cada transactionID única enviada a Adobe se registrará a fin de prepararla para una carga de fuentes de datos de información sin conexión sobre esa transacción.

`measure.setTransactionID("unique_id");`

**appState**: (nombre de página)El valor proporcionado para el estado de la aplicación se almacena en la variable del nombre de página.

`measure.setAppState("state");`

**canal**: measure.setChannel("mobile");

**appSection**: El valor proporcionado para la sección de la aplicación se almacena en la variable server.

Sintaxis:

`void setAppSection(String Section)`

Ejemplo:
`measure.setAppSection("news");`

**campaign**

Sintaxis:

`void setCampaign(String Campaign)`

Ejemplo:

`measure.setCampaign("112233");`

**Productos**

Sintaxis:

```
void setProducts(String Products)
// example Products string: Category;Product[,Category;Product]
```

Ejemplo:

`measure.setProducts("Running;Shoe");`

**eventos**

Sintaxis:

`void setEvents(String Event) //comma-delimited list`

Ejemplo:

`measure.setEvents("event1, event2");`

**geoState**

Sintaxis:

`void setGeoState(String GeoState)`

Ejemplo:

`measure.setGeoState("UT");`

**geoZip**

Sintaxis:

`void setGeoZip(String GeoZip)`

Ejemplo:

`measure.setGeoZip("12345");`

**Datos** de contexto persistentes: Los valores colocados en Datos de contexto persistentes se envían con cada llamada al servidor. Para enviar datos de contexto en una sola llamada, envíe una tabla hash de los datos de contexto como parámetro para la llamada de seguimiento (trackAppState, trackEvents, etc.).

Ejemplo:

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

Consulte Datos de contexto.

**linkTrackVars**: Lista delimitada por comas de nombres de variables que restringe el conjunto actual de variables para el seguimiento de vínculos. Si no se define linkTrackVars, AppMeasurement para Android envía todas las variables definidas con una llamada de trackLink.

Sintaxis:

`void setLinkTrackVars(String Vars) //comma-delimited list`

Ejemplo:

`measure.setLinkTrackVars("eVar1, prop1");`

**linkTrackEvents**: Lista de eventos delimitada por comas que restringe el conjunto actual de eventos para el seguimiento de vínculos. Si no se define linkTrackEvents, AppMeasurement para Android envía todos los eventos con una llamada de trackLink.

Sintaxis:

`void setLinkTrackEvents(String Events) //comma-delimited list`

Ejemplo:

`measure.setLinkTrackEvents("event1, event2");`

## Métodos

Esta sección contiene una lista de los métodos proporcionados por la biblioteca de Android.

**Instancia compartida**

Antes de hacer llamadas de medición, debe recuperar una instancia de la biblioteca para cada método que llame en la biblioteca de medición:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

### Configuración inicial

Este método configura las variables requeridas y debe llamarse antes que a otros métodos.

**configureMeasurement**: Este método se utiliza para configurar los dos parámetros necesarios para iniciar la medición de aplicaciones. Debe establecer los valores reportSuiteIDs y trackingServer en el objeto de medición mediante este método antes de enviar llamadas al servidor.

Sintaxis:

`void configureMeasurement(String reportSuiteIDs, String trackingServer)`

Ejemplos:

`measure.configureMeasurement("my_rsid", "my_tracking_server");`

### Seguimiento de estados y de eventos

Son los métodos principales para rastrear eventos personalizados y estados de aplicaciones.

**trackAppState**: Es la forma recomendada de rastrear los estados de la aplicación en la aplicación. El valor proporcionado en appState se muestra como la variable del nombre de página de la llamada al servidor. La cadena appState debe proporcionarse para cada llamada, ya que no se transfiere a la siguiente llamada.

Los datos de contexto enviados con esta llamada se anexan a cualquier valor en persistentContextData y se envían con la llamada. Solo los valores configurados en persistentContextData permanecen para la siguiente llamada.

Sintaxis:

`void trackAppState(string AppStateName)`

Ejemplos:

`measure.trackAppState("state");`

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.trackAppState("state", contextData);
```

**trackEvents**: Es la forma recomendada de rastrear eventos en la aplicación. trackEvents es similar a trackAppState, pero envía eventos en lugar de nombres de página. Los eventos se proporcionan como una cadena delimitada por comas. La cadena events debe proporcionarse para cada llamada, ya que no se transfiere a la siguiente llamada.

Este método realiza una llamada subyacente a trackLinkURL donde linkURL se define como nil, linkType se define como "o" y linkName se completa con la ID de la aplicación.

Esto significa que linkTrackVars y linkTrackEvents se aplican para llamadas a trackEvents.

Los datos de contexto enviados con esta llamada se anexan a cualquier valor en persistentContextData y se envían con la llamada. Solo los valores configurados en persistentContextData permanecen para la siguiente llamada.

Sintaxis:

`void trackEvents(string Events)`

Ejemplos:

`measure.trackEvents("event1");`

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.trackEvents("event1", contextData);
```

**Nota de importación si usa el método trackLink**

trackEvents hace una llamada subyacente a trackLink donde linkURL se define como null, linkType se define como "o" y linkName se completa con la ID de la aplicación. Esto se hace para evitar que el recuento de vistas de la página (vista de estado) incremente cada vez que envía un evento.

Si llama directamente a trackLink y configura los valores para linkTrackVars y linkTrackEvents, estas restricciones de variables y eventos se aplican a TrackEvents. Esto significa que solo las variables y los eventos definidos en estas listas se envían con TrackEvents. Debería configurar linkTrackVars y linkTrackEvents en nulo a no ser que quiera que esas restricciones se apliquen a trackEvents.

### Seguimiento avanzado (track y trackLink)

Estos métodos proporcionan opciones de seguimiento adicionales que le permiten completar directamente props, eVars y otras variables de SiteCatalyst. Deberían ser usados por clientes con una implementación existente o clientes muy familiarizados con otras implementaciones de SiteCatalyst.

`track` y `trackLink` son los principales métodos de medición que se implementan en todas las versiones de las bibliotecas de medición de Adobe en múltiples plataformas. En la mayoría de las circunstancias, al rastrear aplicaciones móviles es más fácil utilizar los métodos trackAppState y trackEvents que llamar directamente a las funciones track y trackLink.

El seguimiento de vista de páginas (track) y el seguimiento de vínculos (trackLink) envían todas las variables persistentes que tengan algún valor (no nulo, no vacío, no cero). Debe restaurar o vaciar todas las variables, según sea necesario, antes de llamar a track o a trackLink.

*Nota: Debido a que las aplicaciones modernas son multiproceso, no se recomienda configurar los valores de las variables persistentes para que se envíen con una llamada de seguimiento futura (mediante setEvar, setProp, setHier, SetListVar y setPersistentContextData). Por ejemplo, si se establece un valor de variable en varios subprocesos, el valor podría estar en un estado incoherente cuando se realice la llamada de seguimiento. Para evitarlo, se recomienda pasar los datos de contexto con cada llamada de seguimiento y configurar el valor de la variable en las reglas de procesamiento.

**Descripciones de métodos**

**track**: Envía una vista de página estándar, junto con cualquier variable adicional que se establezca en el objeto de medición, al servidor de recopilación.

Cada llamada de seguimiento envía todos los datos persistentes definidos en el objeto de medición (se enumeran en la descripción de clearVars), además de todos los contextData o variables que proporcione solo para esa llamada. Si envía una variable que está definida, se sobrescribirá cualquier valor en la correspondiente variable persistente.

Sintaxis:

```
void track()
void track(Hashtable<String, Object> contextData)
void track(Hashtable<String, Object> contextData, Hashtable<String, Object>
variables)
```

Ejemplos:

`measure.track();`

```
measure.setEvar(1, "evar1value");
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.track(contextData);
```

```
//set an eVar
measure.setEvar(1, "evar1value");
//contextData
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
//variable overrides
Hashtable variableOverrides = new Hashtable<String, Object>();
variableOverrides.put("evar2", "evar2value");
//sends eVar1, eVar2 (set in overrides), and context data
measure.track(contextData, variableOverrides);
```

**trackLink**: Envía datos de vínculos de salida, de descarga o personalizados a los servidores de recopilación de datos de Adobe, junto con cualquier variable trackconfig que tenga algún valor.

Utilice trackLink para rastrear toda actividad que no deba capturar una vista de página.

Sintaxis:

```
void trackLink(String linkURL, String linkType, String linkName,
Hashtable<String, Object> contextData, Hashtable<String, Object> variables)
```

**linkURL**: identifica la dirección URL donde se hizo clic. Si no se especifica la dirección URL, se utiliza el nombre. Utilice este parámetro solo cuando se vincule a una página web desde la aplicación Android. De lo contrario, pase el valor nulo en este parámetro.

**linkType**: identifica el informe del vínculo que mostrará la dirección URL o el nombre. Los valores admitidos son:
* “o” (vínculos personalizados)
* “d” (descargas de archivos)
* “e” (vínculos de salida)

**linkName**: el nombre que se muestra en el informe de vínculos. Si no se especifica el nombre, el informe utiliza la dirección URL.

Para recopilar datos debe especificar el parámetro linkURL o linkName. Cuando no utilice ninguno de estos parámetros, datos de contexto o variables adicionales, pase null como valor.

Ejemplos:

`measure.trackLink("url", "o", "name", contextData, null);`

**setEvar**: Establece la eVar especificada en el valor proporcionado. La eVar se envía con todas las llamadas de seguimiento hasta que se borra al configurarla en una cadena vacía o al llamar a clearVars.

Sintaxis:

`void setEvar(int evarNum, String evarValue)`

**setProp**: Establece la prop especificada en el valor proporcionado. La prop se envía con todas las llamadas de seguimiento hasta que se borra al configurarla en una cadena vacía o al llamar a clearVars.

Sintaxis:

`void setProp(int propNum, String propValue)`

**setHier**: Establece la variable hier especificada en el valor proporcionado. La variable hier se envía con todas las llamadas de seguimiento hasta que se borra al configurarla en una cadena vacía o al llamar a clearVars.

Sintaxis:

`void setHier(int hierNum, String hierValue)`

**setListVar**: Establece la listVar especificada en el valor proporcionado. La lista de variables se envía con todas las llamadas de seguimiento hasta que se borra al configurarla en una cadena vacía o al llamar a clearVars.

Sintaxis:

`void setListVar(int listNum, String listValue)`

**setPersistentContextData**: Los valores colocados en Datos de contexto persistentes se envían con cada llamada al servidor. Para enviar datos de contexto en una sola llamada, envíe una tabla hash de los datos de contexto como parámetro para la llamada de seguimiento (trackAppState, trackEvents, etc.).

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

Consulte Datos de contexto.

**clearVars**: Quita los valores de las siguientes variables en el objeto:

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

Sintaxis:

`void clearVars()`

Ejemplos:
`measure.clearVars();`

**Seguimiento sin conexión**

*Nota: Para habilitar AppMeasurement sin conexión, su grupo de informes debe admitir la marca de fecha y hora.*

Las siguientes variables le permiten almacenar llamadas de medición cuando la aplicación no tiene conexión. Para habilitar AppMeasurement sin conexión, su grupo de informes debe admitir la marca de fecha y hora. Una vez que haya realizado este cambio, todas las visitas deben admitir la marca de fecha y hora o se suprimirán. Si actualmente genera informes de datos de AppMeasurement en un grupo de informes que también recopila datos de JavaScript, es posible que tenga que configurar un grupo de informes separado para AppMeasurement sin conexión para evitar la pérdida de datos.

Cuando se habilita, AppMeasurement sin conexión se comporta de esta manera:
* La aplicación envía una llamada al servidor, pero se produce un error en la transmisión de datos.
* AppMeasurement genera una marca de fecha y hora para la visita actual.
* AppMeasurement almacena en el búfer los datos de la visita y realiza una copia de seguridad de esos datos para un almacenamiento persistente para evitar la pérdida de datos.

En cada una de las visitas posteriores o en el intervalo definido por offlineThrottleDelay, AppMeasurement intenta enviar los datos de la visita almacenados en el búfer, manteniendo el orden de la visita original. Si se produce un error en la transmisión de datos, continúa almacenando en el búfer los datos de la visita (continúa aunque el dispositivo esté sin conexión).

### Métodos de configuración

**setOfflineTrackingEnabled**: El valor predeterminado es false. Habilita o deshabilita el seguimiento sin conexión para la biblioteca de medición.

Sintaxis:

`void setOfflineTrackingEnabled(boolean Enabled);`

Ejemplos:
"measure.setOfflineTrackingEnabled(true);

**setOfflineHitLimit**: El valor predeterminado es 1000. Número máximo de visitas sin conexión almacenadas en la cola. Si se define un límite de más de 5000 visitas, el rendimiento puede verse afectado.

Sintaxis:

`void setOfflineHitLimit(int offlineHitLimit)`

Ejemplos:

`measure.setOfflineHitLimit(2000);`

**getTrackingQueueSize**: Devuelve el número de llamadas de seguimiento almacenadas en la cola sin conexión.

Sintaxis:

`int getTrackingQueueSize()`

Ejemplos:

`int size = measure.getTrackingQueueSize();`

**clearTrackingQueue**: Quita todas las llamadas de seguimiento almacenadas de la cola sin conexión.

Sintaxis:

`void clearTrackingQueue()`

Ejemplos:

`measure.clearTrackingQueue();`

**Advertencia: Tenga cuidado al borrar la cola manualmente ya que la eliminación no puede revertirse.**


**setOnline y setOffline**: Establezca manualmente el estado en línea o sin conexión del objeto de medición. La biblioteca detecta automáticamente si el dispositivo está en línea o sin conexión, de modo que estos métodos solo son necesarios si quiere forzar la medición sin conexión. SetOnline se utiliza solo para volver al estado en línea después de haber pasado manualmente al estado sin conexión.

Cuando la medición está sin conexión:

* Si offlineTrackingEnabled es verdadero: las visitas se almacenan hasta que la medición esté en línea.
* Si offlineTrackingEnabled es falso: se descartan las visitas.

Sintaxis:

```
void setOnline()
void setOffline()
```

Ejemplos:

```
measure.setOffline();
measure.setOnline();
```

## Seguimiento sin conexión

AppMeasurement le permite medir el uso de una aplicación incluso cuando el dispositivo Android esté sin conexión.

*Nota: Para habilitar AppMeasurement sin conexión, su grupo de informes debe admitir la marca de fecha y hora.*

Consulte Seguimiento sin conexión.

## Target

Adobe permite entregar contenido de destino en aplicaciones de Android.

El contenido que Test&amp;Target devuelve puede ser cualquier contenido basado en texto, como HTML, XML o texto sin formato. Cuando el contenido se haya cargado, el programador de la aplicación de Android es quien decide cómo se va a usar en dicha aplicación. El contenido se puede mostrar como HTML o se puede utilizar para cambiar el comportamiento de la aplicación. Esta guía proporciona un ejemplo simple de uso de las clases Test&amp;Target.

Requisitos

* JDK 5/6/7
* Android SDK para plataforma 1.5 o superior.

El ejemplo de esta sección está basado en Eclipse.

**Obtención de la biblioteca**

Visite Medición y optimización de las aplicaciones móviles en Developer Connection para descargar la biblioteca de Android.

Una vez descomprimido el archivo descargado, tendrá los siguientes componentes de software:

* admsAppLibrary.jar: biblioteca diseñada para utilizarse con los simuladores y dispositivos Android. Requiere Android 2.0 o una versión posterior.
* Examples\TrackingHelper.java: clase opcional diseñada para mantener el código de seguimiento separado de la lógica de aplicación.

**Añadir la biblioteca al proyecto**

1. En Eclipse IDE, haga clic con el botón secundario en el nombre del proyecto.
1. Seleccione Ruta de compilación &gt; Agregar archivos externos.
1. Seleccione admsAppLibrary.jar.
1. Haga clic en Abrir.
1. Vuelva a hacer clic con el botón secundario en el proyecto y, a continuación, seleccione Ruta de compilación &gt; Configurar ruta de compilación.
1. Haga clic en la ficha Order and Export (Pedir y exportar).
1. Asegúrese de seleccionar admsAppLibrary.jar.

La aplicación puede importar las clases e interfaces de la biblioteca admsAppLibrary.jar mediante `importcom.adobe.ADMS.*;`

**Agregar permisos de aplicaciones**

La biblioteca AppMeasurement requiere los siguientes permisos para enviar datos y registrar llamadas de seguimiento sin conexión:

* INTERNET
* ACCESS_NETWORK_STATE

Para agregar estos permisos, agregue las siguientes líneas al archivo AndroidManifest.xml (en el directorio del proyecto de la aplicación):

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

Ejemplo

Después de agregar la biblioteca al proyecto y agregar permisos de aplicación, puede usar las dos clases de Test&amp;Target, MboxFactory y Mbox.

En el siguiente ejemplo se muestra cómo cargar contenido HTML desde Test&amp;Target en WebView desde una simple aplicación Android. En este ejemplo se asume que las ofertas y la campaña de la HTML asociada ya se han creado en la herramienta de administración de Test&amp;Target y que la campaña ha sido aprobada.

1. Complete los pasos de Implementación y, a continuación, importe el paquete testandtarget a la parte superior de la subclase de la aplicación o de la actividad:

   `com.adobe.adms.testandtarget.*;`

2. Utilice el siguiente código numerado para crear un mbox (vea los comentarios para obtener una explicación de cada una de las líneas). Para completar este paso, debe saber su código de cliente y el nombre del mbox utilizado en la configuración de la campaña en la herramienta de administración de Test&amp;Target.

   ```
   public class AndroidDemoApplication extends Activity {
   private WebView _webView;
   public void onCreate(Bundle savedInstanceState) {
   super.onCreate(savedInstanceState);
   _webView = new WebView(this);
   setContentView(_webView);
   // 1. Create an instance of the MboxFactory class with your client code.
   MboxFactory factory = new MboxFactory("androiddemo16");
   // 2. Use the MboxFactory instance to create an Mbox.
   Mbox mbox = factory.create("DemoApp");
   // 3. Set the default content for the Mbox.
   mbox.setDefaultContent("<h1>DEFAULT CONTENT</h1>");
   /**
   * 4. Create a custom MboxContentConsumer to consume the content returned. The
   * CustomMboxContentConsumer class defined below simply displays the content
   * returned in a BrowserField as HTML.
   */
   CustomConsumer consumer = new CustomConsumer(_webView);
   mbox.addOnLoadConsumer(consumer);
   // 5. Load the Mbox.
   mbox.load();
   ...
   ```

3. Defina la clase personalizada que implementa la interfaz MboxContentConsumer. Esta interfaz abstracta solo requiere que defina un método denominado “consume” en el que pasar contenido. La clase CustomConsumer definida a continuación muestra el contenido en una WebView.

   ```
   class CustomConsumer implements MboxContentConsumer {
   private WebView _view;
   public CustomConsumer(WebView webview) {
   _view = webview;
   }
   public void consume(String content) {
   _view.loadData(content, "text/html", "utf-8");
   }
   }
   ```

4. Haga clic con el botón secundario en el proyecto y seleccione Ejecutar como &gt; Aplicación Android para generar y probar la aplicación. Si ha configurado y aprobado correctamente la campaña de Test&amp;Target, debería ver su oferta en el emulador de dispositivo Android.

**Métricas del ciclo vital**

Si las métricas del ciclo vital están habilitadas, se envían como parámetros a cada carga de mbox.

* (Recomendado) Seguimiento de eventos del ciclo vital
* Métricas del ciclo vital

## Gestión de público

Adobe permite enviar señales y recuperar segmentos del visitante a partir de la gestión de público.

### Requisitos

* JDK 5/6/7
* Android SDK para plataforma 1.5 o superior.

El ejemplo de esta sección está basado en Eclipse.

### Obtención de la biblioteca

Visite Medición y optimización de las aplicaciones móviles en Developer Connection para descargar la biblioteca de Android.

Una vez descomprimido el archivo descargado, tendrá los siguientes componentes de software:

* admsAppLibrary.jar: biblioteca diseñada para utilizarse con los simuladores y dispositivos Android. Requiere Android 2.0 o una versión posterior.
* Examples\TrackingHelper.java: clase opcional diseñada para mantener el código de seguimiento separado de la lógica de aplicación.

### Añadir la biblioteca al proyecto

1. En Eclipse IDE, haga clic con el botón secundario en el nombre del proyecto.
1. Seleccione Ruta de compilación &gt; Agregar archivos externos.
1. Seleccione admsAppLibrary.jar.
1. Haga clic en Abrir.
1. Vuelva a hacer clic con el botón secundario en el proyecto y, a continuación, seleccione Ruta de compilación &gt; Configurar ruta de compilación.
1. Haga clic en la ficha Order and Export (Pedir y exportar).
1. Asegúrese de seleccionar admsAppLibrary.jar.

La aplicación puede importar las clases e interfaces de la biblioteca admsAppLibrary.jar mediante `importcom.adobe.ADMS.*;`

### Añadir permisos de aplicaciones

La biblioteca AppMeasurement requiere los siguientes permisos para enviar datos y registrar llamadas de seguimiento sin conexión:
* INTERNET
* ACCESS_NETWORK_STATE

Para agregar estos permisos, agregue las siguientes líneas al archivo AndroidManifest.xml (en el directorio del proyecto de la aplicación):

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### Ejemplo de código

Después de agregar la biblioteca al proyecto, puede usar la clase ADMS_AudienceManager. To import the audience manager package add: `import com.adobe.adms.audiencemanager;`

1. Configure la gestión de público:

   `ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

   Reemplace mycompany.demdex.net por su extremo. La gestión de público se puede configurar en cualquier punto de la aplicación.


2. Opcionalmente se pueden configurar el dpid y el dpuuid.

   `ADMS_AudienceManager.SetDpidAndDpuuid("284", "abc123");`

3. Cree un diccionario de características y envíelo en una señal.

```
HashMap<String, Object> data = new HashMap<String, Object>();
data.put("trait", "b");
ADMS_AudienceManager.SubmitSignal(data, new
ADMS_AudienceManager.AudienceManagerCallback<HashMap>() {
@Override
public void call(HashMap visitorProfile) {
// do things with visitorProfile
}
});
```

El diccionario de perfiles del visitante se devuelve en la rellamada como parámetro content.

### Métricas del ciclo vital

Si las métricas del ciclo vital se habilitan y la gestión de público se configura en application:didFinishLaunchingWithOptions:, se envía una señal con métricas del ciclo vital al completar la configuración.

* (Recomendado) Seguimiento de eventos del ciclo vital
* Métricas del ciclo vital

### Referencia de ADMS_AudienceManager

**Métodos**

**ConfigureAudienceManager**: Establece el punto final de gestión de público.

Sintaxis:

`public static void ConfigureAudienceManager(String server, Context context);`

Ejemplo:

`ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

**GetDebugLogging**: Devuelve un valor booleano que indica si los métodos de Audience Manager proporcionarán o no un registro de depuración en la consola.

Sintaxis:

`public static boolean GetDebugLogging();`

**GetDpid**: Devuelve el dpid.

Sintaxis:

`public static String GetDpid();`

**GetDpuuid**: Devuelve el dpuuid.

Sintaxis:

`public static String GetDpuuid();`

**GetVisitorProfile**: Este método se puede llamar en cualquier momento después de enviar una señal para recuperar el perfil del visitante más reciente.

El perfil del visitante contiene pares de valor clave que se devolvieron en el objeto stuff.

Sintaxis:

`public static HashMap GetVisitorProfile();`

**SetDebugLogging**: Habilita o deshabilita el registro de depuración en la consola.

Sintaxis:

`public static void SetDebugLogging(boolean logging);`

**SetDpidAndDpuuid**: Si se establecen newDpid y newDpuuid, se enviarán con cada señal.

Sintaxis:

`public static void SetDpidAndDpuuid(String newDpid, String newDpuuid);`

**SubmitSignal**: Envía un diccionario de características y recibe el perfil de visitante actualizado en llamada de retorno.

El uuid de la respuesta JSON se almacena internamente y se utiliza con todas las señales siguientes. También se envía una solicitud de píxel a cada URL encontrada en el objeto dests.

Sintaxis:

```
public static void SubmitSignal(HashMap<String, Object> data,
AudienceManagerCallback<HashMap> callback);
```

### Interfaces

**Métodos**


**AudienceManagerCallback**

Sintaxis:

```
public interface AudienceManagerCallback<T> {
AudienceManagerCallback
public void call(T item);
}
```

Interfaz para el objeto utilizado en la rellamada de la llamada SubmitSignal.


## Complemento PhoneGap

Este complemento le permite enviar llamadas de AppMeasurement de Android desde el proyecto de PhoneGap.

Si desea obtener ayuda para crear un proyecto de PhoneGap, consulte Introducción de PhoneGap con Android.

Para descargar el complemento, consulte Complementos de PhoneGap de iOS y Android para SiteCatalyst.

### Incluir el complemento

1. Copie ADMS_plugin.java en el paquete de la carpeta src.
2. Copie ADMS_Helper.js en la carpeta assets/www/js de su proyecto de PhoneGap.
3. En la carpeta res/xml, abra el archivo config.xml y registre un nuevo controlador creando un nuevo nodo secundario en plugins: `<plugin name="ADMS_Plugin" value="[YOUR_PACKAGE_NAME].ADMS_plugin" />`

Por ejemplo, si el paquete se llama com.ejemplo.phonegaptest, el nodo del controlador sería el siguiente: `<plugin name="ADMS_Plugin" value="com.example.phonegaptest.ADMS_plugin" />`

### Incluir la biblioteca de AppMeasurement

Para descargar la biblioteca de AppMeasurement, consulte Obtención de la biblioteca.

1. Copie admsAppLibrary.jar en la carpeta libs de su proyecto de PhoneGap.
2. Compruebe que admsAppLibrary.jar esté en su ruta de compilación haciendo clic con el botón secundario en libs &gt; Ruta de compilación &gt; Configurar ruta de compilación.
3. En la ficha Bibliotecas, si aún no está en la lista, haga clic en Agregar JAR y seleccione admsAppLibrary.jar en la carpeta de bibliotecas.


### Seguimiento automático de métricas del ciclo vital

Rastrear las Métricas del ciclo vital requiere una configuración externa a PhoneGap. Para habilitar el seguimiento automático de ciclo vital, complete los pasos de Implementación en Inicio rápido para programadores.

### Uso del complemento

En los archivos html de los cuales quiera realizar un seguimiento, incluya:

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

Y ya está, todo preparado para realizar llamadas de medición. Consulte Métodos del complemento PhoneGap.

### Resolución de problemas

**Mi sintaxis es correcta, ¿por qué no llega al código del complemento?**

Compruebe si aparece el siguiente error en la consola de salida: `java.lang.ClassNotFoundException: ADMS_plugin`

Si se produce este error, asegúrese de que ha realizado el paso 3 en la sección Incluir el complemento.

## Métodos del complemento PhoneGap

En los archivos html en los cuales desee usar estos métodos, incluya:

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

**Métodos de configuración**


**configureMeasurementWithReportSuiteIDsTrackingServer**: Este método se utiliza para configurar los dos parámetros necesarios para iniciar la medición de aplicaciones. Debe establecer los valores reportSuiteIDs y trackingServer en el objeto de medición mediante este método antes de enviar llamadas al servidor.

Sintaxis:

`void configureMeasurementWithReportSuiteIDsTrackingServer(stringreportSuiteIDs, string trackingServer);`

Ejemplo:

`ADMS.configureMeasurementWithReportSuiteIDsTrackingServer("testRSID","10.20.40.199:5050");`

**setOnline y setOffline**: Establezca manualmente el estado en línea o sin conexión del objeto de medición. La biblioteca detecta automáticamente si el dispositivo está en línea o sin conexión, de modo que estos métodos solo son necesarios si quiere forzar la medición sin conexión. SetOnline se utiliza solo para volver al estado en línea después de haber pasado manualmente al estado sin conexión.

Cuando la medición está sin conexión:

* Si offlineTrackingEnabled es verdadero: las visitas se almacenan hasta que la medición esté en línea.
* Si offlineTrackingEnabled es falso: se descartan las visitas.

Sintaxis:

```
void setOnline();
void setOffline();
```

Ejemplo:

```
ADMS.setOnline();
ADMS.setOffline();
```

**setDebugLogging**: Habilita (true) o deshabilita (false) la vista de información de depuración. De manera predeterminada, esta variable tiene el valor false.

No puede sobrescribir esta variable utilizando las sobrescrituras de variables.

Sintaxis:

`void setDebugLogging(bool debugLogging);`

Ejemplo:

`ADMS.setDebugLogging(true);`

### Métodos de seguimiento de estado y eventos


**trackAppState**: Es la forma recomendada de rastrear los estados de la aplicación (por ejemplo, las páginas) en la aplicación. El valor proporcionado en appState se muestra como la variable del nombre de página de la llamada al servidor. La cadena appState debe proporcionarse para cada llamada, ya que no se transfiere a la siguiente llamada.

Sintaxis:

`void trackAppState(string stateName);`

Ejemplo:

`ADMS.trackAppState("login page");`

**trackAppStateWithContextData**: Es la forma recomendada de rastrear los estados de la aplicación (por ejemplo, las páginas) en la aplicación. El valor proporcionado en appState se muestra como la variable del nombre de página de la llamada al servidor. La cadena appState debe proporcionarse para cada llamada, ya que no se transfiere a la siguiente llamada.

Los datos de contexto enviados con esta llamada se anexan a cualquier valor en persistentContextData y se envían con la llamada. Solo los valores configurados en persistentContextData permanecen para la siguiente llamada.

Sintaxis:

`void trackAppStateWithContextData(string stateName, JSON cData);`

cData: objeto JSON con pares de clave-valor para enviar en los datos de contexto.

Ejemplo:

```
trackAppStateWithContextData("login page",
{"user":"john","remember":"true"});
```

**trackEvents**: Es la forma recomendada de rastrear eventos en la aplicación. trackEvents es similar a trackAppState, pero envía eventos en lugar de nombres de página. Los eventos se proporcionan como una cadena delimitada por comas trackEvents. La cadena events debe proporcionarse para cada llamada, ya que no se transfiere a la siguiente llamada.

Este método realiza una llamada subyacente a trackLinkURL donde linkURL se establece en nulo, linkType se define en "o" y linkName se completa con el ID de la aplicación.

Esto significa que linkTrackVars y linkTrackEvents se aplican para llamadas a `trackEvents`.

Sintaxis:

`void trackEvents(string eventNames);`

Ejemplo:

`ADMS.trackEvents("login,event2");`

**Nota de importación si usa el método trackLink**

`trackEvents` hace una llamada subyacente a trackLinkURL donde linkURL se define como null, linkType se define como "o" y linkName se completa con la ID de la aplicación. Esto se hace para evitar que el recuento de vistas de la página (vista de estado) incremente cada vez que se rastrea un evento.

Si llama directamente a trackLinkURL y configura los valores para linkTrackVars y linkTrackEvents, estas restricciones de variables y eventos se aplican a TrackEvents. Esto significa que solo las variables y los eventos definidos en estas listas se envían con TrackEvents. Debería configurar linkTrackVars y linkTrackEvents en nulo a no ser que quiera que esas restricciones se apliquen a trackEvents.

**trackEventsWithContextData**: Es la forma recomendada de rastrear eventos en la aplicación. trackEvents es similar a trackAppState, pero envía eventos en lugar de nombres de página. Los eventos se proporcionan como una cadena delimitada por comas. La cadena events debe proporcionarse para cada llamada, ya que no se transfiere a la siguiente llamada.

Este método hace una llamada subyacente a trackLinkURL donde linkURL se define como null, linkType se define como "o" y linkName se completa con la ID de la aplicación.

Esto significa que linkTrackVars y linkTrackEvents se aplican para llamadas a trackEvents.

Los datos de contexto enviados con esta llamada se anexan a cualquier valor en persistentContextData y se envían con la llamada. Solo los valores configurados en persistentContextData permanecen para la siguiente llamada.

Sintaxis:

`void trackEventsWithContextData(string eventNames, JSON cData);`

cData: objeto JSON con pares de clave-valor para enviar en los datos de contexto.

Ejemplo:

`ADMS.trackEventsWithContextData("login,event2",
{"user":"john","remember":"true"});`

**Nota de importación si usa el método trackLink**

trackEvents hace una llamada subyacente a trackLinkURL donde linkURL se define como null, linkType se define como "o" y linkName se completa con la ID de la aplicación. Esto se hace para evitar que el recuento de vistas de la página (vista de estado) incremente cada vez que se rastrea un evento.

Si llama directamente a trackLinkURL y configura los valores para linkTrackVars y linkTrackEvents, estas restricciones de variables y eventos se aplican a TrackEvents. Esto significa que solo las variables y los eventos definidos en estas listas se envían con TrackEvents. Debería configurar linkTrackVars y linkTrackEvents en nulo a no ser que quiera que esas restricciones se apliquen a trackEvents.

**Métodos de seguimiento avanzados (track y trackLink)**

Estos métodos proporcionan opciones de seguimiento adicionales que le permiten completar directamente props, eVars y otras variables de SiteCatalyst. Deberían ser usados por clientes con una implementación existente o clientes muy familiarizados con otras implementaciones de SiteCatalyst.

`track` y `trackLink` son los principales métodos de medición que se implementan en todas las versiones de las bibliotecas de medición de Adobe en múltiples plataformas. En la mayoría de las circunstancias, al rastrear aplicaciones móviles es más fácil utilizar los métodos trackAppState y trackEvents que llamar directamente a las funciones track y trackLink.

El seguimiento de vista de páginas (track) y el seguimiento de vínculos (trackLink) envían todas las variables persistentes que tengan algún valor (no nulo, no vacío, no cero). Debe restaurar o vaciar todas las variables, según sea necesario, antes de llamar a track o a trackLink.

**Métodos**

**track**: Envía una vista de página estándar, junto con cualquier variable adicional que se establezca en el objeto de medición, al servidor de recopilación.

Sintaxis:

`void track();`

Ejemplo:

`ADMS.track();`

**trackWithContextData**: Envía una vista de página estándar, junto con cualquier variable adicional que se establezca en el objeto de medición, al servidor de recopilación.

Cada llamada a trackWithContextData envía todos los datos persistentes definidos en el objeto de medición (se enumeran en la descripción de clearVars), además de todos los contextData que proporcione solo para esa llamada.

Sintaxis:

`void trackWithContextData(JSON cData);`

cData: objeto JSON con pares de clave-valor para enviar en los datos de contexto.

Ejemplo:

`ADMS.trackWithContextData({"key1":"value1","key2":"value2"});`


**trackWith ContextDataAndVariables**: Envía una vista de página estándar, junto con cualquier variable adicional que se establezca en el objeto de medición, al servidor de recopilación.

Cada llamada a trackWithContextDataAndVariables envía todos los datos persistentes definidos en el objeto de medición (se enumeran en la descripción de clearVars), además de todos los contextData y variables que proporcione solo para esa llamada. Si envía una variable que está definida, se sobrescribirá cualquier valor en la correspondiente variable persistente.

Sintaxis:

`void trackWithContextDataAndVariables(JSON cData, JSON vars);`

cData: objeto JSON con pares de clave-valor para enviar en los datos de contexto.

Ejemplo:

```
ADMS.trackWithContextDataAndVariables({"key1":"value1","key2":"value2"},
{"eVar1":"newValue","prop3":"newValue"});
```

**trackLinkURLWithLinkTypeName**: Envía datos de vínculos de salida, de descarga o personalizados a los servidores de recopilación de datos de Adobe, junto con cualquier variable de configuración de seguimiento que tenga algún valor.

Utilice trackLink para rastrear toda actividad que no deba capturar una vista de página.

Cada llamada a trackLinkURLWithLinkTypeNameContextDataVariables envía todos los datos persistentes definidos en el objeto de medición (se enumeran en la descripción de clearVars), además de todos los contextData que proporcione solo para esa llamada.

Sintaxis:

```
void trackLinkURLWithLinkTypeNameContextDataVariables(string`
linkUrl, string linkType, string linkName, JSON cData, JSON vars);
```

cData: objeto JSON con pares de clave-valor para enviar en los datos de contexto.

Ejemplo:

```
ADMS.trackLinkURLWithLinkTypeNameContextDataVariables("theLink",
"o", "logout", {"key1":"value1"}, {"eVar1":"newValue"});
```

### Establecer y obtener variables de AppMeasurement

**Métodos**

**setEvarToValue**: Establece la eVar especificada en el valor proporcionado. La eVar se envía con la siguiente llamada de seguimiento.

Sintaxis:

`void setEvarToValue(int evar, string value);`

Ejemplo:

`ADMS.setEvarToValue(1, "newValue");`

**setPropToValue**: Establece la prop especificada en el valor proporcionado. La prop se envía con la siguiente llamada de seguimiento.

Sintaxis:

void setPropToValue(int prop, valor de cadena);

Ejemplo:

`ADMS.setPropToValue(1, "newValue");`

**setHierToValue**: Establece la variable hier especificada en el valor proporcionado. La variable se envía con la siguiente llamada de seguimiento.

Sintaxis:

`void setHierToValue(int hier, string value);`

Ejemplo:

`ADMS.setHierToValue(1, "newValue");`

**setListVarToValue**: Establece la lista de variables especificada en el valor proporcionado. La lista de variables se envía con la siguiente llamada de seguimiento.

Sintaxis:

`void setListVarToValue(int list, string value);`

Ejemplo:

`ADMS.setListVarToValue(1, "newValue");`

**getEvar**: Obtiene la variable especificada.

Sintaxis:

`void getEvar(int evar, function success, function fail);`

Ejemplo:

```
ADMS.getEvar(1, function (value) { myTempEvar1 = value; }, function ()
{ myTempEvar1 = null; });
```

**getProp**: Obtiene la variable especificada.

Sintaxis:

`void getProp(int prop, function success, function fail);`

Ejemplo:

```
ADMS.getProp(1, function (value) { myTempProp1 = value; }, function ()
{ myTempProp1 = null; });
```

**getHier**: Obtiene la variable especificada.

Sintaxis:

`void getHier(int hier, function success, function fail);`

Ejemplo:

```
ADMS.getHier(1, function (value) { myTempHier1 = value; }, function ()
{ myTempHier1 = null; });
```

**getListVar**: Obtiene la variable especificada.

Sintaxis:

`void getListVar(int list, function success, function fail);`

Ejemplo:

```
ADMS.getListVar(1, function (value) { myTempListVar1 = value; }, function
() { myTempListVar1 = null; });
```

**clearVars**: Quita los valores de las siguientes variables en el objeto:

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

Sintaxis:

`void clearVars();`

Ejemplo:

`ADMS.clearVars();`

**trackingQueueSize**: Obtiene o establece el número de llamadas de seguimiento almacenadas en la cola sin conexión.

Sintaxis:

`void trackingQueueSize(function success, function fail);`

Ejemplo:

`ADMS.trackingQueueSize(function (value) { myQueueSize = value; }, function () { myQueueSize = 0; });`

**clearTrackingQueue**: Quita todas las llamadas de seguimiento almacenadas de la cola sin conexión. Advertencia: Tenga cuidado al borrar la cola manualmente ya que la eliminación no puede revertirse.

Sintaxis:

`void clearTrackingQueue();`

Ejemplo:

`ADMS.clearTrackingQueue();`

### Establecer y obtener variables de configuración

**Métodos**

**getVersion**: Obtiene la versión de la biblioteca.

Sintaxis:

`void getVersion(function success, function fail);`

Ejemplo:

```
ADMS.getVersion(function (value) { versionNum = value; }, function ()
{ versionNum = 1.0; });
```

**setReportSuiteIDs**: (Requerido) El grupo de informes o los grupos de informes (etiquetado de grupos múltiples) que desea rastrear. Para rastrear grupos de informes múltiples, pase una lista delimitada por comas de los nombres de cada grupo de informes.

No puede sobrescribir esta variable para una sola llamada, debe cambiar el valor persistente.

Sintaxis:
`void setReportSuiteIDs(string reportSuiteIDs);`

Ejemplo:

`ADMS.setReportSuiteIDs("rsid1, rsid2");`

**setTrackingServer**: (Requerido) Identifica el servidor de recopilación.

Esta variable debe completarse con el valor que ha generado en el Administrador de códigos.

Se utiliza el mismo valor para un seguimiento seguro si se ha habilitado ssl.

No puede sobrescribir esta variable para una sola llamada, debe cambiar el valor persistente.

Sintaxis:

`void setTrackingServer(string trackingServer);`

Ejemplo:

`ADMS.setTrackingServer("10.23.52.191:5923");`

**setDataCenter**:

Sintaxis:

`void setDataCenter(string dataCenter);`

Ejemplo:

`ADMS.setDataCenter("myDataCenter");`

**setVisitorID**: El valor predeterminado es CFUUID.

Identificación única para cada visitante. Si no define una visitorID, se generará una visitorID única (mediante CFUUID de Apple) la primera vez que se inicie y se almacenará en una clave predeterminada de usuario. A partir de ese momento, AppMeasurement y PhoneGap utilizarán esta clave. Esta clave también se guarda y se restaura durante el proceso de copia de seguridad de la aplicación estándar.

Sintaxis:

`void setVisitorID(string visitorId);`

Ejemplo:

`ADMS.setVisitorID("myVisitorId");`

**setCharSet**: El valor predeterminado es UTF-8.

Sintaxis:

`void setCharSet(string charSet);`

Ejemplo:

`ADMS.setCharSet("UTF-8");`

**setCurrencyCode**: El valor predeterminado es ninguno (se utiliza el valor definido para el grupo de informes).

El código de divisa usado para compras o eventos de divisa que se rastrean en la aplicación iOS.

Sintaxis:

`void setCurrencyCode(string currencyCode);`

Ejemplo:

`ADMS.setCurrencyCode("USD");`


**setSSLEnabled**: Defaultis false.

Habilita (true) o deshabilita (false) el envío de datos de medición a través de SSL (HTTPS). No puede sobrescribir esta variable para una sola llamada, debe cambiar el valor persistente.

Sintaxis:

`void setSSLEnabled(bool sslEnabled);`

Ejemplo:

`ADMS.setSSLEnabled(false);`

### Establecer y obtener variables de seguimiento persistente

**Métodos**

**setPurchaseID**:

Sintaxis:

`void setPurchaseID(string purchaseId);`

Ejemplo:

`ADMS.setPurchaseID("purchase1");`

**setTransactionID**:

Sintaxis:

`void setTransactionID(string transactionId);`

Ejemplo:

`ADMS.setTransactionID("transaction1");`

**setAppState**:

Sintaxis:

`void setAppState(string stateName);`

Ejemplo:

`ADMS.setAppState("myAppState");`

**setChannel**:

Sintaxis:

`void setChannel(string channel);`

Ejemplo:

`ADMS.setChannel("myChannel");`

**setAppSection**:

Sintaxis:

`void setAppSection(string appSection);`

Ejemplo:

`DMS.setAppSection("myAppSection");`

**setCampaign**:

Sintaxis:

`void setCampaign(string campaign);`

Ejemplo:

`ADMS.setCampaign("myCampaign");`

**setProducts**:

Sintaxis:

`void setProducts(string products);`

Ejemplo:

`ADMS.setProducts("myProduct1,myProduct2");`

**setEvents**:

Sintaxis:

`void setEvents(string events);`

Ejemplo:

`ADMS.setEvents("event1, event2");`

**setGeoState**

Sintaxis:

`void setGeoState(string state);`

Ejemplo:

`ADMS.setGeoState("FL");`

**setGeoZip**:

Sintaxis:

`void setGeoZip(string zip);`

Ejemplo:

`ADMS.setGeoZip("39984");`

**setPersistentContextData**: Los datos de contexto son la manera recomendada de recopilar datos. Para enviar datos de contexto, cree un objeto JSON y asigne pares de valor clave para los valores que quiera enviar.

Sintaxis:

`void setPersistentContextData(JSON cData);`

Ejemplo:

`ADMS.setPersistentContextData({"key1":"value1"});`

**persistentContextData**:

Sintaxis:

`void persistentContextData(function success, function fail);`

Ejemplo:

```
ADMS.persistentContextData(function(value) { alert(value); },
function(error) { alert(error); });
```

**setLinkTrackVars**: Lista delimitada por comas de nombres de variables que restringe el conjunto actual de variables para el seguimiento de vínculos.

Si no se define linkTrackVars, el complemento PhoneGap envía todas las variables definidas con una llamada de trackLink.

Sintaxis:

`void setLinkTrackVars(string linkTrackVars);`

Ejemplo:

`ADMS.setLinkTrackVars("eVar1,eVar2");`


**setLinkTrackEvents**: Lista de eventos delimitada por comas que restringe el conjunto actual de eventos para el seguimiento de vínculos. Si no se define linkTrackEvents, el complemento PhoneGap envía todas las variables definidas con una llamada de trackLink.

Sintaxis:

`void setLinkTrackEvents(string linkTrackEvents);`

Ejemplo:

`ADMS.setLinkTrackEvents("event1,loginEvent");`


**setLightTrackVars**: Lista de variables delimitada por comas que restringe el conjunto actual de variables para llamadas de seguimiento livianas. Las variables que envíe con una llamada al servidor liviana son configuradas por ClientCare.

Sintaxis:

`void setLightTrackVars(string lightTrackVars);`

Ejemplo:

`ADMS.setLightTrackVars("prop1,hier3");`

### Seguimiento sin conexión

**Métodos**

**setOfflineTrackingEnabled**:

Sintaxis:

`void setOfflineTrackingEnabled(bool offlineTrackingEnabled);`

Ejemplo:

`ADMS.setOfflineTrackingEnabled(true);`

**setOfflineHitLimit**:

Sintaxis:

`void setOfflineHitLimit(int offlineHitLimit);`

Ejemplo:

`ADMS.setOfflineHitLimit(3000);`

## Guía de migración de la versión de Android 2.x a 3.x

* AppMeasurement es ahora ADMS_Measurement . Busque las ubicaciones en las que hace referencia a esta clase y actualice el nombre a ADMS_Measurement.
* getInstance es ahora sharedInstance. Busque las ubicaciones en las que llama a getInstance y reemplácelo por sharedInstance.
* Elimine todas las llamadas para producir mediciones (getChurnInstance). El seguimiento automático administra estas llamadas y ahora las variables se insertan mediante datos de contexto.
* Se elimina Timestamp. La biblioteca administra automáticamente las marcas de fecha y hora.

La sintaxis de los siguientes métodos ha cambiado. Hay ejemplos actualizados para todas las propiedades y todos los métodos disponibles en Métodos y variables de configuración.


### Report Suite

**Versión anterior (2.1.x)**

`account`

**Versión nueva (3.x)**

`reportSuiteIDs`

### Track

**Versión anterior (2.1.x)**


`String track()`

`String track(Hashtable variableOverrides)`

**Versión nueva (3.x)**

Pasa null para valores no utilizados.

```
void track()
void track(Hashtable<String, Object>
contextData)
void track(Hashtable<String, Object>
contextData, Hashtable<String, Object>
variables)
```

### Track Link

**Versión anterior (2.1.x)**

```
String trackLink(String linkURL, String
linkType, String linkName)
```

```
String trackLink(String linkURL, String
linkType, String linkName,
Hashtable variableOverrides)
```

**Versión nueva (3.x)**

Estas dos llamadas se han reemplazado por una sola. Pasa null para valores no utilizados.

```
void trackLink(String linkURL, String linkType,
String linkName,
Hashtable<String, Object> contextData,
Hashtable<String, Object> variables)
```

### Métodos de seguimiento sin conexión

**Versión anterior (2.1.x)**

`void forceOffline();`


`void forceOnline();`

**Versión nueva (3.x)**

`void setOnline();`

`void setOffline();`


### Cambio de nombre de variables

La siguiente lista muestra las variables de la versión 2.x con sus correspondientes valores en la versión 3.x. Se han eliminado algunas variables de la versión 3.x para que la biblioteca esté más enfocada al uso móvil y para simplificar la implementación.


*Nota: La versión 3.x usa captadores y definidores en vez de variables públicas. Tendrá que actualizar las ubicaciones en su código en las que defina variables directamente para usar los métodos de establecer y obtener.*

```
timestamp; //Removed
trackOffline; //void setOfflineTrackingEnabled(boolean Enabled)
offlineLimit; //void setOfflineHitLimit(int offlineHitLimit)
account; //reportSuiteIDs
linkURL; //Removed (sent with linkTrackURL)
linkName; //Removed (sent with linkTrackURL)
linkType; //Removed (sent with linkTrackURL)
linkTrackVars; //void setLinkTrackVars(String Vars) //comma-delimited list
linkTrackEvents; //void setLinkTrackEvents(String Events) //comma-delimited list
dc; //Removed
trackingServer; //void setTrackingServer(String trackingServer)
trackingServerSecure; //Removed, trackingServer value is used for secure server if ssl=YES
userAgent; //Removed
dynamicVariablePrefix; //Removed
visitorID; //void setVisitorID(String ID)
charSet; //void setCharSet(String charSet)
visitorNamespace; //Removed
pageName; //void setAppState(String State)
pageURL; //Removed
referrer; //Removed
currencyCode; //void setCurrencyCode(String currencyCode)
purchaseID; //void setPurchaseID(String ID)
channel; //void setChannel(String Channel)
server; //void setAppSection(String Section)
pageType; //Removed
transactionID; //void setTransactionID(String ID)
campaign; //void setCampaign(String Campaign)
state; //void setGeoState(String GeoState)
zip; //void setGeoZip(String GeoZip)
events; //void setEvents(String Event) //comma-delimited list
products; //void setProducts(String Products)
list1-list3; //setListVar(int listNum, String listValue);
hier1-heir5; //setHier(int hierNum, String hierValue);
prop1-prop75; //setProp(int propNum, String propValue);
eVar1-eVar75; //setEvar(int evarNum, String evarValue);
ssl; //void setSSL(boolean ssl)
linkLeaveQueryString; //Removed
debugTracking; //debugLogging
usePlugins; //Removed
useBestPractices; //Removed - handled by Lifecycle AutoTracking
contextData; //persistentContextData
```

## Uso de Bloodhound para probar aplicaciones móviles

La herramienta Bloodhound le permite enviar llamadas al servidor a un equipo local para probar las aplicaciones móviles.

*Importante: Adobe Bloodhound expiró el 30 de abril de 2017. Desde el 1 de mayo de 2017 no se proporcionarán nuevas mejoras ni se ofrecerá más soporte técnico de ingeniería o Adobe Expert Care.*

Durante el desarrollo de la aplicación, Bloodhound le permite ver, de forma local, las llamadas al servidor y, de forma opcional, reenviar los datos a los servidores de recopilación de Adobe.

Bloodhound está disponible para Mac y Windows.

### Requisitos

* Un ordenador Mac basado en Intel con Snow Leopard (10.6) o una versión posterior o un ordenador Windows.
* Conectividad de red con los dispositivos o simuladores móviles.

### Descargar

Consulte Bloodhound - App Measurement QA Tool (Bloodhound - Herramienta de control de calidad de medición de aplicaciones) en Developer Connection (Conexión del programador).

### Instalación

* Mac: abra el dmg que descargó y arrastre Bloodhound a la carpeta Applications.
* Windows: ejecute el archivo de instalación que descargó.

### Uso de Bloodhound

Una vez que inicie la herramienta, el servidor estará desactivado hasta que haga clic en el botón Inicio. Haga clic en el botón Inicio cuando esté listo para capturar las llamadas al servidor desde su aplicación.

Asimismo, también puede especificar un número de puerto personalizado (debe ser mayor que 1024) antes de iniciar el servidor. Si no proporciona un número de puerto, el servidor seleccionará automáticamente un puerto abierto.

Cuando el servidor se esté ejecutando, tiene que configurar sus aplicaciones o dispositivos para que envíen datos a la herramienta, como se indica en la siguiente sección.

### Configuración de dispositivos para enviar visitas a Bloodhound

Puede cambiar la configuración proxy en el dispositivo para enviar solicitudes de http a la herramienta. Las solicitudes que se envían a la herramienta también se pueden reenviar de forma opcional a los servidores de recogida de datos de Adobe.

Si su dispositivo no admite un proxy, puede enviar las visitas directamente a Bloodhound para realizar pruebas.

*Nota: Bloodhound no admite el seguimiento de SSL. Debe deshabilitar SSL en la biblioteca AppMeasurement al realizar pruebas con Bloodhound.*

#### Dispositivos iOS

El dispositivo iOS debe estar en la misma red que el equipo que aloja Bloodhound.

1. Vaya a Configuración &gt; Wi-Fi.
1. Haga clic en la flecha azul situada a la derecha de su red Wi-Fi actual.
1. Desplácese hasta la configuración proxy de HTTP.
1. Seleccione Automático.
1. Introduzca la URL proxy y el puerto (desde la interfaz de usuario de Bloodhound) en el campo URL.

#### Otros dispositivos

Si el dispositivo admite la configuración automática proxy, use la URL proxy (desde la interfaz de usuario de Bloodhound) como URL de Proxy Auto Config (PAC). La compatibilidad del proxy difiere según la versión de Android y hay algunas herramientas de configuración de proxy disponibles para Android que permiten simplificar la configuración.

### Enviar visitas directamente 

En el caso de los dispositivos que no admiten proxy (el simulador de iOS, versiones anteriores de Android, etc.) se puede usar Bloodhound como servidor de seguimiento para capturar las visitas que genera. Para ello, configure el servidor de seguimiento en "<Bloodhound IP>:<BloodhoundPort>".

Por ejemplo:

```
//iOS
[measure configureMeasurementWithReportSuiteIDs:@"my_rsid" trackingServer:@"10.10.2.2:5000"];
measure.ssl = NO;
```

```
//Android
measure.configureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

```
//WinRT for Windows 8, Windows Phone 8
measure.ConfigureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

### Solución de problemas y problemas comunes

* Bloodhound solo funciona con un seguimiento no SSL. No se capturará ninguna visita de seguimiento enviada mediante SSL, con independencia del método que se haya usado anteriormente.

## Widgets de Android

Los widgets de Android se pueden rastrear usando los mismos métodos que con la aplicación. Los widgets comparten el contexto de aplicación con su aplicación, por lo que se conservan el orden de visitas y la identificación de los visitantes.

Las siguientes directrices le ayudarán a rastrear widgets de Android:

* No implemente llamadas de métricas del ciclo vital (startActivity/stopActivity) en el propio widget.
* Para realizar un seguimiento de cuándo se agrega un widget a la pantalla de inicio, agregue una llamada trackState o trackEvent al método onEnabled del widget.
* Para realizar un seguimiento de cuándo se inicia la aplicación desde un widget, agregue una llamada trackState o trackEvent antes de crear un objeto Intent para iniciar la aplicación.
* Si le interesa el seguimiento del contexto de una acción, puede definir una variable ContextData que proporcione la opción de segmentar cada una de forma independiente (por ejemplo, AppExperienceType="widget" frente a "app").
