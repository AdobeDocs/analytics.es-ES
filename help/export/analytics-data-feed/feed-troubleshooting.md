---
description: Esta sección contiene información sobre los problemas más frecuentes.
keywords: Fuente de datos;solución de problemas
title: Solución de problemas de fuentes de datos
uuid: 4be981ab-3a61-4099-9b0d-785d2ac2492a
exl-id: 58531afe-5e0e-49b6-9c9f-9c857be8dc75
translation-type: tm+mt
source-git-commit: c6d4095fdf86be52c7921aed84b9229ac3b27f82
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 91%

---

# Solución de problemas de fuentes de datos

Esta sección contiene información sobre los problemas más frecuentes.

## Error al guardar una fuente {#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

Los nombres de los archivos de fuente de datos se componen del ID del grupo de informes y de la fecha. Si dos fuentes están configuradas para el mismo ID de grupo de informes y la misma fecha, tendrán el mismo nombre de archivo. Si esas fuentes se entregan en la misma ubicación, los archivos se sobrescriben entre sí. Para impedirlo, evite crear fuentes que puedan sobrescribir otra que ya exista en la misma ubicación.

Cuando intente crear una fuente con el mismo nombre de archivo que otra, recibirá el siguiente mensaje:

En ese caso, puede hacer lo siguiente:

* Cambiar la ruta de entrega
* Cambiar las fechas si es posible
* Cambiar el grupo de informes si es posible

## Configuración de BucketOwnerFullControl para las fuentes de datos de Amazon S3  {#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D}

El caso de uso más habitual de Amazon S3 es que el propietario de la cuenta de los servicios web de Amazon (AWS) crea un bucket, a continuación crea un usuario que tiene permiso para crear objetos en ese bucket y, finalmente, proporciona credenciales para ese usuario. En este caso, los objetos de un usuario pertenecen a la misma cuenta y el propietario de la cuenta tiene implícitamente un control total del objeto (leer, eliminar, etc.). Funciona de un modo similar a la entrega por FTP.

AWS también permite a los usuarios crear objetos en un bucket que pertenece a otra cuenta de usuario completamente diferente. Por ejemplo, si dos usuarios de AWS, el usuario A y el usuario B, no pertenecen a la misma cuenta de AWS pero quieren crear objetos en otros buckets. Si el usuario A crea un bucket, por ejemplo el bucket A, este puede crear una política que permita explícitamente que el usuario B cree objetos en el bucket A, aunque el bucket no pertenezca al usuario. Esto puede ser beneficioso porque no es necesario que el usuario A y el usuario B intercambien credenciales. En su lugar, el usuario B proporciona su número de cuenta al usuario A y este crea una política de bucket que diga &quot;permitir al usuario B crear objetos en el bucket A&quot;.

**BucketOwnerFullControl** proporciona derechos a varias cuentas para crear objetos en otros buckets. Si el usuario B carga un objeto al bucket del usuario A, el usuario B todavía &quot;posee&quot; ese objeto y, por defecto, no se han concedido permisos al usuario A sobre ese objeto, aunque el usuario A posea el bucket: los objetos no heredan permisos del bucket primario. El usuario B debe conceder permiso explícitamente al usuario A porque el usuario B sigue siendo el propietario del objeto. Para la carga en varias cuentas, AWS proporciona un BucketOwnerFullControl ACL, especificando que el uso de este ACL por el propietario del bucket (usuario A) tiene permisos concedidos para el objeto (leer, escribir, eliminar, etc.), a pesar de que es el usuario B quien &quot;posee&quot; el objeto.

## Errores de transferencia {#section_4BD44E9167F0494FB2B379D2BA132AD8}

Si se produce un error de transferencia mediante FTP (no se puede iniciar la sesión, se pierde la conexión, se agota la cuota, etc.), Adobe intenta conectarse automáticamente y envía los datos hasta tres veces diferentes. Si no se resuelven los errores, la fuente se marca como errónea y se envía una notificación de correo electrónico.

En caso de un error de transferencia, puede volver a ejecutar un trabajo hasta que se realice correctamente.

## Opciones de reenvío {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Cuando haya comprobado/corregido el problema de entrega, ejecute de nuevo el trabajo para obtener los archivos.

## Efecto del horario de verano en las Fuentes de datos por hora {#section_70E867D942054DD09048E027A9474FFD}

En determinadas zonas horarias, la hora cambia dos veces al año debido a las definiciones del horario de verano (DST). Las fuentes de datos respetan la zona horaria que se ha tomado como referencia para configurar el grupo de informes. Si la zona horaria del grupo de informes no utiliza DST, la entrega de archivos seguirá su curso como cualquier otro día. Si la zona horaria del grupo de informes sí utiliza DST, la entrega de archivos se verá modificada en la hora en la que se produzca el cambio de horario (normalmente a las 2 de la madrugada).

Cuando se realice la transición de STD a DST (cambio de hora estacional), el cliente solo recibirá 23 archivos. La hora que se salta en la transición a DST se omite sin más. Por ejemplo, si la transición se produce a las 2 de la madrugada, el cliente recibirá un archivo correspondiente a la 1 y un archivo correspondiente a las 3. No habrá archivo para las 2, porque las 2 STD se convierten en las 3 DST.

Cuando se realice la transición de DST a STD, el cliente recibirá 24 archivos. Sin embargo, la hora de transición en realidad incluirá datos correspondientes a dos horas. Por ejemplo, si la transición se produce a las 2 de la madrugada, el archivo de la 1 se retrasará una hora, pero incluirá datos de dos horas. Incluirá datos entre la 1 DST y las 2 STD (que habrían sido las 3 DST). El siguiente archivo empezará a las 2 STD.

## Sin datos durante un período de tiempo  {#section_72510794694D42A9A75C966B812AEB0F}

Si quiere, puede configurar una fuente de datos para que envíe un archivo de manifiesto si no se recopilan datos durante un período concreto. Si activa esta opción, recibirá un archivo de manifiesto de aspecto parecido al siguiente:

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 0
 Data-Files: 0
 Total-Records: 0
```

## No se muestra información de dominio en los informes de dominio  {#section_B7508D65370442C7A314EAED711A2C75}

Algunos operadores de telefonía móvil (como T-Mobile y O1) ya no proporcionan información de dominio cuando se realiza una búsqueda de DNS inversa. Por lo tanto, los datos no se muestran en los informes de dominio.

## Información general del procesamiento de datos {#section_6346328F8D8848A7B81474229481D404}

Antes de procesar datos por hora o por día, las fuentes de datos esperan hasta que todas las visitas que han supuesto recopilación de datos dentro del marco de tiempo (un día o una hora) se han registrado en el almacén de datos. A continuación, las fuentes de datos recopilan los datos con marcas de tiempo incluidas dentro del marco de tiempo, las comprimen y las envían por FTP. En el caso de las fuentes por hora, los archivos se suelen registrar en el almacén de datos dentro de los 15-30 minutos posteriores a la hora, pero no hay un período de tiempo definido. Si no ha habido datos con marcas de tiempo incluidas en el marco de tiempo, el proceso vuelve a intentarlo con el siguiente marco de tiempo. El proceso actual de fuente de datos utiliza el campo `date_time` para determinar las visitas que corresponden a la hora. Este campo está basado en la zona horaria del grupo de informes.

## Formatos de fuente de datos &quot;por hora&quot; frente a &quot;diarios&quot;

Para los datos con más de 7 días de antigüedad, los archivos &quot;por hora&quot; de un día se combinan en un solo archivo &quot;Diario&quot;.

Ejemplo: Se crea una nueva fuente de datos el 9 de marzo de 2021 y los datos del 1 de enero de 2021 al 9 de marzo se entregan como &quot;por hora&quot;. Sin embargo, los archivos &quot;Por hora&quot; anteriores al 2 de marzo de 2021 se combinan en un solo archivo &quot;Diario&quot;. Puede extraer archivos &quot;por hora&quot; solo de datos que tengan menos de 7 días desde la fecha de creación. En este caso, del 2 de marzo al 9 de marzo.