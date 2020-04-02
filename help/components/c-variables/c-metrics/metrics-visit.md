---
description: Secuencia de visitas de la página efectuadas en una sesión. La métrica de visitas se utiliza comúnmente en informes que muestran el número de sesiones de usuario que se producen en el período de tiempo seleccionado.
keywords: visit
title: Visita
topic: Metrics
uuid: 91317487-f116-4546-8cd2-421418c49a7a
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visita

Secuencia de visitas de la página efectuadas en una sesión. La métrica de visitas se utiliza comúnmente en informes que muestran el número de sesiones de usuario que se producen en el período de tiempo seleccionado.

> [!NOTE] Para obtener información sobre cómo se calculan las visitas y los inicios de aplicaciones móviles, consulte [Comparar visitas e inicios de aplicaciones móviles](https://helpx.adobe.com/es/analytics/kb/compare-visits-and-mobile-app-launches.html) en la Base de conocimiento.

La métrica de visitas siempre se asocia con un período de tiempo, por lo que sabe si contar una visita nueva si el mismo visitante vuelve a su sitio. Una sesión se inicia cuando el usuario accede por primera vez al sitio y finaliza cuando se da uno de los escenarios siguientes:

* **30 minutos de inactividad**: casi todas las sesiones finalizan de este modo. Si pasan más de 30 minutos entre las solicitudes de imagen, se inicia una nueva sesión.
* **12 horas de actividad constante**: si un usuario activa solicitudes de imagen sin que haya transcurrido un lapso de más de 30 minutos durante 12 horas, se iniciará automáticamente una nueva visita.
* **2500 visitas**: si un usuario genera un gran número de visitas sin iniciar una sesión nueva, se cuenta una visita nueva después de 2500 solicitudes de imagen.
* **100 visitas en 100 segundos**: si una visita consta de más de 100 visitas que se producen en menos de 100 segundos, la visita finaliza automáticamente. Este comportamiento normalmente indica la actividad bot, y su limitación sirve para evitar que estas visitas intensivas de procesamiento aumenten la latencia y el tiempo que se tarda en generar informes.

> [!NOTE] La definición de una visita se puede abreviar para un grupo de informes si se solicita específicamente, pero no se puede alargar. Para ello, un usuario de asistencia técnica debe ponerse en contacto con el Servicio de atención al cliente.

Los escenarios siguientes no inician una nueva visita:

* El usuario cierra y vuelve a abrir la pestaña, y navega de nuevo al sitio en un lapso de 30 minutos. Aunque el usuario cierre el explorador o reinicie el ordenador, seguirá considerándose como una única visita (puesto que regresa al sitio dentro del período de tiempo de 30 minutos).
* Un usuario explora el sitio usando varias pestañas. Aunque la exploración en varias pestañas no incrementa el número de visitas o visitantes, si se usa otro explorador sí se incrementa. Esto se debe a que las distintas pestañas hacen referencia a las mismas cookies, mientras que un explorador diferente no.

Una visita no es necesariamente lo mismo que una sesión de navegador. Si un visitante cierra el navegador, lo vuelve a abrir y regresa al sitio cinco minutos después, se reconoce como continuación de la visita original. Esto también significa que si un visitante permanece en una página durante 35 minutos, la visita se cierra y se procesa; si luego hace clic y abre otra página, se considerará que es el comienzo de otra visita.

Cuando una visita finaliza, caducan y dejan de persistir todas las variables con una caducidad de visita. La métrica de número de visitas será incrementada en la siguiente visita para este visitante.

> [!NOTE] Si utiliza Analytics como fuente para Adobe Target, consulte la sección sobre [minimización de recuentos inflados de visitas y visitantes en A4T ](https://marketing.adobe.com/resources/help/es_ES/target/a4t/minimizing-inflated-visit-and-visitor-counts-a4t.html) en la [!DNL Target] documentación.

Para obtener más información, consulte [Identificación de visitantes únicos](https://marketing.adobe.com/resources/help/es_ES/sc/implement/visid_overview.html) en la Guía de implementación de Adobe Analytics.

**Períodos de tiempo**

Se informa una visita en cada período de tiempo en que hubo actividad. Por ejemplo, supongamos que una visita comienza a las 23.45 del 1 de diciembre, y continúa hasta las 00.30 del 2 de diciembre. La visita se cuenta el 1 de diciembre y el 2 de diciembre. Este método de informes se aplica a los demás períodos de tiempo, como semanal, mensual, trimestral y anual.
