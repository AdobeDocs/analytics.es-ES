---
description: Adobe Analytics oferta varias métricas y dimensiones de tiempo empleado. Averiguar cuáles son y cómo se calculan.
title: Tiempo empleado
topic: Metrics
translation-type: tm+mt
source-git-commit: 8df1fdfb048dd69b4926b7b812ec5dfea4a97b89

---


# [!UICONTROL Time spent]

Various [!UICONTROL 'time spent'] metrics and dimensions are offered across Adobe Analytics products.

## [!UICONTROL 'Time spent'] métricas

| Métrica | Definición | Disponible en |
|---|---|---|
| [!UICONTROL Total seconds spent] | Representa el tiempo total durante el cual los visitantes interactúan con un elemento de dimensión específico. Incluye la instancia de un valor y persistencia en todas las visitas individuales posteriores. En el caso de las props, el tiempo empleado también se cuenta en los eventos de vínculo siguientes. | Analysis Workspace, Reports &amp; Analytics, Report Builder (llamado “tiempo total empleado”), Data Warehouse, Ad Hoc Analysis |
| [!UICONTROL Time spent per visit] (Seconds) | *Segundos totales empleados (devoluciones)*<br>representa el tiempo medio durante el cual los visitantes interactúan con un elemento de dimensión específico durante cada visita. | Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis |
| [!UICONTROL Time spent per visitor] (Seconds) | *Segundos totales empleados (visitantes únicos)*<br> representa el tiempo medio durante el cual los visitantes interactúan con un elemento de dimensión específico a lo largo de la duración de la visita (la duración de su cookie). | Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis |
| [!UICONTROL Average time spent on site] (Seconds) | Representa el tiempo total durante el cual los visitantes interactúan con un elemento de dimensión específico, por secuencia con un elemento de dimensión. No se limita solamente a los promedios del &quot;sitio&quot; como sugiere el nombre. Consulte la sección “Cómo se calcula el tiempo empleado” para obtener más información sobre las secuencias.<br>**Nota:** Es muy probable que, en el nivel de elemento de dimensión, esta métrica difiera del “Tiempo empleado por visita” debido a diferencias en el denominador del cálculo. | Analysis Workspace, Reports &amp; Analytics (se muestra en minutos), Report Builder (se muestra en minutos), Ad Hoc Analysis |
| [!UICONTROL Average time spent on page] | Métrica obsoleta.<br> En su lugar, se recomienda el uso de “Tiempo promedio empleado en el sitio” si se necesita el tiempo promedio para un elemento de dimensión. | Report Builder (cuando hay una dimensión en la solicitud) |
| [!UICONTROL Total session length], alias [!UICONTROL Previous session length] | Solo SDK de aplicaciones móviles. <br>Se determina para la sesión anterior la próxima vez que se inicia la aplicación. Esta métrica, calculada en segundos, no se cuenta cuando la aplicación está en segundo plano, solo cuando está en uso. Es una métrica de nivel de sesión.<br>Por ejemplo: instalamos la aplicación ABC, la iniciamos, la utilizamos durante 2 minutos y la cerramos. No se envía ningún dato acerca de la duración de la sesión. The next time we launch the app, [!UICONTROL Previous Session Length] will be sent with a value of 120. | Analysis Workspace, Reports &amp; Analytics, Report Builder, interfaz de usuario de Mobile Services |
| [!UICONTROL Average session length] (mobile) | *Duración total de la sesión (inicios y primeros arranques)*<br>solo SDK de la aplicación móvil. Es una métrica de nivel de sesión. | Report Builder, interfaz de usuario de Mobile Services, Ad Hoc Analysis |

## Dimensiones de “Tiempo empleado”

| Dimensión | Definición | Disponible en |
|---|---|---|
| [!UICONTROL Time spent per visit - granular] | El tiempo total empleado durante la visita, truncado al segundo más cercano y aplicado a todas las visitas individuales que formaron parte de la visita. Es una dimensión de nivel de visita. | Analysis Workspace, Ad Hoc Analysis |
| [!UICONTROL Time spent per visit - bucketed] | La dimensión pormenorizada, agrupada en 9 intervalos distintos. Es una dimensión de nivel de visita. Los intervalos incluyen:<ul><li>Menos de 1 minuto</li><li>1 a 5 minutos</li><li>5 a 10 minutos</li><li>10 a 30 minutos</li><li>30 a 60 minutos</li><li>1 a 2 horas</li><li>2 a 5 horas</li><li>5 a 10 horas</li><li>10 a 15 horas</li></ul>**Nota**: No puede haber bloques superiores a este, ya que las visitas caducan tras 12 horas de actividad. | Analysis Workspace, Reports &amp; Analytics, Report Builder, Ad Hoc Analysis |
| [!UICONTROL Time spent on page - granular] | El tiempo total empleado en cada visita individual, truncado al segundo más cercano. Es una dimensión de nivel de visita e incluye tanto las vistas de página como los eventos de vínculo. A pesar de su nombre, no se limita a la dimensión “página”. | Analysis Workspace, Ad Hoc Analysis |
| [!UICONTROL Time spent on page - bucketed] | La dimensión pormenorizada, agrupada en 10 intervalos distintos; sin embargo, la dimensión agrupada solo cuenta vistas de página (y excluye los eventos de vínculo). Es una dimensión de nivel de visita individual. Los intervalos incluyen:<ul><li>menos de 15 segundos</li><li>de 15 a 29 segundos</li><li>de 30 a 59 segundos</li><li>1 a 3 minutos</li><li>3 a 5 minutos</li><li>5 a 10 minutos</li><li>10 a 15 minutos</li><li>15 a 20 minutos</li><li>20 a 30 minutos</li><li>más de 30 minutos</li></ul> | Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis |

## Cálculo del “Tiempo empleado”

Adobe Analytics uses explicit values (including link events and video views) to calculate [!UICONTROL Time Spent].

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. For similar reasons, [!UICONTROL Bounce Visits] (i.e. visits with a single hit) also does not have a &#39;time spent&#39; associated with it.

El **numerador** en todos los cálculos de tiempo empleado es “Segundos totales empleados”.

El **denominador** no está disponible como una métrica separada en Adobe Analytics. Para métricas de “Tiempo empleado” de nivel de visita individual, el denominador son secuencias. Una secuencia es un conjunto consecutivo de visitas individuales en el que una variable dada contiene el mismo valor (por configuración, por propagarse hacia delante o por persistir). “Propagarse hacia delante” se refiere a la conservación de las props entre vistas de página (es decir, entre eventos de vínculo subsiguientes) con el propósito de calcular el tiempo empleado.

* For example, in the case of [!UICONTROL Page Name] or other dimensions at the hit level, the denominator is essentially [!UICONTROL 'Instances'] or [!UICONTROL 'Page Views'], but with reloads and unset values (e.g. link events) counted as a single interaction (a sequence).

* Las visitas individuales de Devolución y Salida también se eliminan del denominador porque no es posible saber el “Tiempo empleado”.

## Preguntas frecuentes

**Pregunta 1: ¿Es posible aplicar todas las métricas de “Tiempo empleado” a cualquier dimensión?**

Respuesta: Las métricas de “Tiempo empleado” que se pueden aplicar a cualquier dimensión son:

* [!UICONTROL Total seconds spent]

* [!UICONTROL Time spent per visit] (Seconds)

* [!UICONTROL Time spent per visitor] (Seconds)

* [!UICONTROL Average time spent on site] (Seconds)

**Pregunta 2: ¿Qué dimensión de tiempo empleado es más apropiada para su desglose con otras dimensiones?**

A: La [!UICONTROL Time Spent on Page – granular] dimensión es una dimensión de nivel de visita individual. Desglosarla mediante otra dimensión indicará los segundos que duró una visita individual en la que la dimensión de desglose también estaba presente.
En el ejemplo siguiente, el término de búsqueda “classifieds” se asocia a los tiempos de visita individual de 54 segundos, 59 segundos, etc., tal vez indicando que los visitantes pasan tiempo leyendo el contenido devuelto por el término de búsqueda.

![](assets/time-spent1.png)

**Tercer trimestre: ¿Qué métrica es apropiada para la dimensión de[!UICONTROL Time Spent on Page – granular]?**

Respuesta: Cualquier métrica. La dimensión muestra el tiempo empleado en la visita individual exacta en la que se produjo el evento. Un tiempo empleado mayor significa que un visitante pasó más tiempo en una página (visita individual) en la que se produjo el evento.

![](assets/time-spent2.png)

**T4: ¿En qué se diferencia[!UICONTROL Average Time Spent on Site]de[!UICONTROL Time Spent per Visit]?**

Respuesta: La diferencia es el denominador de la métrica:

* [!UICONTROL Average time spent on site] utiliza las secuencias que incluyen un elemento de dimensión.

* [!UICONTROL Time spent per visit] utiliza el recuento de visitas

Como resultado, ambas métricas pueden arrojar resultados similares en el nivel de visita, pero distintos en el de visita individual.

**T5: ¿Por qué los totales de desglose no[!UICONTROL Average Time Spent on Site]coinciden con el elemento de línea principal?**

A: Porque [!UICONTROL Average Time Spent on Site] depende de secuencias ininterrumpidas de una dimensión y el informe interno no depende del informe externo al calcular estas ejecuciones.

Por ejemplo, considere la siguiente visita.
|hit#|1|2|3||—|—|—|—||**Segundos empleados**|30|100|10||Nombre **** de página|Inicio|Producto|Inicio||**fecha**|Ene 1|Ene 1|Ene 1|

Al calcular el tiempo de espera para la página principal sería (30+10)/2=20, pero desglosar ese valor por día daría (30+10)/1=40, ya que el día tiene una sola ejecución no interrumpida del 1 de enero.

Como resultado, ambas métricas pueden arrojar resultados similares en el nivel de visita, pero distintos en el de visita individual.

## Ejemplos de [!UICONTROL Time Spent] cálculos

Supongamos que el siguiente conjunto de llamadas de servidor es para un único visitante dentro de una sola visita:

| N.º de visita individual de la visita | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **Tiempo de visita transcurrido (en segundos)** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **Segundos empleados** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **Tipo de visita individual** | Página | Vínculo | Página | Página | Página | Página | Página |
| **Nombre de la página** | Página principal | - | Product | Página principal | Página principal  (recarga) | Carro de compras | Confirmación del pedido |
|  |  |  |  |  |  |  |  |
| **prop1** | A  (configurado) | A (propagarse hacia delante) | sin configurar | B (configurado) | B (configurado) | A(configurado) | C  (configurado) |
| **prop1 segundos empleados** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar1** | Rojo (configurado) | Rojo (conservado) | (caducado) | Azul (configurado) | Azul (configurado) | Azul (conservado) | Rojo (configurado) |
| **Segundos empleados por eVar1** | 30 | 50 | - | 10 | 40 | 60 | - |

En función de la tabla anterior, la métrica de tiempo empleado se calcula del modo siguiente:

| prop1 | Segundos totales empleados | Tiempo empleado por visita | Tiempo empleado por visitante | Número de secuencias | Tiempo promedio empleado en el sitio |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| Tiempo no atribuido | 100 | - | - | - | - |

| eVar1 | Segundos totales empleados | Tiempo empleado por visita | Tiempo empleado por visitante | Número de secuencias | Tiempo promedio empleado en el sitio |
|---|---|---|---|---|---|
| Rojo | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| Azul | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| Tiempo no atribuido | 100 | - | - | - | - |

Tiempo empleado por visita (granular): 290
Tiempo empleado en la página (granular): 10, 30, 40, 50, 60, 100

Algunas notas adicionales para complementar el ejemplo:

* Todos los cálculos del tiempo empleado se basan en el tiempo transcurrido de visita, que comienza en cero en la primera visita individual de la visita.

* “Segundos empleados” es la diferencia entre la marca de tiempo de la visita individual actual y la de la visita individual siguiente. Como resultado, la última visita individual de la visita (y las devoluciones) no tienen tiempo empleado.

* Una &quot;secuencia&quot; es un conjunto consecutivo de visitas individuales en el que una variable dada contiene el mismo valor (ya sea por estar configurada, propagarse hacia delante o persistir). Por ejemplo, prop1 &quot;A&quot; tiene dos secuencias: visitas individuales 1 y 2 y visita individual 6. Los valores de la última visita individual de la visita no inicio una nueva secuencia porque la última visita individual no tiene tiempo empleado. El tiempo promedio invertido en el sitio utiliza secuencias en el denominador.

   * Solo para los propósitos de Tiempo empleado, las props se “propagan hacia delante” desde las visitas individuales de página hacia las visitas individuales de vínculo subsiguientes, como se muestra arriba para la visita individual n.º 2 de prop1. Esto permite que el valor configurado para prop1 en la visita individual n.º 1 (“A”) acumule el tiempo empleado en la visita individual n.º 2.

   * Las eVars acumulan tiempo empleado en cualquier visita individual en las que estén configuradas o persistan. La persistencia de una eVar se define en la configuración de eVar, en Analytics > Administración.

