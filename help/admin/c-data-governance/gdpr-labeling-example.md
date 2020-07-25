---
description: 'null'
title: Ejemplo de etiquetado
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: tm+mt
source-git-commit: b3e8f77bfa7c48fc82e5ebd5bbe66511ea82c9f4
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 100%

---


# Ejemplo de etiquetado

## Ejemplo de datos de visita

Suponga que dispone de los siguientes datos de visita:

* La primera fila contiene las etiquetas de cada variable.
* La segunda fila es el nombre de la variable. Si tiene una etiqueta de ID, contiene el área de nombres asignado entre paréntesis.
* Los datos de visita empiezan en la tercera fila.

| Etiquetas | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|---|---|---|---|---|---|
| **Nombre de variable** <br> **(Área de nombres)** | **MyProp1** <br> **(usuario)** | **ID de visitante** <br> **(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3** <br> **(xyz)** |
| Datos de visita | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## Ejemplo de solicitud de acceso

Si envío una solicitud de acceso, el archivo de resumen contendrá los valores indicados en la tabla a continuación. Una solicitud puede contener únicamente un archivo de dispositivo, solo un archivo de persona o uno de cada. Solo se devuelven dos archivos de resumen si se utiliza un ID de persona y expandIDs es &quot;true&quot;.

| Valores de API | Valores de API | Tipo de archivo devuelto | Datos en el archivo de acceso de resumen<br> | Datos en el archivo de acceso de resumen<br> | Datos en el archivo de acceso de resumen<br> | Datos en el archivo de acceso de resumen<br> | Datos en el archivo de acceso de resumen<br> |
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
| Mary | 42 | A | Privacidad-7398 | Privacidad-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | Privacidad-1866 | Privacidad-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE]
>
>Solo se ven afectadas las celdas de las filas que contienen AAID = 77 y una etiqueta DEL-DEVICE.

| user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacidad-0523 | 77 | Privacidad-1866 | Privacidad-3681 | X |
| Privacidad-0523 | 88 | Privacidad-2178 | Privacidad-1975 | Y |
| Privacidad-0523 | 99 | Privacidad-9045 | Privacidad-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE]
>
>Solo se ven afectadas las celdas de las filas que contienen user=Mary y una etiqueta DEL-PERSON. Además, en la práctica, la variable que contiene A_ID probablemente sería una prop o eVar y su valor de sustitución sería una cadena que empiece por “Privacidad-”, seguida por un número aleatorio (GUID), en lugar de sustituir el valor numérico con un valor numérico aleatorio diferente.

| user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacidad-5782 | 09 | Privacidad-0859 | Privacidad-8183 | Privacidad-9152 |
| Privacidad-5782 | 16 | Privacidad-6104 | Privacidad-2911 | Privacidad-6821 |
| Privacidad-5782 | 83 | Privacidad-2714 | Privacidad-0219 | Privacidad-4395 |
| John | 09 | D | Privacidad-8454 | Privacidad-8216 |
| John | 16 | E | Privacidad-2911 | Privacidad-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

Recuerde lo siguiente:

* Las celdas de las filas que contienen `user=Mary` y una etiqueta `DEL-DEVICE` o `DEL-PERSON` se ven afectadas, así como las celdas con una etiqueta `DEL-DEVICE` en filas que contienen cualquier ID de visitante que se ha producido en una fila que contiene `user=Mary`.
* `MyEvar2` en las filas cuarta y quinta se actualiza, ya que estas filas contienen los mismos valores de ID de visitante que los de las filas primera y segunda, de forma que la expansión del ID los incluye para las eliminaciones de dispositivos.
* Los valores de `MyEvar2` de las filas segunda y quinta coinciden tanto antes como después de la eliminación, pero tras la eliminación ya no coincide el valor N que se produce en la última fila, ya que esa fila no se ha actualizado como parte de la solicitud de eliminación.
* `MyEvar3` se comporta de forma muy distinta a como lo hacía sin expansión de ID porque, sin esta, ningún coincidía.`ID-DEVICES` Ahora, `AAID` coincide en las primeras cinco filas.
