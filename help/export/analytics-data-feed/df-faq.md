---
description: Preguntas frecuentes sobre las fuentes de datos
keywords: Fuente de datos, trabajo, columna previa, columna posterior, distinción de mayúsculas y minúsculas
title: Preguntas frecuentes sobre las fuentes de datos
feature: Data Feeds
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: a71db2fac9333b70a55da91fe9a94b0cc8434b42
workflow-type: tm+mt
source-wordcount: '1450'
ht-degree: 100%

---

# Preguntas frecuentes sobre las fuentes de datos

Preguntas frecuentes sobre las fuentes de datos.

## ¿Deben ser únicos los nombres de las fuentes? {#unique}

Los nombres de los archivos de fuente de datos se componen del ID del grupo de informes y de la fecha. Si dos fuentes están configuradas para el mismo RSID y la misma fecha, tendrán el mismo nombre de archivo. Si esas fuentes se entregan en la misma ubicación, los archivos se sobrescribirán entre sí. Para impedirlo, evite crear fuentes que puedan sobrescribir otras que ya existan en la misma ubicación.

Cuando intente crear una fuente con el mismo nombre de archivo que otra, recibirá un mensaje de error. Considere las siguientes soluciones:

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

Las fuentes de datos no incluyen bots filtrados por las [reglas de bots de la Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html?lang=es).

## ¿Por qué veo varios valores `000` en la columna de fuente de datos `event_list` o `post_event_list`? {#values}

Algunos editores de hojas de cálculo, especialmente Microsoft Excel, redondean automáticamente números muy grandes. La columna `event_list` contiene muchos números delimitados por comas, lo que a veces hace que Excel la trate como un número elevado. Se redondean los últimos dígitos a `000`.

Adobe recomienda no abrir automáticamente los archivos `hit_data.tsv` en Microsoft Excel. En su lugar, utilice el cuadro de diálogo Importar datos de Excel y asegúrese de que todos los campos se tratan como texto.

## ¿Se garantiza que columnas como `hitid_high`, `hitid_low`, `visid_high` y `visid_low` sean únicas para la visita? {#hitid}

En casi todos los casos, la concatenación de `hitid_high` y `hitid_low` identifica una visita de forma exclusiva. El mismo concepto se aplica a la concatenación de `visid_high` y `visid_low` para las visitas. Sin embargo, las anomalías de procesamiento rara vez hacen que dos visitas compartan el mismo ID. Adobe recomienda no crear flujos de trabajo de fuentes de datos que dependan de que cada visita sea única de forma inflexible.

## ¿Por qué falta información en la columna de dominio para algunos operadores? {#domain}

Algunos operadores de telefonía móvil (como T-Mobile y O1) ya no proporcionan información de dominio cuando se realiza una búsqueda de DNS inversa. Por lo tanto, los datos no se muestran en los informes de dominio.

## ¿Por qué no puedo extraer archivos por hora de datos que tengan más de 7 días? {#hourly}

Para los datos con más de 7 días de antigüedad, los archivos por hora de un día se combinan en un solo archivo diario.

Ejemplo: Se crea una nueva fuente de datos el 9 de marzo de 2021 y los datos del 1 de enero de 2021 al 9 de marzo se entregan como “Por hora”. Sin embargo, los archivos por hora de antes del 2 de marzo de 2021 se combinan en un solo archivo diario. Puede extraer archivos por hora solo de datos que tengan menos de 7 días desde la fecha de creación. En este caso, del 2 al 9 de marzo.

## ¿Cuál es el impacto del horario de verano en las fuentes de datos por hora? {#dst}

En determinadas zonas horarias, la hora cambia dos veces al año debido a las definiciones del horario de verano (DST). Las fuentes de datos respetan la zona horaria que se ha tomado como referencia para configurar el grupo de informes. Si la zona horaria del grupo de informes no utiliza DST, la entrega de archivos seguirá su curso como cualquier otro día. Si la zona horaria del grupo de informes sí utiliza DST, la entrega de archivos se verá modificada en la hora en la que se produzca el cambio de horario (normalmente a las 2 de la madrugada).

Cuando se realice la transición de STD a DST (cambio de hora estacional), el cliente solo recibirá 23 archivos. La hora que se salta en la transición a DST se omite sin más. Por ejemplo, si la transición se produce a las 2 de la madrugada, el cliente recibirá un archivo correspondiente a la 1 y un archivo correspondiente a las 3. No habrá archivo para las 2, porque las 2 STD se convierten en las 3 DST.

Cuando se realice la transición de DST a STD, el cliente recibirá 24 archivos. Sin embargo, la hora de transición en realidad incluirá datos correspondientes a dos horas. Por ejemplo, si la transición se produce a las 2 de la madrugada, el archivo de la 1 se retrasará una hora, pero incluirá datos de dos horas. Incluirá datos entre la 1 DST y las 2 STD (que habrían sido las 3 DST). El siguiente archivo comienza a las 2 STD.

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

