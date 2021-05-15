---
description: Preguntas más frecuentes sobre las fuentes de datos
keywords: Fuente de datos;trabajo;columna previa;columna posterior;distinción entre mayúsculas y minúsculas
title: Preguntas frecuentes sobre las fuentes de datos
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: 7312b61b8d73f45afa3eb9aac73cc4d5fd39bc82
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 49%

---

# Preguntas frecuentes sobre las fuentes de datos

Preguntas más frecuentes sobre las fuentes de datos.

## ¿Deben ser únicos los nombres de las fuentes?{#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

Los nombres de los archivos de fuente de datos se componen del ID del grupo de informes y de la fecha. Si dos fuentes están configuradas para el mismo ID de grupo de informes y la misma fecha, tendrán el mismo nombre de archivo. Si esas fuentes se entregan en la misma ubicación, los archivos se sobrescriben entre sí. Para impedirlo, evite crear fuentes que puedan sobrescribir otra que ya exista en la misma ubicación.

Cuando intente crear una fuente con el mismo nombre de archivo que otra, recibirá el siguiente mensaje:

En ese caso, puede hacer lo siguiente:

* Cambiar la ruta de entrega
* Cambiar las fechas si es posible
* Cambiar el grupo de informes si es posible

## ¿Cuándo se procesan los datos? {#section_6346328F8D8848A7B81474229481D404}

Antes de procesar datos por hora o por día, las fuentes de datos esperan hasta que todas las visitas que han supuesto recopilación de datos dentro del marco de tiempo (un día o una hora) se han registrado en el almacén de datos. A continuación, las fuentes de datos recopilan los datos con marcas de tiempo incluidas dentro del marco de tiempo, las comprimen y las envían por FTP. En el caso de las fuentes por hora, los archivos se suelen registrar en el almacén de datos dentro de los 15-30 minutos posteriores a la hora, pero no hay un período de tiempo definido. Si no ha habido datos con marcas de tiempo incluidas en el marco de tiempo, el proceso vuelve a intentarlo con el siguiente marco de tiempo. El proceso actual de fuente de datos utiliza el campo `date_time` para determinar las visitas que corresponden a la hora. Este campo está basado en la zona horaria del grupo de informes.

## ¿Cuál es la diferencia entre columnas con prefijo `post_` y columnas sin un prefijo `post_`?

Las columnas sin el prefijo `post_` contienen datos exactamente como se enviaron a la recopilación de datos. Las columnas con el prefijo `post_` contienen el valor después del procesamiento. Algunos ejemplos que pueden cambiar un valor son la persistencia de variables, las reglas de procesamiento, las reglas de VISTA, la conversión de divisas u otra lógica del lado del servidor que Adobe aplique. Adobe recomienda utilizar la versión `post_` de una columna siempre que sea posible.

Si una columna no contiene una versión `post_` (por ejemplo: `visit_num`), se puede considerar que es una columna posterior.

## ¿Cómo gestionan las fuentes de datos la distinción entre mayúsculas y minúsculas?

En Adobe Analytics, la mayoría de las variables se consideran sin distinción de mayúsculas y minúsculas a efectos de los informes. Por ejemplo: “nieve”, “Nieve”, “NIEVE” y “nLeve” se consideran todos como un mismo valor. La distinción entre mayúsculas y minúsculas se conserva en las fuentes de datos.

Si ve diferentes variaciones de mayúsculas y minúsculas del mismo valor entre columnas no posteriores y posteriores (por ejemplo, “nieve” en la columna previa y “Nieve” en la columna posterior), la implementación utiliza valores en mayúsculas y minúsculas en todo el sitio. Se pasó anteriormente por la variación de la distinción de mayúsculas y minúsculas en la columna posterior y se almacena en la cookie virtual, o se procesó aproximadamente en el mismo momento para el grupo de informes.

## ¿Las reglas de bots de la Admin Console filtran bots incluidos en las fuentes de datos?

Las fuentes de datos no incluyen bots filtrados por las [reglas de bots de la Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## ¿Por qué veo varios valores `000` en la columna de fuente de datos `event_list` o `post_event_list`?

Algunos editores de hojas de cálculo, especialmente Microsoft Excel, redondean automáticamente grandes números. La columna `event_list` contiene muchos números delimitados por comas, lo que a veces hace que Excel la trate como un número elevado. Se redondean los últimos dígitos a `000`.

Adobe recomienda no abrir automáticamente los archivos `hit_data.tsv` en Microsoft Excel. En su lugar, utilice el cuadro de diálogo Importar datos de Excel y asegúrese de que todos los campos se tratan como texto.

## ¿Por qué falta información en la columna de dominio para algunos operadores? {#section_B7508D65370442C7A314EAED711A2C75}

Algunos operadores de telefonía móvil (como T-Mobile y O1) ya no proporcionan información de dominio cuando se realiza una búsqueda de DNS inversa. Por lo tanto, los datos no se muestran en los informes de dominio.

## ¿Por qué no puedo extraer archivos &quot;por hora&quot; de datos que tengan más de 7 días?

Para los datos con más de 7 días de antigüedad, los archivos &quot;por hora&quot; de un día se combinan en un solo archivo &quot;Diario&quot;.

Ejemplo: Se crea una nueva fuente de datos el 9 de marzo de 2021 y los datos del 1 de enero de 2021 al 9 de marzo se entregan como &quot;por hora&quot;. Sin embargo, los archivos &quot;Por hora&quot; anteriores al 2 de marzo de 2021 se combinan en un solo archivo &quot;Diario&quot;. Puede extraer archivos &quot;por hora&quot; solo de datos que tengan menos de 7 días desde la fecha de creación. En este caso, del 2 de marzo al 9 de marzo.

## ¿Cuál es el impacto del horario de verano en las fuentes de datos por hora? {#section_70E867D942054DD09048E027A9474FFD}

En determinadas zonas horarias, la hora cambia dos veces al año debido a las definiciones del horario de verano (DST). Las fuentes de datos respetan la zona horaria que se ha tomado como referencia para configurar el grupo de informes. Si la zona horaria del grupo de informes no utiliza DST, la entrega de archivos continúa normalmente como cualquier otro día. Si la zona horaria del grupo de informes sí utiliza DST, la entrega de archivos se modifica en la hora en la que se produzca el cambio de hora (normalmente a las 2 de la madrugada).

Cuando se realice la transición de STD a DST, el cliente solo recibirá 23 archivos. Se omite la hora omitida en la transición a DST. Por ejemplo, si la transición se produce a las 2 de la madrugada, se obtiene un archivo para la 1 y un archivo para las 3. No hay archivo de 2 porque, a las 2 STD, se convierte en 3 DST.

Cuando se realiza la transición de DST a STD, el cliente obtiene 24 archivos. Sin embargo, la hora de transición incluye datos correspondientes a dos horas. Por ejemplo, si la transición se produce a las 2 de la madrugada, el archivo de la 1 se retrasa una hora, pero contiene datos de dos horas. Contiene datos entre la 1 DST y las 2 STD (que habrían sido las 3 DST). El siguiente archivo comienza a las 2 STD.

## ¿Cómo gestiona Analytics los errores de transferencia de FTP? {#section_4BD44E9167F0494FB2B379D2BA132AD8}

En caso de que se produzca un error en la transferencia FTP (inicio de sesión denegado, pérdida de conexión, falta de cuota, etc.), el Adobe intenta conectarse automáticamente y envía los datos hasta tres veces diferentes. Si no se resuelven los errores, la fuente se marca como errónea y se envía una notificación de correo electrónico.

Si falla una transferencia, puede volver a ejecutar un trabajo hasta que se realice correctamente.

Si tiene problemas para que una fuente de datos aparezca en su sitio FTP, consulte [Resolución de problemas de trabajos](jobs-troubleshooting.md).

## ¿Cómo puedo reenviar un trabajo? {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Cuando haya comprobado/corregido el problema de entrega, ejecute de nuevo el trabajo para obtener los archivos.

## ¿Cuál es la configuración de BucketOwnerFullControl para las fuentes de datos de Amazon S3? {#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D}

El caso de uso más habitual de Amazon S3 es que el propietario de la cuenta de los servicios web de Amazon (AWS) crea un bucket, a continuación crea un usuario que tiene permiso para crear objetos en ese bucket y, finalmente, proporciona credenciales para ese usuario. En este caso, los objetos de un usuario pertenecen a la misma cuenta y el propietario de la cuenta tiene implícitamente un control total del objeto (leer, eliminar, etc.). Este proceso es similar al funcionamiento de la entrega por FTP.

AWS también permite a un usuario crear objetos en un bucket que pertenece a una cuenta de usuario diferente. Por ejemplo, si dos usuarios de AWS, el usuario A y el usuario B, no pertenecen a la misma cuenta de AWS pero quieren crear objetos en otros buckets. Si el usuario A crea un bucket, por ejemplo el bucket A, este puede crear una política que permita explícitamente que el usuario B cree objetos en el bucket A, aunque el bucket no pertenezca al usuario. Esta directiva puede ser ventajosa porque no requiere que el usuario A y el usuario B intercambien credenciales. En su lugar, el usuario B proporciona su número de cuenta al usuario A y este crea una política de bucket que diga &quot;permitir al usuario B crear objetos en el bucket A&quot;.

**BucketOwnerFullControl** proporciona derechos a varias cuentas para crear objetos en otros buckets. Si el usuario B carga un objeto en el bucket del usuario A, el usuario B sigue &quot;siendo propietario&quot; de ese objeto y, de forma predeterminada, no se concede ningún permiso al usuario A para ese objeto aunque el usuario A posea el bucket. Esto se debe a que los objetos no heredan permisos del bloque principal. El usuario B debe conceder permiso explícitamente al usuario A porque el usuario B sigue siendo el propietario del objeto. Para conceder este permiso, el usuario B debe cargar el objeto con un BucketOwnerFullControl ACL, que especifica que el propietario del bucket (usuario A) tiene permisos totales para el objeto (leer, escribir, eliminar, etc.), aunque el objeto sea &quot;propiedad&quot; del usuario B.

>[!MORELIKETHIS]
>
>* [Solución de problemas de los trabajos](jobs-troubleshooting.md)

