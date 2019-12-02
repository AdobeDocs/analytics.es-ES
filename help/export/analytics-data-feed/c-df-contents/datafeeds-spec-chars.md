---
description: Información sobre los caracteres especiales que se utilizan en la fuente de datos.
keywords: Data Feed;job;special characters;hit_data;multi-valued variables;events_list;products_list;mvvars
solution: Analytics
subtopic: data feeds
title: Caracteres especiales en las fuentes de datos
topic: Reports and analytics
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Caracteres especiales en las fuentes de datos

Adobe utiliza la lógica de escape para asegurarse de que los valores enviados a los servidores de recopilación de datos no dañan ni dañan los archivos de fuentes de datos. Adobe reserva los siguientes caracteres para los siguientes fines en `hit_data.tsv`.

## Caracteres especiales en cualquier columna

| Carácter | Descripción |
|--- |--- |
| `\t` | Representa una ficha. Marca el final de una columna o campo de datos. |
| `\n` | Representa una nueva línea. Marca el final de una fila o visita individual. |
| `\` | Barra invertida. Escapa los caracteres cuando se envían como parte de la recopilación de datos. |

Cuando estos valores reservados van precedidos de una barra invertida, se envían como parte de la recopilación de datos.

| Carácter | Descripción |
|--- |--- |
| `\\t` | El valor '`\t`' se envió durante la recopilación de datos y Adobe lo escapó. |
| `\\n` | El valor '`\n`' se envió durante la recopilación de datos y Adobe lo escapó. |
| `\\` | El valor '`\`' se envió durante la recopilación de datos y Adobe lo escapó. |

Por ejemplo: un visitante del sitio utiliza la búsqueda interna y busca "search\nstring". Rellene eVar1 con "search\nstring" y envíe ese valor a Adobe. Adobe recibe esta visita y escapa a la nueva línea incluida en la cadena. El valor real colocado en los datos sin procesar es "search\\nstring".

## Caracteres especiales de las variables multivalor (events_list, products_list, mvvars)

Los siguientes caracteres tienen un significado especial en las columnas que pueden contener varios valores.

| Carácter | Descripción |
|--- |--- |
| `,` | Coma. Representa el final de un valor individual. Separa las cadenas de producto, los ID de evento u otros valores. |
| `;` | Punto y coma. Representa el final de un valor individual en `product_list`. Separa los campos de una sola cadena de producto. |
| `=` | Es igual a signo. Assigns a value to an event in `product_list`. |
| `^` | Acento circunflejo. Escapa los caracteres cuando se envían como parte de la recopilación de datos. |

Cuando estos valores reservados van precedidos de un acento circunflejo, se envían como parte de la recopilación de datos.

| Carácter | Descripción |
|--- |--- |
| `^,` | El valor '`,`' se envió durante la recopilación de datos y Adobe lo escapó. |
| `^;` | El valor '`;`' se envió durante la recopilación de datos y Adobe lo escapó. |
| `^=` | El valor '`=`' se envió durante la recopilación de datos y Adobe lo escapó. |
| `^^` | El valor '`^`' se envió durante la recopilación de datos y Adobe lo escapó. |
