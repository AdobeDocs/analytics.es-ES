---
description: Muestra ejemplos de cómo etiquetar datos para datos de visitas, solicitudes de acceso y solicitudes de eliminación
title: Ejemplos de etiquetado
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
exl-id: 9bea8636-c79c-4998-8952-7c66d31226e3
source-git-commit: 91864a15bda5022dbbd9b9b312bc6c042078b6a5
workflow-type: ht
source-wordcount: '814'
ht-degree: 100%

---

# Ejemplos de etiquetado

## Ejemplo de datos de visita

Suponga que dispone de los siguientes datos de visita:

* La primera fila contiene las etiquetas de cada variable.
* La segunda fila es el nombre de la variable. Si tiene una etiqueta de ID, contiene el área de nombres asignado entre paréntesis.
* Los datos de visita empiezan en la tercera fila.

| Etiquetas | I2 <br> ID-PERSON <br> DEL-PERSON <br> ACC-PERSON | I2 <br> ID-DEVICE <br> DEL-DEVICE <br> ACC-ALL | I2 <br> DEL-PERSON <br> ACC-PERSON | I2 <br> DEL-DEVICE <br> DEL-PERSON <br> ACC-ALL | I2 <br> ID-DEVICE <br> DEL-DEVICE <br> ACC-ALL |
|---|---|---|---|---|---|
| **Nombre de variable** <br> **(Área de nombres)** | **MyProp1** <br> **(usuario)** | **ID de visitante** <br> **(AAID)** | **MyEvar1**  | **MyEvar2**  | **MyEvar3**  <br> **(xyz)** |
| Datos de visita | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## Ejemplo de solicitud de acceso

Si envío una solicitud de acceso, el archivo de resumen contiene los valores indicados en la tabla a continuación. Una solicitud puede contener únicamente un archivo de dispositivo, solo un archivo de persona o uno de cada. Solo se devuelven dos archivos de resumen si se utiliza un ID de persona y expandIDs es &quot;true&quot;.

<table>
  <tr>
    <th colspan="2" style="text-align:center">Valores de API</th>
    <th rowspan="2">Tipo de archivo devuelto<br></th>
    <th colspan="5" style="text-align:center">Datos en el archivo de acceso de resumen</th>
  </tr>
  <tr>
    <th>Espacio de nombres/ ID</th>
    <th>expandIDs</th>
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
    <td>contenedor</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A,B,C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary</td>
    <td rowspan="2">true</td>
    <td>contenedor</td>
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
    <td>contenedor</td>
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
    <td>55, 77</td>
    <td>no presente</td>
    <td>M, R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>true</td>
    <td>dispositivo</td>
    <td>no presente</td>
    <td>55, 77</td>
    <td>no presente</td>
    <td>M, P, R</td>
    <td>W, X</td>
  </tr>
</table>

Tenga en cuenta que la configuración para expandIDs no supone ninguna diferencia en cuanto al resultado cuando se utiliza un ID de cookie.

## Ejemplos de solicitudes de eliminación

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
>Solo se ven afectadas las celdas de las filas que contienen AAID = 77 y una etiqueta DEL-DEVICE.

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
>Solo se ven afectadas las celdas de las filas que contienen user=Mary y una etiqueta DEL-PERSON. Además, en la práctica, la variable que contiene A_ID probablemente sería una prop o una eVar. Su valor de reemplazo sería una cadena que empiece por “Privacy-”, seguida de un número aleatorio (GUID), en lugar de reemplazar el valor numérico con un valor numérico aleatorio diferente.

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
* Debido a la expansión del ID, las celdas de las filas que contienen `AAID=77`, `AAID=88` o `AAID=99` (que son los valores AAID de las filas que contienen `user=Mary`) y una etiqueta `DEL-DEVICE` se ven afectadas. Esto incluye celdas con una etiqueta `DEL-DEVICE` en filas donde `user=Mary`. Esto provoca que las celdas de las filas 4 y 5 (así como las filas 1-3) con etiquetas `DEL-DEVICE` (AAID, MyEvar2 y MyEvar3) se deban ocultar.
* La configuración expandIDs no se expande a la llamada para incluir los valores presentes en MyEvar3 (`X`, `Y` y `Z`), que tiene una etiqueta ID-DEVICE, cuando `user=Mary`. ExpandIDs solo se expande para incluir los ID de visitante (AAID en este ejemplo, pero también el ECID) en filas donde `user=Mary`. Por lo tanto, las dos últimas filas, que contienen los valores MyEvar3 de `X` y `Z`, no se ven afectadas.
* `MyEvar2` en las filas cuarta y quinta se actualiza, ya que estas filas contienen los mismos valores de ID de visitante (`77` y `88`) que los de las filas primera y segunda. Como resultado, la expansión de ID los incluye para eliminaciones en el nivel de dispositivo.
* Los valores de `MyEvar2` en las filas segunda y quinta coinciden tanto antes como después de la eliminación. Sin embargo, después de la eliminación, ya no coinciden con el valor `N` que se produce en la última fila, ya que esa fila no se actualizó como parte de la solicitud de eliminación.
* `MyEvar3` se comporta de forma muy distinta a como lo hacía sin expansión de ID porque, sin esta, ningún coincidía.`ID-DEVICES` Ahora, `AAID` coincide en las primeras cinco filas.
