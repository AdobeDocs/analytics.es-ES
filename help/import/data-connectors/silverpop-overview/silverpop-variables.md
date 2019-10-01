---
description: La integración de Data Connectors para Silverpop utiliza variables de Analytics para rastrear distintas métricas de Silverpop.
seo-description: La integración de Data Connectors para Silverpop utiliza variables de Analytics para rastrear distintas métricas de Silverpop.
seo-title: Variables de integración de Analytics
title: Variables de integración de Analytics
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Analytics Integration Variables{#analytics-integration-variables}

La integración de Data Connectors para Silverpop utiliza variables de Analytics para rastrear distintas métricas de Silverpop.

Después de identificar el evento y las eVars que se usarán con la integración de Silverpop, utilice la Consola de administración de Adobe Analytics para habilitarlos (consulte Grupos [de informes](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)).

En la tabla siguiente se describen las variables de Analytics necesarias para la integración de Silverpop.

## Variables requeridas {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Tipo de variable | Nombre  | Método de obtención de datos | Descripción |
|---|---|---|---|
| event (numérico) | Devoluciones | Se importa automáticamente desde Silverpop. | El evento Devoluciones permite ver el número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. |
| event (numérico) | Clics | Se importa automáticamente desde Silverpop. | El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. |
| event (numérico) | Abre | Se importa automáticamente desde Silverpop. | El evento Abrir permite ver el número de visitantes que abrieron el mensaje de correo electrónico. |
| event (numérico) | Envía | Se importa automáticamente desde Silverpop. | El evento Envíos permite ver el número de mensajes de correo electrónico que se han enviado. |
| event (numérico) | Cancelar suscripciones | Se importa automáticamente desde Silverpop. | El evento Cancelar suscripción le permite ver el número de visitantes que abrieron el mensaje de correo electrónico y luego hicieron clic en el vínculo Cancelar suscripción para rechazar futuros mensajes de correo electrónico de su organización. |
| eVar | ID de Silverpop/ID de visitante | Recopilado a partir de parámetros de consulta en vínculos de correo electrónico mediante el método de recopilación automatizada o un complemento de JavaScript. | ID de visitante único |
| eVar o s.campaign | ID de correo | Recopilado a partir de parámetros de consulta en vínculos de correo electrónico mediante el método de recopilación automatizada o un complemento de JavaScript. | Esto generalmente se almacena en la variable de campaña. |

## Variables opcionales {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Tipo de variable | Nombre  | Método de obtención de datos | Descripción |
|---|---|---|---|
| event (contador) | Archivo descargado | Recopilado manualmente mediante etiquetas de Analytics. | Este evento se utiliza para identificar a los usuarios que descargaron un archivo en el sitio. |
| event (contador) | Formulario iniciado | Recopilado manualmente mediante etiquetas de Analytics. | Formulario iniciado se utiliza para identificar a los usuarios que comienzan un formulario pero no lo completan. |
| event (contador) | Formulario completado | Recopilado manualmente mediante etiquetas de Analytics. | Formulario completado se utiliza para identificar a los visitantes que comienzan un formulario y no lo completan. |
| eVar | Email Address | Recopilado manualmente mediante etiquetas de Analytics. | La dirección de correo electrónico es para recopilar manualmente la dirección de correo electrónico al registrarse, iniciar sesión u otras páginas en las que se recopila la dirección de correo electrónico. Esta variable se utiliza para volver a comercializar a los usuarios que han elegido recibir correo electrónico, pero es posible que no hayan hecho clic anteriormente a través de un correo electrónico. |
| eVar | Archivo descargado | Recopilado manualmente mediante etiquetas de Analytics. | El archivo descargado identifica qué archivo descargó un visitante. |
| eVar | Nombre del formulario | Recopilado manualmente mediante etiquetas de Analytics. | Nombre del formulario identifica qué formulario abandonó un visitante. |

