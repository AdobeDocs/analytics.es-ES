---
title: Código de seguimiento
description: Nombre del código de seguimiento o campaña.
feature: Dimensions
exl-id: e4f70552-6946-4974-a9e2-928faf563ecd
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: ht
source-wordcount: '559'
ht-degree: 100%

---

# Código de seguimiento

La [dimensión](overview.md) “Código de seguimiento” muestra los nombres de los códigos de seguimiento en el sitio. Puede colocar vínculos con diferentes valores de parámetros de cadenas de consulta en diferentes lugares de internet. Esta dimensión puede ayudarle a entender mejor qué vínculos fueron los más exitosos a la hora de impulsar el tráfico al sitio.

Añadir cadenas de consulta de código de seguimiento es habitual en los correos electrónicos, anuncios, publicaciones en redes sociales y otros esfuerzos de marketing que utiliza su organización.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`v0`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable [`campaign`](/help/implement/vars/page-vars/campaign.md).

## Elementos de dimensión

Los elementos de dimensión incluyen los nombres de los códigos de seguimiento en el sitio. Su organización determina qué elementos de dimensión específicos desea utilizar. Consulte [Seguimiento de la campaña](/help/implement/use-cases/campaign-tracking.md) para obtener más información.

## Comparación de la dimensión Código de seguimiento con los canales de marketing que recopilan códigos de seguimiento

Algunos usuarios que configuran reglas de procesamiento de canal de marketing configuran una regla que toma todos los valores utilizados en la dimensión Código de seguimiento. A pesar de ser una práctica excelente, son diferentes debido a las diferencias inherentes de procesamiento y arquitectura. La siguiente lista explica por qué estos dos métodos, aunque parecidos a primera vista, pueden cambiar el comportamiento de la atribución.

### Canales anteriores en reglas de procesamiento

Las reglas de procesamiento de los canales de marketing que se encuentran más arriba en la lista pueden impedir que las visitas se atribuyan a su canal de marketing de códigos de seguimiento. Por ejemplo:

1. Tiene “Redes sociales” configuradas como la primera regla y “Códigos de seguimiento” como la segunda.
2. Un usuario publica un vínculo a su sitio que contiene un código de seguimiento en un sitio de medios sociales y varios de sus amigos hacen clic en ese vínculo a su sitio.

Dado que “Redes sociales” es la primera regla de procesamiento de canales de marketing, estos usuarios atribuyen el canal de marketing “Redes sociales” y no el canal de marketing de códigos de seguimiento.

### Otros canales de marketing pueden otorgar la atribución mediante el último contacto

Cuando se trata de una dimensión Código de seguimiento estándar, no debe preocuparse por otras partes del sitio que roban la atribución. Sin embargo, con los canales de marketing, un usuario puede hacer coincidir una regla diferente y dar una atribución diferente. Por ejemplo:

1. Tiene “Códigos de seguimiento” como primer canal y “Directo” como segundo.
2. Un usuario llega al sitio inicialmente a través de un código de seguimiento, pero luego sale.
3. Al día siguiente, escriben su dirección URL en la barra de direcciones y luego realizan una compra.

En este ejemplo, el canal de marketing de códigos de seguimiento no obtendría crédito de último contacto para esa compra. En su lugar, iría al canal de marketing “Directo”.


### Diferencias de caducidad

Los canales de marketing tienen una caducidad de participación del visitante de 30 días móviles, independientemente de si hubo contacto con un canal o no. Los códigos de seguimiento tienen una caducidad basada en el momento en que se configuró la variable. Por ejemplo:

1. Tiene una caducidad de la participación del visitante de 30 días y también configuró la dimensión Código de seguimiento para que caduque a los 30 días.
2. Un usuario llega al sitio a través de un código de seguimiento. Exploran el sitio y luego se van.
3. Tres semanas después, regresan sin un código de seguimiento o canal de marketing, y luego se van de nuevo.
4. Otras dos semanas después (cinco semanas después de su visita inicial), regresan sin un código de seguimiento o canal de marketing y luego realizan una compra.

El usuario realizó una compra más allá de los 30 días, pero nunca estuvo inactivo durante más de 30 días. En este caso, vería los ingresos atribuidos al canal de marketing de códigos de seguimiento, pero no a la propia dimensión Código de seguimiento.



