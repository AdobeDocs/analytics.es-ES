---
description: 'null'
seo-description: 'null'
seo-title: Ejemplo de etiquetado
title: Ejemplo de etiquetado
uuid: a 9 a 5 b 937-dbde -4 f 0 f-a 171-005 ef 4 c 79 df 9
translation-type: tm+mt
source-git-commit: fe1d2eb0bae02ee9eeb59e1689519836f8acf8db

---


# Ejemplo de etiquetado

## Ejemplo de datos de visita {#section_94DE6BC0026F46D7AD7061C5625C8D52}

Suponga que dispone de los siguientes datos de visita:

* La primera fila contiene las etiquetas de cada variable.
* La segunda fila es el nombre de la variable. Si tiene una etiqueta de ID, contiene el espacio de nombres asignado entre paréntesis.
* Los datos de visita empiezan en la tercera fila.

<!-- Meike, I converted html tables for fix elusive validation error. Bob -->

| Etiquetas | I2<br>ID-PERSONDEL<br>-PERSONACC<br>-PERSON | I 2<br>ID-DEVICEDEL<br>-DEVICEACC<br>-ALL | I 2<br>DEL-PERSONACC<br>-PERSON | I 2<br>DEL-DEVICEDEL<br>-PERSONACC<br>-ALL | I 2<br>ID-DEVICEDEL<br>-DEVICEACC<br>-ALL |
|---|---|---|---|---|---|
| Nombre de variable<br>(espacio de nombres) | Myprop 1<br>(usuario) | ID de visitante<br>(AAID) | MyEvar1 | MyEvar2 | Myevar 3<br>(xyz) |
| Datos de visita | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |


## Ejemplo de solicitud de acceso {#section_BDA817FD2415420DAAC835825484BA9D}

Si envío una solicitud de acceso, el archivo de resumen contendrá los valores indicados en la tabla a continuación. Una solicitud puede contener únicamente un archivo de dispositivo, solo un archivo de persona o uno de cada. Solo se devuelven dos archivos de resumen si se utiliza un ID de persona y expandIDs es "true".

| Valores de API | Valores de API | Tipo de archivo devuelto | Data in <br>Summary Access File </br> | Data in <br>Summary Access File</br> | Data in <br>Summary Access File</br> | Data in <br>Summary Access File</br> | Data in <br>Summary Access File</br> |
|--- |--- |--- |---|---|---|---|---|
| Espacio de nombres/ ID | expandIDs |  | MyProp1 | Visitor ID | MyEvar1 | MyEvar2 | MyEvar3 |
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

## Ejemplo de solicitud de eliminación {#section_6C75F70F5D574BE7AA540981E8B7EA26}

Con una solicitud de eliminación que utiliza valores de API en la primera fila de la tabla, la tabla de visitas se actualizará para buscar algo parecido a esto:

| AAID=77 expandIDs value<br>does not matter</br> | AAID=77 expandIDs value<br>does not matter</br> | AAID=77 expandIDs value<br>does not matter</br> | AAID=77 expandIDs value<br>does not matter</br> | AAID=77 expandIDs value<br>does not matter</br> |
|---|---|---|---|---|
| MyProp1 | AAID | MyEvar1 | MyEvar2 | MyEvar3 |
| Mary | 42 | A | GDPR-7398 | GDPR-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | GDPR-1866 | GDPR-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE]
>
>Solo se afectan las celdas de las filas que contienen AAID = 77 y una etiqueta del DEL-DEVICE.

| user = maryexpandids<br>= false</br> | user = maryexpandids<br>= false</br> | user = maryexpandids<br>= false</br> | user = maryexpandids<br>= false</br> | user = maryexpandids<br>= false</br> |
|--- |---|---|---|---|
| MyProp1 | AAID | MyEvar1 | MyEvar2 | MyEvar3 |
| GDPR-0523 | 77 | GDPR-1866 | GDPR-3681 | X |
| GDPR-0523 | 88 | GDPR-2178 | GDPR-1975 | Y |
| GDPR-0523 | 99 | GDPR-9045 | GDPR-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE]
>
>Solo se afectan las celdas de las filas que contienen user = Mary y una etiqueta del DE-PERSON. Además, en la práctica, la variable que contiene A_ID probablemente sería una prop o eVar y su valor de sustitución sería una cadena que empiece por “GDPR-”, segunda por un número aleatorio (GUID), en lugar de sustituir el valor numérico con un valor numérico aleatorio diferente.

| user=Mary<br>expandIDs=true</br> | user = maryexpandids<br>= true</br> | user = maryexpandids<br>= true</br> | user = maryexpandids<br>= true</br> | user = maryexpandids<br>= true</br> |
|--- |---|---|---|---|
| MyProp1 | AAID | MyEvar1 | MyEvar2 | MyEvar3 |
| GDPR-5782 | 09 | GDPR-0859 | GDPR-8183 | GDPR-9152 |
| GDPR-5782 | 16 | GDPR-6104 | GDPR-2911 | GDPR-6821 |
| GDPR-5782 | 83 | GDPR-2714 | GDPR-0219 | GDPR-4395 |
| John | 09 | D | GDPR-8454 | GDPR-8216 |
| John | 16 | E | GDPR-2911 | GDPR-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

Tenga en cuenta lo siguiente:

* Las celdas de las filas que contienen user=Mary y una etiqueta DEL-DEVICE o DEL-PERSON se ven afectadas, así como las celdas con una etiqueta DEL-DEVICE en filas que contienen cualquier ID de visitante que se ha producido en una fila que contiene user=Mary.
* MyEvar2 en las filas cuarta y quinta se actualiza, ya que estas filas contienen los mismos valores de ID de visitante que los de las filas primera y segunda, de forma que la expansión del ID los incluye para las eliminaciones de dispositivos.
* Los valores de MyEvar2 de las filas segunda y quinta coinciden tanto antes como después de la eliminación, pero tras la eliminación ya no coincide el valor N que se produce en la última fila, ya que esa fila no se ha actualizado como parte de la solicitud de eliminación.
* MyEvar3 se comporta de forma muy distinta a como lo hacía sin expansión de ID porque, sin esta, ningún ID-DEVICES coincidía. Ahora, AAID coincide en las primeras cinco filas.
