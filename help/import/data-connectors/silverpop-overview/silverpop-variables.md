---
description: La integración de Data Connectors para Silverpop usa variables de Analytics para rastrear distintas métricas de Silverpop.
title: Variables de integración de Analytics
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variables de integración de Analytics {#analytics-integration-variables}

La integración de Data Connectors para Silverpop usa variables de Analytics para rastrear distintas métricas de Silverpop.

Después de identificar el evento y las eVars que se van a usar con la integración de Silverpop, utilice la Admin Console de Adobe Analytics para habilitarlos (consulte [Grupos de informes](https://docs.adobe.com/content/help/es-ES/analytics/admin/manage-report-suites/report-suites-admin.html)).

La siguiente tabla describe las variables de Analytics que se necesitan para la integración de Silverpop.

## Variables requeridas {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Tipo de variable | Nombre | Método de obtención de datos | Descripción |
|---|---|---|---|
| Evento (numérico) | Devoluciones | Se importa automáticamente desde Silverpop. | El evento de devoluciones permite ver el número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| Evento (numérico) | Clics | Se importa automáticamente desde Silverpop. | El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. |
| Evento (numérico) | Aperturas | Se importa automáticamente desde Silverpop. | El evento de aperturas (Opened) permite ver el número de visitantes que abrieron el mensaje de correo electrónico. |
| Evento (numérico) | Enviados | Se importa automáticamente desde Silverpop. | El evento de enviados permite ver el número de mensajes de correo electrónico que se han enviado. |
| Evento (numérico) | Cancelación de suscripción | Se importa automáticamente desde Silverpop. | El evento de cancelación de suscripción (Unsuscribed) le permite ver el número de visitantes que abrieron el mensaje de correo electrónico y luego hicieron clic en el vínculo Cancelar suscripción para rechazar futuros mensajes de correo electrónico de su organización. |
| eVar | ID de Silverpop/ID de visitante | Recopilado a partir de parámetros de consulta en vínculos de correo electrónico mediante el método de recopilación automatizada o un complemento de JavaScript. | ID de visitante único |
| eVar o s.campaign | ID de correo | Recopilado a partir de parámetros de consulta en vínculos de correo electrónico mediante el método de recopilación automatizada o un complemento de JavaScript. | Generalmente se almacena en la variable de campaña. |

## Variables opcionales {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Tipo de variable | Nombre | Método de obtención de datos | Descripción |
|---|---|---|---|
| Evento (contador) | Descarga de archivos | Recopilado manualmente mediante etiquetas de Analytics. | Este evento se utiliza para identificar a los usuarios que descargaron un archivo en el sitio. |
| Evento (contador) | Formulario iniciado | Recopilado manualmente mediante etiquetas de Analytics. | Se utiliza para identificar a los usuarios que comienzan un formulario, pero no lo completan. |
| Evento (contador) | Formulario completado | Recopilado manualmente mediante etiquetas de Analytics. | Se utiliza para identificar a los visitantes que comienzan un formulario y no lo completan. |
| eVar | Dirección de correo electrónico | Recopilado manualmente mediante etiquetas de Analytics. | Para recopilar manualmente la dirección de correo electrónico al registrarse, iniciar sesión u otras páginas en las que se recopila la dirección de correo electrónico. Esta variable se utiliza para volver a enviar marketing a los usuarios que han elegido recibir correo electrónico, pero es posible que no hayan hecho clic anteriormente a través de uno. |
| eVar | Archivo descargado | Recopilado manualmente mediante etiquetas de Analytics. | Identifica qué archivo descargó un visitante. |
| eVar | Nombre del formulario | Recopilado manualmente mediante etiquetas de Analytics. | Identifica qué formulario abandonó un visitante. |

