---
description: La integración de Data Connectors para Silverpop usa variables de Analytics para rastrear distintas métricas de Silverpop.
seo-description: La integración de Data Connectors para Silverpop usa variables de Analytics para rastrear distintas métricas de Silverpop.
seo-title: Variables de integración de Analytics
title: Variables de integración de Analytics
uuid: 3 aef 3 caf-e 24 e -4 fe 7-b 4 d 7-50 ca 0 f 6703 b 5
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Analytics Integration Variables{#analytics-integration-variables}

La integración de Data Connectors para Silverpop usa variables de Analytics para rastrear distintas métricas de Silverpop.

Después de identificar el evento y las evars que se van a utilizar con la integración de Silverpop, use la Consola de administración de Adobe Analytics para habilitarlos (consulte [Grupos de informes](http://microsite.omniture.com/t2/help/en_US/reference/index.html?f=report_suites_admin)).

La siguiente tabla describe las variables de Analytics necesarias para la integración de Silverpop.

## Variables requeridas {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Tipo de variable | Nombre  | Método de obtención de datos | Descripción |
|---|---|---|---|
| event (numérico) | Devoluciones | Importado automáticamente desde Silverpop. | El evento Devoluciones permite ver la cantidad de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| event (numérico) | Clics | Importado automáticamente desde Silverpop. | El evento Clics permite ver la cantidad de visitantes que hicieron clic en el mensaje de correo electrónico. |
| event (numérico) | Aperturas | Importado automáticamente desde Silverpop. | El evento Abierto permite ver la cantidad de visitantes que abrieron el mensaje de correo electrónico. |
| event (numérico) | Envíos | Importado automáticamente desde Silverpop. | El evento Envíos permite ver la cantidad de mensajes de correo electrónico que se enviaron. |
| event (numérico) | Cancelar suscripción | Importado automáticamente desde Silverpop. | El evento Sin suscripción permite ver la cantidad de visitantes que abrieron el mensaje de correo electrónico pero luego hicieron clic en el vínculo Cancelar suscripción para rechazar los futuros mensajes de correo electrónico de su organización. |
| eVar | ID de Silverpop/ID de visitante | Se recopilan de los parámetros de consulta en vínculos de correo electrónico a través del método de recopilación automatizada o de un complemento JavaScript. | ID de visitante único |
| Evar o s. campaign | ID de correo | Se recopilan de los parámetros de consulta en vínculos de correo electrónico a través del método de recopilación automatizada o de un complemento JavaScript. | Esto suele almacenarse en la variable de campaña. |

## Variables opcionales {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Tipo de variable | Nombre  | Método de obtención de datos | Descripción |
|---|---|---|---|
| event (contador) | Archivo descargado | Se recopilan manualmente mediante etiquetas de Analytics. | Este evento se utiliza para identificar a los usuarios que descargaron un archivo en el sitio. |
| event (contador) | Formulario iniciado | Se recopilan manualmente mediante etiquetas de Analytics. | El formulario iniciado se utiliza para identificar a los usuarios que comienzan un formulario, pero no lo completan. |
| event (contador) | Formulario completado | Se recopilan manualmente mediante etiquetas de Analytics. | El formulario completado se utiliza para identificar a los visitantes que comienzan un formulario y no lo completan. |
| eVar | Email Address | Se recopilan manualmente mediante etiquetas de Analytics. | La dirección de correo electrónico sirve para recopilar manualmente la dirección de correo electrónico en el registro, inicio de sesión u otras páginas donde se recopila la dirección de correo electrónico. Esta variable se utiliza para remercadotecnia con los usuarios que han elegido recibir correos electrónicos, pero quizás no hayan hecho clic en un mensaje de correo electrónico pasado. |
| eVar | Archivo descargado | Se recopilan manualmente mediante etiquetas de Analytics. | Archivo descargado identifica qué archivo ha descargado un visitante. |
| eVar | Nombre del formulario | Se recopilan manualmente mediante etiquetas de Analytics. | El Nombre del formulario identifica qué formulario abandonó un visitante. |

