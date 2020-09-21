---
title: Código de seguimiento
description: Nombre del código de seguimiento o campaña.
translation-type: ht
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: ht
source-wordcount: '525'
ht-degree: 100%

---


# Código de seguimiento

La dimensión “Código de seguimiento” muestra los nombres de los códigos de seguimiento en el sitio. Esta dimensión se recopila generalmente mediante parámetros de cadena de consulta. Puede colocar vínculos con diferentes valores de parámetros de cadena de consulta en diferentes lugares de Internet. Esta dimensión indica qué vínculos fueron los más exitosos a la hora de conducir el tráfico al sitio.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`v0`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable [`campaign`](/help/implement/vars/page-vars/campaign.md).

## Elementos de dimensión

Los elementos de dimensión incluyen los nombres de los códigos de seguimiento en el sitio. Su organización determina qué elementos de dimensión específicos desea utilizar.

## Comparación de la dimensión Código de seguimiento con los canales de marketing que recopilan códigos de seguimiento

Algunos usuarios que configuran reglas de procesamiento de canal de marketing configuran una regla que toma todos los valores utilizados en la dimensión Código de seguimiento. A pesar de ser una práctica excelente, son diferentes debido a las diferencias inherentes de procesamiento y arquitectura. La siguiente lista explica por qué estas dos dimensiones, aunque parecidas de un vistazo, no se pueden comparar entre sí.

* **Canales anteriores en reglas de procesamiento**: Las reglas de procesamiento de los canales de marketing que se encuentran más arriba en la lista pueden impedir que las visitas se atribuyan a su canal de marketing de códigos de seguimiento. Por ejemplo:

   1. Tiene “Redes sociales” configuradas como la primera regla y “Códigos de seguimiento” como la segunda.
   2. Un usuario publica un vínculo a su sitio que contiene un código de seguimiento en un sitio de medios sociales y varios de sus amigos hacen clic en ese vínculo a su sitio.

   Dado que “Redes sociales” es la primera regla de procesamiento de canales de marketing, estos usuarios atribuyen el canal de marketing “Redes sociales” y no el canal de marketing de códigos de seguimiento.
* **Otros canales de marketing pueden robar atribución**: Cuando se trata de una dimensión Código de seguimiento estándar, no es necesario preocuparse por otras partes del sitio que roban la atribución. Sin embargo, con los canales de marketing, un usuario puede hacer coincidir una regla diferente y dar una atribución diferente. Por ejemplo:
   1. Tiene “Códigos de seguimiento” como primer canal y “Directo” como segundo.
   2. Un usuario llega al sitio inicialmente a través de un código de seguimiento, pero luego sale.
   3. Al día siguiente, escriben su dirección URL en la barra de direcciones y luego realizan una compra.

   El canal de marketing de códigos de seguimiento no obtendría crédito de último contacto para esa compra. En su lugar, iría al canal de marketing “Directo”.
* **Diferencias de caducidad**: Los canales de marketing tienen una caducidad de participación del visitante de 30 días móviles, independientemente de si hubo contacto con un canal o no. Los códigos de seguimiento tienen una caducidad basada en el momento en que se configuró la variable. Por ejemplo:
   1. Tiene una caducidad de la participación del visitante de 30 días y también configuró la dimensión Código de seguimiento para que caduque a los 30 días.
   2. Un usuario llega al sitio a través de un código de seguimiento. Exploran el sitio y luego se van.
   3. Tres semanas después, regresan sin un código de seguimiento o canal de marketing, y luego se van de nuevo.
   4. Otras dos semanas después (cinco semanas después de su visita inicial), regresan sin un código de seguimiento o canal de marketing y luego realizan una compra.
   El usuario realizó una compra más allá de los 30 días, pero nunca estuvo inactivo durante más de 30 días. Verá los ingresos atribuidos al canal de marketing de códigos de seguimiento, pero no a la dimensión independiente.
