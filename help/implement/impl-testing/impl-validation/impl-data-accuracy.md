---
description: La validación de la precisión de los datos es un proceso en el que se comparan los datos de un informe con puntos de datos conocidos y verificables.
keywords: Analytics Implementation
solution: Analytics
title: Validación de la precisión de los datos
topic: Developer and implementation
uuid: 267f6c61-705a-41cf-9e09-4e2ce2331f32
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Validación de la precisión de los datos

La validación de la precisión de los datos es un proceso en el que se comparan los datos de un informe con puntos de datos conocidos y verificables.

El proceso de validación debe realizarlo el personal de Adobe, preferiblemente un consultor de Adobe (la persona más familiarizada con los detalles de implementación técnica).

Los puntos de datos preferidos para esta validación, por orden de preferencia, son los siguientes:

* (Sitios de econversion) Comparación de los pedidos de econversion para un solo día.
* Comparación de los eventos de éxito conocidos, especialmente los datos registrados en los que la dirección IP y otra información del explorador almacenada generalmente en registros de servidores web se puede comparar con los datos recopilados.
* Comparación de las vistas de páginas.

> [!NOTE] Las páginas predeterminadas, como [!DNL index.html], generalmente reciben tráfico automatizado o de seguimiento. Estas páginas muestran diferencias mayores con la recopilación de datos basada en el explorador que otras páginas visitadas.

Los tres tipos de validación requieren un registro de depuración o una fuente de datos para el período de tiempo en cuestión. Generalmente es un día o menos.

Se espera que los pedidos o eventos de éxito se puedan medir con una precisión del 2-3 % respecto a los valores reales (algunas veces se alcanza más precisión) usando implementaciones estándar basadas en JavaScript. Asume que es una página SSL porque las páginas SSL se almacenan en caché con mucha menos frecuencia y, por definición, no deberían almacenarse en caché. Una implementación con solicitudes de imagen que están totalmente en el lado del servidor para una página SSL debe desviarse entre el 0-1 % respecto a los valores reales. Las páginas no seguras pueden experimentar diferencias mayores, pero aún dentro del 5 % respecto a los valores reales.

Cuando se comparan vistas de páginas para un único período de tiempo, se espera que las vistas de página se desvíen un 5 % respecto a los valores reales, sin incluir el tráfico de monitoreo (como Keynote o WhatsUpGold) ni el tráfico automatizado (arañas, bots y scripts).

Al comparar la precisión de los datos, hay que tener en cuenta lo siguiente:

* Los controles de calidad u otros tipos de pruebas internas que pudieran estar filtrados por direcciones IP o reglas de VISTA.
* Etiquetas inteligentes que solo generan etiquetas para determinados tipos de pedidos o tráfico.
* Las consultas de comparación deben tener en cuenta qué está midiendo el sitio web (sin incluir devoluciones, pedidos realizados por el personal de atención al cliente u otras condiciones especiales).
* Asegúrese de que las diferencias de zona horaria entre la consulta y el grupo de informes coinciden.
* Tráfico de Keynote personalizado o similar (transacción de Keynote, etc.) que mide el proceso de pedido y puede reflejarse en las etiquetas, pero que se elimina de los sistemas de pedidos.
* Los procesos de anulación de duplicación del cliente.
* Las recargas de la página de pedidos (la duplicación de los pedidos se anula en función del *`purchaseID`*).

