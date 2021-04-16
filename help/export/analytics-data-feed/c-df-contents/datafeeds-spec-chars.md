---
description: Información sobre los caracteres especiales que se utilizan en la fuente de datos.
keywords: Fuente de datos;trabajo;caracteres especiales;hit_data;variables de varios valores;events_list;products_list;mvvars
subtopic: data feeds
title: Caracteres especiales en las fuentes de datos
feature: Conceptos básicos de Reports & Analytics
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
exl-id: b816ebc5-0b23-4420-aa8c-b88953d031e6
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 95%

---

# Caracteres especiales en las fuentes de datos

Adobe utiliza la lógica de escape para asegurarse de que los valores enviados a los servidores de recopilación de datos no se dañan ni introducen datos negativos en los archivos. Adobe reserva los caracteres que aparecen a continuación para los siguientes fines en `hit_data.tsv`.

## Caracteres especiales en cualquier columna

| Carácter | Descripción |
|--- |--- |
| `\t` | Representa una pestaña. Marca el final de una columna o campo de datos. |
| `\n` | Representa una nueva línea. Marca el final de una fila o visita. |
| `\` | Barra invertida. Omite los caracteres cuando se envían como parte de la recopilación de datos. |

Cuando estos valores reservados van precedidos de una barra invertida, se envían como parte de la recopilación de datos.

| Carácter | Descripción |
|--- |--- |
| `\\t` | El valor “`\t`” se envió durante la recopilación de datos, omitido por Adobe. |
| `\\n` | El valor “`\n`” se envió durante la recopilación de datos, omitido por Adobe. |
| `\\` | El valor “`\`” se envió durante la recopilación de datos, omitido por Adobe. |

Por ejemplo: Un visitante del sitio utiliza la búsqueda interna y busca “search\nstring”. Propague la eVar1 con “search\nstring” y envíe ese valor a Adobe. Adobe recibe esta visita y omite la nueva línea incluida en la cadena. El valor real colocado en los datos sin procesar es “search\\nstring”.

## Caracteres especiales de las variables multivalor (events_list, products_list, mvvars)

Los siguientes caracteres tienen un significado especial en las columnas que pueden contener varios valores.

| Carácter | Descripción |
|--- |--- |
| `,` | Coma. Representa el final de un valor individual. Separa las cadenas de producto, los ID de evento u otros valores. |
| `;` | Punto y coma. Representa el final de un valor individual en `product_list`. Separa los campos de una sola cadena de producto. |
| `=` | Signo igual. Asigna un valor a un evento de `product_list`. |
| `^` | Acento circunflejo. Omite los caracteres cuando se envían como parte de la recopilación de datos. |

Cuando estos valores reservados van precedidos de un acento circunflejo, se envían como parte de la recopilación de datos.

| Carácter | Descripción |
|--- |--- |
| `^,` | El valor “`,`” se envió durante la recopilación de datos, omitido por Adobe. |
| `^;` | El valor “`;`” se envió durante la recopilación de datos, omitido por Adobe. |
| `^=` | El valor “`=`” se envió durante la recopilación de datos, omitido por Adobe. |
| `^^` | El valor “`^`” se envió durante la recopilación de datos, omitido por Adobe. |
