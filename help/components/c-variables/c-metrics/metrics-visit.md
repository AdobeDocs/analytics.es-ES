---
description: Secuencia de vistas de página en una sesión. La métrica de visitas se utiliza comúnmente en informes que muestran el número de sesiones de usuario que se producen en el período de tiempo seleccionado.
keywords: visit
title: Visita
topic: Metrics
uuid: 91317487-f116-4546-8cd2-421418c49a7a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Visita

Secuencia de vistas de página en una sesión. La métrica de visitas se utiliza comúnmente en informes que muestran el número de sesiones de usuario que se producen en el período de tiempo seleccionado.

>[!NOTE] Para obtener información sobre cómo se calculan las visitas y los inicios de aplicaciones móviles, consulte [Comparar visitas e inicios de aplicaciones móviles](https://helpx.adobe.com/es/analytics/kb/compare-visits-and-mobile-app-launches.html) en la Base de conocimiento.

La métrica de visitas siempre se asocia con un período de tiempo, por lo que sabe si contar una visita nueva si el mismo visitante vuelve a su sitio. Una sesión inicio cuando el usuario llega al sitio por primera vez y finaliza en uno de los siguientes casos:

* **30 minutos de inactividad:** Casi todas las sesiones finalizan de esta manera. Si transcurren más de 30 minutos entre solicitudes de imagen, se iniciará una nueva visita.
* **12 horas de actividad consistente:** Si un usuario activa solicitudes de imágenes sin un intervalo de más de 30 minutos durante 12 horas, se crea un inicio automático de una nueva visita.
* **2500 visitas:** Si un usuario genera un gran número de visitas sin iniciar una nueva sesión, se cuenta una nueva visita después de 2500 solicitudes de imagen.
* **100 visitas en 100 segundos**: Si una visita consta de más de 100 visitas que se producen en menos de 100 segundos, la visita finaliza automáticamente. Este comportamiento suele indicar la actividad de bots y esta limitación se impone para evitar que estas visitas intensivas en procesamiento aumenten la latencia y el tiempo necesario para generar informes.

>[!NOTE] La definición de una visita se puede abreviar para un grupo de informes si se solicita específicamente, pero no se puede alargar. Pida a uno de los usuarios de asistencia técnica de su organización que se ponga en contacto con el Servicio de atención al cliente para solicitar este cambio.

Los siguientes escenarios no inicios una nueva visita:

* El usuario cierra la ficha, la vuelve a abrir y regresa al sitio en un plazo de 30 minutos. El usuario también puede cerrar el explorador o reiniciar el equipo y seguir siendo contado como una sola visita (dado que el visitante regresa a su sitio dentro del período de tiempo de 30 minutos).
* Usuarios explorando su sitio en varias fichas. Aunque la exploración con varias fichas no incrementa las visitas ni los visitantes, el uso de un explorador independiente sí lo hace. Esto se debe a que las distintas fichas hacen referencia a las mismas cookies, mientras que los exploradores independientes no.

Una visita no necesariamente coincide con una sesión del explorador. Por ejemplo: si un visitante cierra el explorador, lo vuelve a abrir y llega al sitio cinco minutos después, se reconoce como una continuación de la misma visita. Esto también significa que si un visitante permanece en una página durante 35 minutos, la visita se cerrará y procesará, y una nueva visita se inicio si hace clic en otra página.

Cuando finaliza una visita, todas las variables con una caducidad de visita caducan y ya no persisten. La métrica de número de visitas se incrementará en la próxima visita para este visitante.

>[!NOTE] Si utiliza Analytics como fuente para Adobe Target, consulte la sección sobre [minimización de recuentos inflados de visitas y visitantes en A4T ](https://marketing.adobe.com/resources/help/es_ES/target/a4t/minimizing-inflated-visit-and-visitor-counts-a4t.html) en la [!DNL Target] documentación.

Para obtener más información, consulte [Identificación de Visitantes](https://marketing.adobe.com/resources/help/es_ES/sc/implement/visid_overview.html) únicos en la guía de implementación de Adobe Analytics.

**Períodos de tiempo**

Se informa de una visita en cada período de tiempo en el que se produjo la actividad. Por ejemplo, supongamos que una visita comienza a las 23.45 del 1 de diciembre y continúa hasta las 12.30 del 2 de diciembre. La visita se cuenta el 1 de diciembre y el 2 de diciembre. Este sistema de informes se aplica a otros períodos de tiempo, incluidos semanal, mensual, trimestral y anual.
