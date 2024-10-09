---
title: Visitas
description: Secuencia de visitas de la página efectuadas en una sesión.
feature: Metrics
exl-id: 4f78f2b5-f958-44fe-876a-83f07980beec
source-git-commit: a3a23e1d13bc10305a8cb991b73c2873a58baf63
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 98%

---

# Visitas

La [métrica](overview.md) “Visitas” muestra el número de sesiones en todos los visitantes del sitio.

## Cálculo de esta métrica

Una visita se vincula siempre a un periodo de tiempo, para que sepa si se debe contar una nueva visita si la misma persona vuelve al sitio. Una visita inicia cuando el usuario llega al sitio por primera vez. Una visita finaliza cuando cumple cualquiera de los siguientes criterios:

* **30 minutos de inactividad**: Casi todas las sesiones finalizan de esta forma. Si pasan más de 30 minutos entre cada visita individual, se inicia una nueva visita.
* **12 horas de actividad**: Si un usuario activa las solicitudes de imagen de forma consistente sin interrupciones de 30 minutos durante más de 12 horas, se iniciará automáticamente una nueva visita.
* **2500 visitas**: Si un usuario genera un gran número de visitas sin iniciar una sesión nueva, se cuenta una visita nueva después de 2500 solicitudes de imagen.
* **100 visitas en 100 segundos**: si una visita tiene más de 100 visitas que se producen en los primeros 100 segundos de la visita, la visita finaliza automáticamente. Este comportamiento suele indicar la actividad de bots y esta limitación se impone para ayudar a aumentar el rendimiento del informe.

Una visita no necesariamente coincide con una sesión del explorador debido a los criterios anteriores. Una de las diferencias más comunes se produce cuando un visitante navega hasta el sitio, deja la pestaña abierta durante más de 30 minutos y luego reanuda la exploración. Aunque esta acción es técnicamente parte de la misma sesión de navegación, Adobe considera que esta acción genera dos visitas separadas.

## Comportamiento que afecta a las visitas

Si un visitante realiza cualquiera de estas acciones, se da comienzo a una nueva visita:

* Elimina las cookies a mitad de la sesión y continúa explorando el sitio
* Deja el sitio abierto en una pestaña durante más de 30 minutos y, a continuación, continúa explorando
* Abre un explorador diferente y navega al sitio en el mismo equipo
* La misma persona que explora el sitio en diferentes dispositivos

Si un visitante realiza cualquiera de estas acciones, una nueva visita **no se inicia** siempre y cuando haya menos de 30 minutos entre visitas individuales consecutivas:

* Cierra el explorador y luego navega al sitio nuevamente
* Reinicia el equipo, abre el mismo explorador y vuelve a navegar al sitio
* Pasa a una red diferente, como cuando se desconecta de red por cable y se conecta a una red inalámbrica
* Navega por el sitio en varias pestañas. Si un visitante cambia de una pestaña a otra, cada visita individual se cuenta como parte de la misma visita.

## Cambiar la definición de una visita

Puede cambiar el tiempo necesario para la definición de una visita a un intervalo de tiempo diferente a 30 minutos.

* Para los [grupos de informes virtuales](../vrs/vrs-about.md), puede cambiar el tiempo de espera de visita mediante la lista desplegable [!UICONTROL Tiempo de espera de visita]. Puede cambiar el tiempo de espera de visita a cualquier valor razonable.
* Para los grupos de informes estándar, póngase en contacto con el Servicio de atención al cliente para solicitar que la duración de la visita se acorte en un grupo de informes determinado. La duración de la visita para los grupos de informes estándar no puede exceder los 30 minutos, por lo que solo puede abreviarse.

## Visitas que abarcan un límite de fecha

Una visita se contabiliza por cada periodo de tiempo involucrado. Por ejemplo, si tiene un visitante que empieza a navegar por el sitio el lunes a las 23:45 y envía su última solicitud de imagen el martes a las 00:10, en el informe aparecerá una visita atribuida tanto al lunes como al martes. Sin embargo, se deduplica la métrica de visitas totales y se muestra una sola visita para el intervalo de fechas del proyecto.

## Visitas en una dimensión o visitas totales

Las visitas en el contexto de una dimensión (por ejemplo, [Canal de marketing](../dimensions/marketing-channel.md)) muestran el número de visitas que contenían un elemento de dimensión en particular en cualquier momento. Con frecuencia existen varios elementos de dimensión en distintas visitas individuales en la misma visita. Normalmente no tiene sentido intentar sumar visitas que informan sobre elementos de dimensión.

## Visitas de todos los visitantes en Data Warehouse

La métrica Visitas - Todos los visitantes está disponible en Data Warehouse además de la métrica Visitas. La métrica Visitas - Todos los visitantes es comparable a la métrica Visitas de otras herramientas de Analytics. La métrica Visitas de Data Warehouse excluye a los visitantes que no tienen cookies persistentes. Adobe recomienda usar Visitas - Todos los visitantes en solicitudes de Data Warehouse en las que se desean ver visitas como métricas.
