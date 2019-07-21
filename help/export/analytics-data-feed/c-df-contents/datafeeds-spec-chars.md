---
description: Información sobre los caracteres especiales que se utilizan en la fuente de datos.
keywords: Fuente de datos; trabajo; caracteres especiales; hit_ data; variables multivalor; events_ list; products_ list; mvvars
seo-description: Información sobre los caracteres especiales que se utilizan en la fuente de datos.
seo-title: Caracteres especiales
solution: Analytics
subtopic: fuentes de datos
title: Caracteres especiales
topic: Reports and Analytics
uuid: 5 efe 019 b -39 e 6-4226-a 936-88202 a 02 f 5 e 6
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Caracteres especiales

Información sobre los caracteres especiales que se utilizan en la fuente de datos.

* [Caracteres especiales del archivo hit_data](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_9759C7A6AE684EB5B4A154FB6A26B39E)
* [Caracteres especiales de las variables multivalor (events_list, products_list, mvvars)](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_056F8D540FFC4F24A001DC74331C2AAC)
* [Flujo de trabajo de muestra](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_97F8C2925A35433DA2E7E8BE60037E37)

## Caracteres especiales del archivo hit_data {#section_9759C7A6AE684EB5B4A154FB6A26B39E}

Los caracteres siguientes tienen un significado especial en el archivo hit_data:

| Carácter | Significado | Descripción |
|--- |--- |--- |
| \t (carácter de tabulación) | Final de columna | Marca el final de un campo de datos. |
| \n (carácter de nueva línea) | Final de fila | Marca el final de una fila de datos. |
| \  (carácter de barra invertida) | Carácter de escape | Elude la tabulación, la nueva línea y la barra invertida cuando el carácter forma parte del valor enviado durante la recopilación de datos. |

La barra invertida delante de cualquiera de los caracteres especiales representa un carácter literal.

| Carácter | Significado | Descripción |
|--- |--- |--- |
| \\t | Tabulación | Carácter literal de tabulación. Este carácter forma parte del valor enviado durante la recopilación de datos. |
| \\n | Nueva línea | Nueva línea literal. Este carácter forma parte del valor enviado durante la recopilación de datos. |
| \\ | Barra invertida | Carácter literal de barra invertida. Este carácter forma parte del valor enviado durante la recopilación de datos. |

## Caracteres especiales de las variables multivalor (events_list, products_list, mvvars) {#section_056F8D540FFC4F24A001DC74331C2AAC}

Los caracteres siguientes tienen un significado especial en las variables multivalor:

<table id="table_FDA13DE05A784ED4972C2955BD2642C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Carácter </th> 
   <th colname="col02" class="entry"> Significado </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> , </code> (carácter de coma) </td> 
   <td colname="col02"> Final del valor </td> 
   <td colname="col2"> <p>Separa las cadenas de productos, los ID de eventos u otros valores de las variables multivalor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> ; </code> (carácter de punto y coma) </td> 
   <td colname="col02"> Final del subvalor incluido en un valor de producto concreto </td> 
   <td colname="col2"> <p>Separa los valores asociados con un producto concreto de <code>product_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> = </code> (carácter de igualdad) </td> 
   <td colname="col02"> Asignación de valor </td> 
   <td colname="col2"> <p>Asigna un valor a un evento de <code>event_list </code>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Cuando uno de los caracteres especiales va precedido de un acento circunflejo, representa un carácter literal.

| Carácter | Significado | Descripción |
|--- |--- |--- |
| ^, | Coma | Carácter literal de coma. Este carácter forma parte del valor enviado durante la recopilación de datos. |
| ^; | Punto y coma | Carácter literal de punto y coma. Este carácter forma parte del valor enviado durante la recopilación de datos. |
| ^= | Es igual a | Carácter literal de igualdad. Este carácter forma parte del valor enviado durante la recopilación de datos. |
| ^^ | Acento circunflejo | Carácter literal de acento circunflejo. Este carácter forma parte del valor enviado durante la recopilación de datos. |

## Flujo de trabajo de muestra {#section_97F8C2925A35433DA2E7E8BE60037E37}

Si algunas de las columnas de la fuente de datos contienen datos introducidos por el usuario, tiene que comprobar si hay caracteres especiales antes de separar los datos por columna o fila mediante `split`, `readLine`, u otra función similar.

Consideremos los siguientes datos:

| Ancho del explorador | Altura del explorador | eVar1 | prop1 |
|---|---|---|---|
| 1680 | 1050 | search\nstring | en |
| 800 | 600 | search\tstring | en |

Durante la exportación, se eluden los caracteres de nueva línea y de tabulación de los valores de eVar1. La fuente de datos de estas filas aparece de la forma siguiente:

```
1680\t1050\tsearch\\nstring\ten\n 
800\t600\tsearch\\tstring\ten\n
```

Calling `readLine()` on the first row returns the following partial string:

```
800\t600\tsearch\
```

Calling `split("\t")` on the second row returns the following string array:

```
800 
600 
search\ 
string 
en
```

Para evitarlo, utilice una solución parecida a la siguiente:

1. Empezando por el principio del archivo, lea hasta que localice un carácter de tabulación, nueva línea, barra invertida o acento circunflejo.
1. Realice una acción en función del carácter especial que haya encontrado:

   * Tabulación: inserte la cadena hasta ese punto en una celda de almacenamiento de datos y continúe.
   * Nueva línea: complete la fila de almacenamiento de datos.
   * Barra invertida: lea el siguiente carácter, inserte el literal de cadena adecuado y continúe.
   * Acento circunflejo: lea el siguiente carácter, inserte el literal de cadena adecuado y continúe.

