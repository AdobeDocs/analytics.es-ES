---
description: 'Actualmente existen tres versiones de integración de DFA: 1.0, 1.5, y 2.0.'
keywords: DFA
seo-description: 'Actualmente existen tres versiones de integración de DFA: 1.0, 1.5, y 2.0.'
seo-title: Diferencias de versiones
solution: Analytics
title: Diferencias de versiones
topic: Data Connectors
uuid: e 0 ae 70 f 0-369 d -451 a -9752-02660 d 270660
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Diferencias de versiones{#version-differences}

Actualmente existen tres versiones de integración de DFA: 1.0, 1.5, y 2.0.

La siguiente tabla resume las funciones en cada versión de la integración.

| Función | Versión 1.0 | Versión 1.5 | Versión 2.0 |
|---|---|---|---|
| Métricas por la noche de clics e impresiones de DFA | Sí | Sí | Sí |
| Rastreo de clics y visualizaciones | Sí | Sí | Sí |
| La integración recibe datos en un nivel de Anunciante | No | Sí | Sí |
| La integración recibe datos en un nivel de Configuración de Floodlight | No | No | Sí |
| Métricas de coste | No | No | Sí |
| Métricas de creativo | No | No | Sí |
| Cadenas de consulta más allá de 2k bytes | No | Sí | Sí |
| Usa el módulo Integrate para una recopilación de datos óptima de terceros | No | Sí | Sí |
| Rastreo de tiempos de espera y errores | No | Sí | Sí |
| Sin necesidad de ID del cliente negociado | No | No | Sí |

## Acerca de la versión 1.5 {#section-b5a3e967cfa141ea8f740612336181be}

La versión 1.5 de la integración introduce el módulo Integrate al JavaScript de la página de aterrizaje. El módulo Integrate permite solicitudes de tamaño fijo al servidor de publicidad de DFA (ad.doubleclick.net) que supera los límites de solicitudes de 2K de la integración previa. También introduce un tiempo de espera que se puede configurar, *`s.maxDelay`*, para seguir recopilando datos de visitantes de Adobe cuando ocurren interrupciones de red. Los errores y el tiempo de espera también se pueden capturar en variables de Analytics.

La siguiente ilustración muestra interacciones de red en la página de aterrizaje en la versión 1.5.

![](assets/DFA_About_1_5.png)

En la versión 1.5, el módulo Integrate (2) solicita datos del Servidor de Floodlight (3). El Servidor de Floodlight redireccionará al servidor de publicidad de DFA, que devolverá datos sobre el visitante de la misma manera que la versión 1.0. Redireccionará 302 (4) a un servicio de traductor especial en integrate.112.2o7.net, que convertirá la estructura de la respuesta en un objeto JSON. El módulo Integrate consume este objeto JSON y pasa la información al Seguimiento de Adobe (5).

Al pasar de la Versión 1.0 de la integración a 1.5 hay un cambio de JavaScript. Para obtener este JavaScript, inicie sesión en su cuenta de Adobe Online Marketing Suite, elija el producto Genesis, haga clic en Editar en la integración DFA y continúe con el asistente. Siempre y cuando se haya asignado previamente un ID de sitio de cliente, una vez que haya guardado la integración recibirá inmediatamente el nuevo código JavaScript por correo electrónico. Una vez que tenga este código, la nueva versión del s_code principal será necesaria con el módulo Integrate. Este código se puede solicitar al Administrador de cuentas o al Asesor de implementación.

Una función importante del nuevo código JavaScript es que no se necesita ningún cambio de implementación entre la versión 1.5 y la versión 2.0.

## Acerca de la versión 2.0 {#section-afd56de0c56c4489bb5ddc5798d6709a}

La última versión de la integración DFA incorpora datos para una Configuración de Floodlight completa en la integración. Antes de la versión 2.0, las integraciones individuales estaban ligadas a un solo Anunciante de DFA. Con este cambio las métricas de Clics, Impresiones y Costes para la Configuración de Floodlight completa se incluirán en el grupo de informes integrado. También es posible rastrear visualizaciones entre sitios, cuando los dos sitios se encuentren en la misma Configuración de Floodlight.

Las métricas de Coste de medios también están disponibles desde la versión 2.0 de la integración. Para habilitar métricas de coste de medios para una integración, debe elegir un evento de Informes y análisis para Coste de medios en el asistente Genesis, así como también especificar en qué moneda se encuentran las figuras de métricas en la interfaz de DFA.

Se espera que los tiempos de espera disminuyan con la integración 2.0, puesto que se han eliminado los redireccionamientos 302. La eliminación de estos saltos debería disminuir los tiempos de espera e incrementar la cantidad de datos DFA que puede integrar.

Si una Configuración de Floodlight es una configuración compartida en DFA, la actualización de la versión 1. 5 a 2.0 hace que los datos de conversión para todos los anunciantes compartidos dentro de la Configuración de Floodlight se incluyan en el grupo de informes.

## Actualización a la versión 2.0 {#section-f0bf90b9a7a1434ab1540b6c0999f4c7}

La siguiente tabla describe los propietarios para migración a versiones más nuevas de la integración:

| Migración | Propietario | Tareas |
|---|---|---|
| Versión 1.0 a 1.5 | Cliente | Implementar JavaScript versión 1.5 con el módulo Integrate |
| Versión 1.5 a 2.0 | Cliente | El cliente comienza una conversación con Google sobre períodos de tiempo para la actualización. Después de la aprobación, Google habilita el Servicio de publicidad avanzado. |

