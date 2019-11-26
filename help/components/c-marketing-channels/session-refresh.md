---
title: Canal interno (Actualización de sesión)
description: Obtenga información sobre el canal Interno (Actualización de sesión).
translation-type: tm+mt
source-git-commit: 490a856effac7ec3ff2430dff0ffdcee587bf933

---


# Canal interno (Actualización de sesión)

El canal interno (con frecuencia denominado Actualización de sesión) consiste en visitas al sitio donde la dirección URL de referencia coincide con la configuración de los filtros de URL internos en la Consola de administración, lo que significa que el visitante vino desde dentro del sitio para iniciar la visita.

![](assets/int-channel1.png)

## Omitir prácticas recomendadas

Se recomienda desactivar la opción de anulación del último toque para los canales directos e internos, de modo que no puedan tomar crédito de otros canales de último toque persistentes (o entre sí).

>[!NOTE]Este documento supone que la actualización directa y de sesión tienen la opción Anular configuración desactivada.

![](assets/int-channel2.png)

## Período de compromiso

Los canales de primer y último toque de un visitante se restablecen tras 30 días de inactividad en ese explorador.

>[!NOTE] 30 días es el valor predeterminado y se puede modificar según sea necesario mediante la configuración de administración.

Si el visitante utiliza el sitio con frecuencia, la ventana de participación se abrirá. Deben estar inactivos durante 30 días para que caduque el período y se restablezcan los canales.
Ejemplo:

* Día 1: El usuario ingresa al sitio en la pantalla. Los canales de primer y último toque se definirán como Mostrar.

* Día 2: El usuario ingresa al sitio en búsqueda natural. El primer toque permanece como visualización y el último toque se establece como búsqueda natural.

* Día 35: El usuario no ha estado en el sitio en 33 días y regresa usando la ficha que había abierto en su explorador. Suponiendo una ventana de participación de 30 días, la ventana se habría cerrado y las cookies del canal de mercadotecnia habrían caducado. El canal de primer toque y último toque se restablecerá y se establecerá en Actualización de sesión, ya que el usuario procedió de una URL interna.

## Relación entre primer y último toque

Para comprender la interacción entre el primer y el último toque, y confirmar que las sobrescrituras funcionan según lo esperado, puede extraer un informe de canal de primer toque, subrelacionado con un informe de canal de último toque, con la métrica de éxito clave en (ver ejemplo más abajo). En el ejemplo se muestra la interacción entre los canales de primer y último toque.

![](assets/int-channel3.png)

La intersección en la que el primer toque es igual que el último toque se resalta en naranja. Tanto la actualización directa como la actualización de sesión solo obtienen crédito de último toque si también son el canal de primer toque, ya que no pueden tomar crédito de otros canales persistentes (filas resaltadas en gris).

## ¿Por qué se produce la actualización de la sesión?

Como sabemos que la actualización de sesión de último toque solo puede producirse si también fue el primer toque, los escenarios siguientes explican cómo la actualización de sesión puede ser un canal de primer toque.

### Escenario 1: Tiempo de espera de sesión

Un visitante llega al sitio web y luego deja la ficha abierta en el explorador para usarla en una fecha posterior. El período de compromiso del visitante caduca (o elimina voluntariamente sus cookies) y utiliza la ficha de apertura para volver a visitar el sitio web. Dado que la dirección URL de referencia es un dominio interno, la visita se clasificará como Actualización de sesión.

### Escenario 2: No todas las páginas del sitio están etiquetadas

Un visitante aterriza en la Página A que no está etiquetada y luego se mueve a la página B que está etiquetada. La página A se vería como el referente interno y la visita se clasificaría como Actualización de sesión.

### Escenario 3: Redirecciones

Si no se configura una redirección para pasar datos del referente a la nueva página de aterrizaje, se pierden los datos del referente de entrada real y ahora la página de redirección (probablemente una página interna) aparece como el dominio de referencia. La visita se clasificará como Actualización de sesión.

### Escenario 4: Tráfico entre dominios

Un visitante pasa de un dominio que se activa a la Suite A a un segundo dominio que se activa a la Suite B. Si en la Suite B los filtros de URL internos incluyen el primer dominio, la visita en la Suite B se registrará como interna, ya que los canales de mercadotecnia la ven como una nueva visita en el segundo grupo. La visita se clasificará como Actualización de sesión.

### Escenario 5: Largos tiempos de carga de la página de entrada

Un visitante llega a la página A, que tiene mucho contenido, y el código de Adobe Analytics se encuentra en la parte inferior de la página. Antes de cargar todo el contenido (incluida la solicitud de imagen de Adobe Analytics), el visitante hace clic en la página B. La página B activa su solicitud de imagen de Adobe Analytics. Dado que la solicitud de imagen de la página A nunca se cargó, la segunda página aparece como la primera visita individual de la visita en Adobe Analytics, con la página A como referente. La visita se clasifica como Actualización de sesión.

### Escenario 6: Borrado de cookies en el sitio intermedio

Un visitante ingresa al sitio y luego borra sus cookies a mitad de la sesión. Los canales de primer y último toque se restablecerían y la visita se clasificaría como Actualización de sesión (porque el referente sería interno).
