---
description: Muestra ejemplos de cómo etiquetar datos para datos de visitas, solicitudes de acceso y solicitudes de eliminación
title: Ejemplos de etiquetado
feature: Data Governance
role: Admin
exl-id: 9bea8636-c79c-4998-8952-7c66d31226e3
source-git-commit: 0b8b9d0067c183bfeb13816f942b3726ac66d08c
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 81%

---

# Ejemplos de etiquetado

## Ejemplo de datos de visita {#hit}

Supongamos que tiene los siguientes datos de visitas:

* La primera fila contiene las etiquetas de cada variable.
* La segunda fila es el nombre de la variable. Si tiene una etiqueta de ID, contiene el área de nombres asignado entre paréntesis.
* Los datos de visitas comienzan en la tercera fila.

| Etiquetas | I2 <br> ID-PERSON <br> DEL-PERSON <br> ACC-PERSON | I2 <br> ID-DEVICE <br> DEL-DEVICE <br> ACC-ALL | I2 <br> DEL-PERSON <br> ACC-PERSON | I2 <br> DEL-DEVICE <br> DEL-PERSON <br> ACC-ALL | I2 <br> ID-DEVICE <br> DEL-DEVICE <br> ACC-ALL |
|---|---|---|---|---|---|
| **Nombre de variable** <br> **(Área de nombres)** | **MyProp1** <br> **(usuario)** | **ID de visitante** <br> **(AAID)** | **MyEvar1**  | **MyEvar2**  | **MyEvar3** <br>  **(xyz)** |
| Datos de visitas | Mary | 77 | A | M | X |
| | Mary | 88 | B | N | Y |
| | Mary | 99 | C | O | Z |
| | John | 77 | D | P | W |
| | John | 88 | E | N | U |
| | John | 44 | F | Q | V |
| | John | 55 | G | R | X |
| | Alice | 66 | A | N | Z |

## Muestra de solicitud de acceso {#access}

Si envía una solicitud de acceso, recibirá dos archivos que puede devolver al interesado. Un archivo CSV contiene una fila por cada visita recibida para el interesado y una columna para cada variable con la etiqueta de acceso adecuada. El otro archivo es un archivo HTML de resumen que enumera cada variable, seguida de todos los valores únicos vistos para esa variable para el interesado y el número de veces que se vio cada valor único.

Para nuestro ejemplo, el archivo de resumen contiene los valores indicados en la tabla a continuación. Una solicitud puede contener únicamente un archivo de dispositivo, 0 solo un archivo de persona o ambos. Solo se devuelven dos archivos de resumen si se utiliza un ID de persona y `expandIds` es &quot;true&quot;.

<table>
  <tr>
    <th colspan="2" style="text-align:center">Valores de la API</th>
    <th>Tipo de archivo<br/>de resumen<br/>devuelto</th>
    <th colspan="5" style="text-align:center">Datos en el archivo de acceso de resumen</th>
  </tr>
  <tr>
    <th>Espacio de nombres/ ID</th>
    <th>expandIDs</th>
    <th></th>
    <th>MyProp1</th>
    <th>ID de visitante</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>false</td>
    <td>dispositivo</td>
    <td>no presente</td>
    <td>77</td>
    <td>no presente</td>
    <td>M, P</td>
    <td>X, W</td>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>true</td>
    <td>dispositivo</td>
    <td>no presente</td>
    <td>77</td>
    <td>no presente</td>
    <td>M, P</td>
    <td>X, W</td>
  </tr>
  <tr>
    <td>user=Mary</td>
    <td>false</td>
    <td>persona</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A,B,C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary</td>
    <td rowspan="2">true</td>
    <td>persona</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A,B,C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td>dispositivo</td>
    <td>no presente</td>
    <td>77, 88</td>
    <td>A,B,C</td>
    <td>N, P</td>
    <td>U, W</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary<br>AAID=66</td>
    <td rowspan="2">true</td>
    <td>persona</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A,B,C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td>dispositivo</td>
    <td>no presente</td>
    <td>66, 77, 88</td>
    <td>A,B,C</td>
    <td>N, P</td>
    <td>U, W, Z</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>false</td>
    <td>dispositivo</td>
    <td>no presente</td>
    <td>57, 77</td>
    <td>no presente</td>
    <td>M, R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>true</td>
    <td>dispositivo</td>
    <td>no presente</td>
    <td>57, 77</td>
    <td>no presente</td>
    <td>M, P, R</td>
    <td>W, X</td>
  </tr>
</table>

Tenga en cuenta que la configuración de `expandIDs` no supone ninguna diferencia en cuanto al resultado cuando se utiliza un ID de cookie.

## Muestras de solicitudes de eliminación {#delete}

Con una solicitud de eliminación que utiliza valores de API en la primera fila de la tabla, la tabla de visitas se actualizará para buscar algo parecido a esto:

<table>
  <tr>
    <th colspan="5" style="text-align:center">AAID=77 <br>(el valor expandIDs no importa)</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Mary</td>
    <td>42</td>
    <td>A</td>
    <td>Privacidad-7398</td>
    <td>Privacidad-9152</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>88</td>
    <td>B</td>
    <td>N</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>99</td>
    <td>C</td>
    <td>O</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>42</td>
    <td>D</td>
    <td>Privacidad-1866</td>
    <td>Privacidad-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>Solo se ven afectadas las columnas de las filas que contienen `AAID=77` y una etiqueta `DEL-DEVICE`.

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary <br> expandIDs=false</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Privacidad-0523</td>
    <td>77</td>
    <td>Privacidad-1866</td>
    <td>Privacidad-3681</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Privacidad-0523</td>
    <td>88</td>
    <td>Privacidad-2178</td>
    <td>Privacidad-1975</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Privacidad-0523</td>
    <td>99</td>
    <td>Privacidad-9045</td>
    <td>Privacidad-2864</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>77</td>
    <td>D</td>
    <td>P</td>
    <td>W</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>Solo se ven afectadas las etiquetas celcolumnsls en las filas que contienen `user=Mary` y `DEL-PERSON`. Además, en la práctica, la variable que contiene `A_ID` probablemente sería una prop o eVar. Su valor de reemplazo sería una cadena que empiece por `Privacy-`, seguida de un número aleatorio (GUID), en lugar de reemplazar el valor numérico por un valor numérico aleatorio, diferente.

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary <br> expandIDs=true</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Privacidad-5782</td>
    <td>09</td>
    <td>Privacidad-0859</td>
    <td>Privacidad-8183</td>
    <td>Privacidad-9152</td>
  </tr>
  <tr>
    <td>Privacidad-5782</td>
    <td>16</td>
    <td>Privacidad-6104</td>
    <td>Privacidad-2911</td>
    <td>Privacidad-6821</td>
  </tr>
  <tr>
    <td>Privacidad-5782</td>
    <td>83</td>
    <td>Privacidad-2714</td>
    <td>Privacidad-0219</td>
    <td>Privacidad-4395</td>
  </tr>
  <tr>
    <td>John</td>
    <td>09</td>
    <td>D</td>
    <td>Privacidad-8454</td>
    <td>Privacidad-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>16</td>
    <td>E</td>
    <td>Privacidad-2911</td>
    <td>Privacidad-2930</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

Recuerde lo siguiente:

* Solo se ven afectadas las celdas de las filas que contienen `user=Mary` y una etiqueta `DEL-PERSON`.

