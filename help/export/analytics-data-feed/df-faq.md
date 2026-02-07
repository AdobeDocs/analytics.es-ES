---
description: Obtenga respuestas a las preguntas frecuentes acerca de las fuentes de datos en Adobe Analytics.
keywords: Fuente de datos, trabajo, columna previa, columna posterior, distinción de mayúsculas y minúsculas
title: Preguntas frecuentes sobre fuentes de datos
feature: Data Feeds
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: 470ab0dfa76681d73f847ba9c2aecaf64804540c
workflow-type: tm+mt
source-wordcount: '1488'
ht-degree: 73%

---

# Preguntas frecuentes sobre las fuentes de datos

Preguntas frecuentes sobre las fuentes de datos.

## ¿Deben ser únicos los nombres de las fuentes? {#unique}

Adobe Analytics no evita que se sobrescriban los archivos de fuente de datos.

Para evitar que se sobrescriban los archivos de fuente de datos, se recomienda que todos los archivos de fuente de datos que se envíen a la misma ubicación tengan nombres de archivo únicos.

Los nombres de los archivos de fuentes de datos están formados por las siguientes características de fuentes de datos:

* ID del grupo de informes (RSID)

* Fecha de exportación

Si dos fuentes están configuradas para el mismo ID de grupo de informes y la misma fecha, tendrán el mismo nombre de archivo. Si esas fuentes se entregan en la misma ubicación, los archivos se sobrescriben entre sí.

Para evitar la sobrescritura de un archivo, considere las siguientes soluciones:

* Cambiar la ruta de entrega
* Cambiar las fechas si es posible
* Cambiar el grupo de informes si es posible

## ¿Cuándo se procesan los datos? {#processed}

Antes de procesar datos por hora o por día, las fuentes de datos esperan hasta que todas las visitas que han supuesto recopilación de datos dentro del marco de tiempo (un día o una hora) se han registrado en el almacén de datos. A continuación, las fuentes de datos recopilan los datos con marcas de tiempo incluidas dentro del marco de tiempo, las comprimen y las envían por FTP. En el caso de las fuentes por hora, los archivos se suelen registrar en el almacén de datos dentro de los 15-30 minutos posteriores a la hora, pero no hay un período de tiempo definido. Si no ha habido datos con marcas de tiempo incluidas en el marco de tiempo, el proceso vuelve a intentarlo con el siguiente marco de tiempo. El proceso actual de fuente de datos utiliza el campo `date_time` para determinar las visitas que corresponden a la hora. Este campo está basado en la zona horaria del grupo de informes.

## ¿Cuál es la diferencia entre columnas con prefijo `post_` y columnas sin un prefijo `post_`? {#post}

Las columnas sin el prefijo `post_` contienen datos exactamente como se enviaron a la recopilación de datos. Las columnas con un prefijo `post_` contienen el valor después del procesamiento. Algunos ejemplos que pueden cambiar un valor son la persistencia de variables, las reglas de procesamiento, las reglas de VISTA, la conversión de divisas u otra lógica del lado del servidor que Adobe aplique. Adobe recomienda utilizar la versión `post_` de una columna siempre que sea posible.

Si una columna no contiene una versión `post_` (por ejemplo: `visit_num`), se puede considerar que es una columna posterior.

## ¿Cómo gestionan las fuentes de datos la distinción entre mayúsculas y minúsculas? {#case}

En Adobe Analytics, la mayoría de las variables se consideran sin distinción de mayúsculas y minúsculas a efectos de los informes. Por ejemplo: “nieve”, “Nieve”, “NIEVE” y “nLeve” se consideran todos como un mismo valor. La distinción entre mayúsculas y minúsculas se conserva en las fuentes de datos.

Si ve diferentes variaciones de mayúsculas y minúsculas del mismo valor entre columnas no posteriores y posteriores (por ejemplo, “nieve” en la columna previa y “Nieve” en la columna posterior), la implementación utiliza valores en mayúsculas y minúsculas en todo el sitio. Se pasó anteriormente por la variación de la distinción de mayúsculas y minúsculas en la columna posterior y se almacena en la cookie virtual, o se procesó aproximadamente en el mismo momento para el grupo de informes.

## ¿Las reglas de bots de la Admin Console filtran bots incluidos en las fuentes de datos? {#bots}

Las fuentes de datos no incluyen bots filtrados por las [reglas de bots de la Admin Console](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md).

## ¿Por qué veo varios valores `000` en la columna de fuente de datos `event_list` o `post_event_list`? {#values}

Algunos editores de hojas de cálculo, especialmente Microsoft Excel, redondean automáticamente números muy grandes. La columna `event_list` contiene muchos números delimitados por comas, lo que a veces hace que Excel la trate como un número elevado. Se redondean los últimos dígitos a `000`.

Adobe recomienda no abrir automáticamente los archivos `hit_data.tsv` en Microsoft Excel. En su lugar, utilice el cuadro de diálogo Importar datos de Excel y asegúrese de que todos los campos se tratan como texto.

## ¿Se garantiza que columnas como `hitid_high`, `hitid_low`, `visid_high` y `visid_low` sean únicas para la visita? {#hitid}

En casi todos los casos, la concatenación de `hitid_high` y `hitid_low` identifica una visita de forma exclusiva. El mismo concepto se aplica a la concatenación de `visid_high` y `visid_low` para las visitas. Sin embargo, las anomalías de procesamiento rara vez hacen que dos visitas compartan el mismo ID. Adobe recomienda no crear flujos de trabajo de fuentes de datos que dependan de que cada visita sea única de forma inflexible.

## ¿Por qué falta información en la columna de dominio para algunos operadores? {#domain}

Algunos operadores de telefonía móvil (como T-Mobile y O1) ya no proporcionan información de dominio cuando se realiza una búsqueda de DNS inversa. Por lo tanto, los datos no se muestran en los informes de dominio.

## ¿Por qué no puedo extraer de forma fiable archivos por hora para fechas más antiguas? {#hourly}

Para optimizar el almacenamiento y el procesamiento, Adobe consolida regularmente las exportaciones por hora en archivos diarios. Debido a cómo y cuándo se ejecutan estas consolidaciones, la salida por hora para fechas anteriores a 10 días no es predecible. Para una fecha determinada, es posible ver una combinación de archivos por hora durante algunas horas y un archivo diario consolidado para otros. Los datos consolidados en un archivo diario se asignan normalmente a la hora `00`, lo que puede dejar otras horas en blanco cuando esas horas se solicitan directamente.

Para los rellenos de más de 10 días, Adobe recomienda encarecidamente utilizar la granularidad diaria para garantizar resultados completos y predecibles. Si debe solicitar la granularidad horaria en días anteriores, incluya siempre la hora `00` en la solicitud para evitar que falten datos consolidados por hora.

## ¿Cuál es el impacto del horario de verano en las fuentes de datos por hora? {#dst}

En determinadas zonas horarias, la hora cambia dos veces al año debido a las definiciones del horario de verano (DST). Las fuentes de datos respetan la zona horaria que se ha tomado como referencia para configurar el grupo de informes. Si la zona horaria del grupo de informes no utiliza DST, la entrega de archivos seguirá su curso como cualquier otro día. Si la zona horaria del grupo de informes sí utiliza DST, la entrega de archivos se verá modificada en la hora en la que se produzca el cambio de horario (normalmente a las 2:00 AM).

Cuando realice las transiciones de tiempo STD -> DST (primavera hacia adelante), recibirá 23 archivos. La hora que se salta en la transición a DST se omite sin más. Por ejemplo, si la transición se produce a las 2 de la madrugada, recibirá un archivo correspondiente a la hora 1:00 y un archivo correspondiente a la hora 3:00. No hay ningún archivo de 2:00 porque, en 2:00 STD, se convierte en 3:00 DST.

Cuando realice transiciones de DST a STD (alternativa), recibirá 24 archivos. Sin embargo, la hora de transición en realidad incluirá datos correspondientes a dos horas. Por ejemplo, si la transición se produce a las 2:00 a. m., el archivo de 1:00 se retrasará una hora, pero contendrá datos durante dos horas. Contiene datos de 1:00 DST a 2:00 STD (que habrían sido 3:00 DST). El siguiente archivo comienza en 2:00 STD.

## ¿Cómo gestiona Analytics los errores de transferencia de FTP? {#ftp-failure}

Si falla una transferencia FTP (debido a un inicio de sesión denegado, una conexión perdida, un error de cuota u otro problema), Adobe intenta conectarse automáticamente y envía los datos hasta tres veces diferentes. Si no se resuelven los errores, la fuente se marca como errónea y se envía una notificación de correo electrónico.

Si una transferencia da error, puede volver a ejecutar el trabajo hasta que se realice correctamente.

Si tiene problemas para que una fuente de datos aparezca en su sitio FTP, consulte [Resolución de problemas de fuentes de datos](troubleshooting.md).

## ¿Cómo puedo reenviar un trabajo? {#resend}

Cuando haya comprobado/corregido el problema de entrega, ejecute de nuevo el trabajo para obtener los archivos.

## ¿Cuál es la configuración de BucketOwnerFullControl para las fuentes de datos de Amazon S3? {#BucketOwnerFullControl}

**BucketOwnerFullControl** proporciona derechos a varias cuentas para crear objetos en otros contenedores.

El caso de uso más habitual de Amazon S3 es que el propietario de la cuenta de los servicios web de Amazon (AWS) crea un contenedor, a continuación crea un usuario que tiene permiso para crear objetos en ese contenedor y, finalmente, proporciona credenciales para ese usuario. En este caso, los objetos de un usuario pertenecen a la misma cuenta y el propietario de la cuenta tiene implícitamente un control total del objeto (leer, eliminar, etc). Funciona de un modo similar a la entrega por FTP.

AWS también permite a los usuarios crear objetos en un contenedor que pertenece a otra cuenta de usuario completamente diferente. Por ejemplo, si dos usuarios de AWS, el usuario A y el usuario B, no pertenecen a la misma cuenta de AWS pero quieren crear objetos en otros contenedores. Si el usuario A crea un contenedor llamado “contenedorA”, puede crear una política que permita explícitamente que el usuario B cree objetos en el contenedorA, aunque el contenedor no pertenezca al usuario. Esta directiva puede ser beneficiosa porque no es necesario que el usuario A y el usuario B intercambien credenciales. En su lugar, el usuario B proporciona su número de cuenta al usuario A y este crea una política de contenedor que diga “permitir al usuario B crear objetos en el contenedorA”.

Sin embargo, los objetos no heredan permisos del contenedor principal. Por tanto, si el usuario B carga un objeto al bloque del usuario A, el usuario B todavía “posee” ese objeto y, por defecto, no se han concedido permisos al usuario A sobre ese objeto, aunque el usuario A posea el contenedor. El usuario B debe conceder permiso explícitamente al usuario A porque el usuario B sigue siendo el propietario del objeto. Para conceder este permiso, el usuario B debe cargar el objeto con un BucketOwnerFullControl ACL, que especifica que el propietario del contenedor (usuario A) tiene permisos totales para el objeto (leer, escribir, eliminar, etc.), aunque el objeto sea “propiedad” del usuario B.

>[!NOTE]
>
>Adobe Analytics no determina si el contenedor tiene una política que requiera dar al propietario del contenedor total control de nuevos objetos, o incluso si el propietario del contenedor está en una cuenta diferente a la del usuario que escribe los datos. En su lugar, Analytics agrega automáticamente el propietario del contenedor a la ACL de `BucketOwnerFullControl` con cada carga de fuente.

