---
description: 'null'
seo-description: 'null'
seo-title: Ejemplo de etiquetado
title: Ejemplo de etiquetado
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: tm+mt
source-git-commit: d2134271c4586d629c8b25f60c746902ba13683b

---


# Ejemplo de etiquetado

## Ejemplo de datos de visita

Suponga que dispone de los siguientes datos de visita:

* La primera fila contiene las etiquetas de cada variable.
* La segunda fila es el nombre de la variable. Si tiene una etiqueta de ID, contiene el espacio de nombres asignado entre paréntesis.
* Los datos de visita empiezan en la tercera fila.

| Etiquetas | I2<br>ID-<br>PERSONDEL-<br>PERSONACC-PERSONA | I2<br>ID-<br>DEVICEDEL-<br>DEVICEACC-ALL | I2<br>DEL-<br>PERSONACC-PERSON | I2<br>DEL-<br>DEVICEDEL-<br>PERSONACC-ALL | I2<br>ID-<br>DEVICEDEL-<br>DEVICEACC-ALL |
|---|---|---|---|---|---|
| **Nombre**<br>**de la variable (espacio de nombres)** | **MyProp1**<br>**(usuario)** | **ID**<br>**del visitante (AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3**<br>**(xyz)** |
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
| Mary | 42 | A | Privacy-7398 | Privacy-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | Privacy-1866 | Privacy-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] Solo se ven afectadas las celdas de las filas que contienen AAID = 77 y una etiqueta DEL-DEVICE.

| user=<br>MaryexpandedIDs=false | user=<br>MaryexpandedIDs=false | user=<br>MaryexpandedIDs=false | user=<br>MaryexpandedIDs=false | user=<br>MaryexpandedIDs=false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-0523 | 77 | Privacy-1866 | Privacy-3681 | X |
| Privacy-0523 | 88 | Privacy-2178 | Privacy-1975 | Y |
| Privacy-0523 | 99 | Privacy-9045 | Privacy-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] Solo se ven afectadas las celdas de las filas que contienen user=Mary y una etiqueta DEL-PERSON. Además, en la práctica, la variable que contiene A_ID probablemente sea una prop o eVar y su valor de reemplazo será una cadena que comience por "Privacy-", seguida de un número aleatorio (GUID), en lugar de reemplazar el valor numérico con un valor numérico aleatorio diferente.

| user=<br>MaryexpandedIDs=true | user=<br>MaryexpandedIDs=true | user=<br>MaryexpandedIDs=true | user=<br>MaryexpandedIDs=true | user=<br>MaryexpandedIDs=true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-5782 | 09 | Privacy-0859 | Privacy-8183 | Privacy-9152 |
| Privacy-5782 | 16 | Privacy-6104 | Privacy-2911 | Privacy-6821 |
| Privacy-5782 | 83 | Privacy-2714 | Privacy-0219 | Privacy-4395 |
| John | 09 | D | Privacy-8454 | Privacy-8216 |
| John | 16 | E | Privacy-2911 | Privacy-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

Tenga en cuenta lo siguiente:

* Cells on rows containing `user=Mary` and a `DEL-DEVICE` or `DEL-PERSON` label are impacted, as well as cells with a `DEL-DEVICE` label on rows containing any Visitor ID that occurred on a row containing `user=Mary`.
* `MyEvar2` en las filas cuarta y quinta se actualiza, ya que estas filas contienen los mismos valores de ID de visitante que los de las filas primera y segunda, de forma que la expansión del ID los incluye para las eliminaciones de dispositivos.
* The values of `MyEvar2` in rows two and five match both before and after the delete, but after the delete no longer matches the value N that occurs in the last row, because that row was not updated as part of the delete request.
* `MyEvar3` se comporta de forma muy distinta a como lo hacía sin expansión de ID porque, sin esta, ningún coincidía.`ID-DEVICES` Now `AAID` matches on the first five rows.
