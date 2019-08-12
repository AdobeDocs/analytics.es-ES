---
description: 'null'
seo-description: 'null'
seo-title: Ejemplo de etiquetado
title: Ejemplo de etiquetado
uuid: a 9 a 5 b 937-dbde -4 f 0 f-a 171-005 ef 4 c 79 df 9
translation-type: tm+mt
source-git-commit: edafa9ca8dc34bd1f3af8c56b4f23c4a983aa677

---


# Ejemplo de etiquetado

## Ejemplo de datos de visita

Suponga que dispone de los siguientes datos de visita:

* La primera fila contiene las etiquetas de cada variable.
* La segunda fila es el nombre de la variable. Si tiene una etiqueta de ID, contiene el espacio de nombres asignado entre paréntesis.
* Los datos de visita empiezan en la tercera fila.

| Etiquetas | I2<br>ID-PERSONDEL<br>-PERSONACC<br>-PERSON | I 2<br>ID-DEVICEDEL<br>-DEVICEACC<br>-ALL | I 2<br>DEL-PERSONACC<br>-PERSON | I 2<br>DEL-DEVICEDEL<br>-PERSONACC<br>-ALL | I 2<br>ID-DEVICEDEL<br>-DEVICEACC<br>-ALL |
|---|---|---|---|---|---|
| **Nombre de variable**<br>**(espacio de nombres)** | **Myprop 1**<br>**(usuario)** | **ID de visitante**<br>**(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3**<br>**(xyz)** |
| Datos de visita | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## Ejemplo de solicitud de acceso

Si envío una solicitud de acceso, el archivo de resumen contendrá los valores indicados en la tabla a continuación. Una solicitud puede contener únicamente un archivo de dispositivo, solo un archivo de persona o uno de cada. Solo se devuelven dos archivos de resumen si se utiliza un ID de persona y expandIDs es "true".

| Valores de API | Valores de API | Tipo de archivo devuelto | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File |
|--- |--- |--- |---|---|---|---|---|
| **Espacio de nombres/ ID** | **expandIDs** |  | **MyProp1** | **Visitor ID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | false | dispositivo | Variable no presente | 77 | Variable no presente | M, P | X, W |
| AAID=77 | true | dispositivo | Variable no presente | 77 | Variable no presente | M, P | X, W |
| user=Mary | false | contenedor | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | contenedor | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | dispositivo | no presente | 77, 88 | no presente | N, P | U, W |
| user=Mary AAID=66 | true | contenedor | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary AAID=66 | true | dispositivo | no presente | 66, 77, 88 | no presente | N, P | U, W, Z |
| xyz=X | false | dispositivo | no presente | 55, 77 | no presente | M, R | X |
| xyz=X | true | dispositivo | no presente | 55, 77 | no presente | M, P, R | W, X |

Tenga en cuenta que la configuración para expandIDs no supone ninguna diferencia en cuanto al resultado cuando se utiliza un ID de cookie.

## Ejemplo de solicitud de eliminación

Con una solicitud de eliminación que utiliza valores de API en la primera fila de la tabla, la tabla de visitas se actualizará para buscar algo parecido a esto:

| AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter |
|---|---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Mary | 42 | A | GDPR-7398 | GDPR-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | GDPR-1866 | GDPR-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] Solo se afectan las celdas de las filas que contienen AAID = 77 y una etiqueta del DEL-DEVICE.

| user = maryexpandids<br>= false | user = maryexpandids<br>= false | user = maryexpandids<br>= false | user = maryexpandids<br>= false | user = maryexpandids<br>= false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| GDPR-0523 | 77 | GDPR-1866 | GDPR-3681 | X |
| GDPR-0523 | 88 | GDPR-2178 | GDPR-1975 | Y |
| GDPR-0523 | 99 | GDPR-9045 | GDPR-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] Solo se afectan las celdas de las filas que contienen user = Mary y una etiqueta del DE-PERSON. Además, en la práctica, la variable que contiene A_ID probablemente sería una prop o eVar y su valor de sustitución sería una cadena que empiece por “GDPR-”, segunda por un número aleatorio (GUID), en lugar de sustituir el valor numérico con un valor numérico aleatorio diferente.

| user=Mary<br>expandIDs=true | user = maryexpandids<br>= true | user = maryexpandids<br>= true | user = maryexpandids<br>= true | user = maryexpandids<br>= true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| GDPR-5782 | 09 | GDPR-0859 | GDPR-8183 | GDPR-9152 |
| GDPR-5782 | 16 | GDPR-6104 | GDPR-2911 | GDPR-6821 |
| GDPR-5782 | 83 | GDPR-2714 | GDPR-0219 | GDPR-4395 |
| John | 09 | D | GDPR-8454 | GDPR-8216 |
| John | 16 | E | GDPR-2911 | GDPR-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

Tenga en cuenta lo siguiente:

* Cells on rows containing `user=Mary` and a `DEL-DEVICE` or `DEL-PERSON` label are impacted, as well as cells with a `DEL-DEVICE` label on rows containing any Visitor ID that occurred on a row containing `user=Mary`.
* `MyEvar2` en las filas cuarta y quinta se actualiza, ya que estas filas contienen los mismos valores de ID de visitante que los de las filas primera y segunda, de forma que la expansión del ID los incluye para las eliminaciones de dispositivos.
* The values of `MyEvar2` in rows two and five match both before and after the delete, but after the delete no longer matches the value N that occurs in the last row, because that row was not updated as part of the delete request.
* `MyEvar3` se comporta de forma muy distinta a como lo hacía sin expansión de ID porque, sin esta, ningún coincidía.`ID-DEVICES` Now `AAID` matches on the first five rows.
