---
title: Visitas
description: Secuencia de visitas de la página efectuadas en una sesión.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 5%

---


# Visitas

La métrica &quot;Visitas&quot; muestra el número de sesiones en todos los visitantes del sitio.

## Cómo se calcula esta métrica

Una visita siempre se vincula a un período de tiempo, por lo que usted sabe si contar una nueva visita si la misma persona regresa a su sitio. Una visita inicio cuando el usuario llega al sitio por primera vez. Una visita finaliza cuando cumple cualquiera de los siguientes criterios:

* **30 minutos de inactividad**: Casi todas las sesiones finalizan de esta manera. Si transcurren más de 30 minutos entre las visitas individuales, se iniciará una nueva visita.
* **12 horas de actividad**: Si un usuario activa las solicitudes de imagen de forma consistente sin espacios de 30 minutos durante más de 12 horas, se crea un inicio automático de una nueva visita.
* **2500 visitas**: Si un usuario genera un gran número de visitas sin iniciar una nueva sesión, se cuenta una nueva visita después de 2500 solicitudes de imagen.
* **100 visitas en 100 segundos**: si una visita consta de más de 100 visitas que se producen en menos de 100 segundos, la visita finaliza automáticamente. Este comportamiento suele indicar la actividad de bots y esta limitación se impone para ayudar a aumentar el rendimiento del informe.

Una visita no necesariamente coincide con una sesión del explorador debido a los criterios anteriores. Una de las diferencias más comunes es dónde un visitante navega hasta el sitio, deja la ficha abierta durante más de 30 minutos y luego reanuda la exploración. Aunque esta acción es técnicamente parte de la misma sesión de navegación, Adobe considera esta acción como dos visitas separadas.

## Comportamiento que afecta a las visitas

Si un visitante realiza cualquiera de estas acciones, una nueva visita inicio:

* Borra la caché a mitad de la sesión y continúa explorando el sitio
* Deja el sitio abierto en una ficha durante más de 30 minutos y, a continuación, continúa explorando
* Abre un explorador diferente y navega al sitio en el mismo equipo
* La misma persona que explora el sitio en diferentes dispositivos

Si un visitante realiza cualquiera de estas acciones, una nueva visita **no tiene** inicios siempre y cuando haya menos de 30 minutos entre visitas individuales consecutivas:

* Cierra el explorador y luego navega al sitio nuevamente
* Reinicia el equipo, abre el mismo explorador y vuelve a navegar al sitio
* Transiciones a una red diferente, como la desconexión de una estación de acoplamiento de red cableada a una red inalámbrica
* Navega por el sitio en varias fichas. Si un visitante cambia de una ficha a otra, cada visita se cuenta como parte de la misma visita.

## Cambiar la definición de una visita

Puede cambiar la definición de una visita a una hora que no sea de 30 minutos.

* Para los grupos [de informes](../vrs/vrs-about.md)virtuales, puede cambiar el tiempo de espera de visita mediante la lista desplegable Tiempo de espera [!UICONTROL de] visita. Puede cambiar el tiempo de espera de visita a cualquier valor razonable.
* Para los grupos de informes estándar, póngase en contacto con el Servicio de atención al cliente para solicitar que la duración de la visita se acorte en un grupo de informes determinado. La duración de la visita para los grupos de informes estándar no puede exceder los 30 minutos, por lo que solo puede abreviarla.

## Visitas que abarcan un límite de fecha

Una visita se contabiliza por cada período de tiempo involucrado. Por ejemplo: si tiene un visitante que indica que los inicios que navegan por su sitio el lunes a las 11:45 p.m. y luego envían su última solicitud de imagen el martes a las 12:10 a.m., verá una visita atribuida tanto al lunes como al martes. Sin embargo, se anula la duplicación de la métrica de visitas totales y se muestra una sola visita para el intervalo de fechas del proyecto.

## Visitas en una dimensión versus visitas totales

Las visitas en el contexto de una dimensión (por ejemplo, [Marketing canal](../dimensions/marketing-channel.md)) muestran el número de visitas que contenían un elemento de dimensión en particular en cualquier momento. Existen varios elementos de dimensión con frecuencia en distintas visitas individuales en la misma visita. Normalmente no tiene sentido intentar sumar visitas que informan sobre elementos de dimensión.
