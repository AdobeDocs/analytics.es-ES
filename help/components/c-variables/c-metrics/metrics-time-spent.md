---
description: Adobe Analytics ofrece varias métricas y dimensiones de Tiempo empleado. Averigüe qué son y cómo se calculan.
solution: Analytics
title: Tiempo empleado
topic: Metrics
translation-type: tm+mt
source-git-commit: e04051a655a842092f3d99ba784a738e86d65eb2

---


# [!UICONTROL Tiempo empleado]

Los productos de Adobe Analytics ofrecen varias métricas y dimensiones [!UICONTROL de tiempo empleado] .

## [!UICONTROL Métricas de tiempo empleado]

| Métrica | Definición | Disponible en |
|---|---|---|
| [!UICONTROL Segundos totales empleados] | Representa el tiempo total que los visitantes interactúan con un elemento de dimensión específico. Incluye la instancia de un valor y la persistencia en todas las visitas posteriores. En el caso de las props, el tiempo empleado también se cuenta en los eventos de vínculo siguientes. | Analysis Workspace, Informes y análisis, Creador de informes (llamado "tiempo total empleado"), Almacén de datos, Análisis específicos |
| [!UICONTROL Tiempo empleado por visita] (segundos) | *Segundos totales empleados / (devoluciones de visita)*<br>Representa la cantidad promedio de tiempo que los visitantes interactúan con un elemento de dimensión específico durante cada visita. | Analysis Workspace, Informes y análisis, Análisis específicos |
| [!UICONTROL Tiempo empleado por visitante] (segundos) | *Segundos totales empleados /*<br>visitante únicoRepresenta la cantidad promedio de tiempo que los visitantes interactúan con un elemento de dimensión específico durante toda la vida del visitante (la duración de la cookie). | Analysis Workspace, Informes y análisis, Análisis específicos |
| [!UICONTROL Tiempo promedio empleado en el sitio] (segundos) | Representa el tiempo total que los visitantes interactúan con un elemento de dimensión específico, por secuencia con un elemento de dimensión. No se limita al promedio del “sitio”, como su nombre sugiere. Consulte la sección "Cómo se calcula el tiempo empleado" para obtener más información sobre las secuencias.<br>**Nota**: Es muy probable que esta métrica difiera de 'Tiempo empleado por visita' en un nivel de elemento de dimensión debido a las diferencias en el denominador en el cálculo. | Analysis Workspace, Informes y análisis (se muestra en minutos), Creador de informes (se muestra en minutos), Análisis específicos |
| [!UICONTROL Tiempo promedio empleado en la página] | Métrica obsoleta.<br> En su lugar, se recomienda utilizar "Tiempo promedio empleado en el sitio" si se necesita tiempo promedio para un elemento de dimensión. | Report Builder (cuando hay una dimensión en la solicitud) |
| [!UICONTROL Duración]total de la sesión, también conocida como Duración de la sesión [!UICONTROL anterior] | Solo SDK de aplicaciones móviles. <br>Se determina para la sesión anterior la próxima vez que se inicia la aplicación. Esta métrica se calcula en segundos y no cuenta cuando la aplicación se encuentra en segundo plano, solo cuando está en uso. Es una métrica de nivel de sesión.<br>Ejemplo: Instalamos la aplicación ABC, la iniciamos y la usamos durante 2 minutos y luego la cerramos. No se envían datos sobre la hora de esta sesión. The next time we launch the app, [!UICONTROL Previous Session Length] will be sent with a value of 120. | Analysis Workspace, Informes y análisis, Creador de informes, Interfaz de usuario de Mobile Services |
| [!UICONTROL Duración] media de la sesión (móvil) | *Duración total de la sesión / (Inicios - Primeros inicios)SDK de la aplicación*<br>móvil únicamente. Es una métrica de nivel de sesión. | Creador de informes, interfaz de usuario de Mobile Services, análisis específicos |

## Dimensiones 'Tiempo empleado'

| Dimensión | Definición | Disponible en |
|---|---|---|
| [!UICONTROL Tiempo empleado por visita (granular)] | El tiempo total empleado durante la visita, truncado al segundo más cercano y aplicado a todas las visitas individuales que formaron parte de la visita. Es una dimensión de nivel de visita. | Analysis Workspace, Análisis específicos |
| [!UICONTROL Tiempo empleado por visita - General] | La dimensión granular, agrupada en 9 intervalos distintos. Es una dimensión de nivel de visita. Los intervalos son:<ul><li>Menos de 1 minuto</li><li>1 a 5 minutos</li><li>5 a 10 minutos</li><li>10 a 30 minutos</li><li>30 a 60 minutos</li><li>1 a 2 horas</li><li>2 a 5 horas</li><li>5 a 10 horas</li><li>10 a 15 horas</li></ul>**Nota**: No puede haber bloques superiores a esto, ya que una visita caduca después de 12 horas de actividad. | Analysis Workspace, Informes y análisis, Creador de informes, Análisis específicos |
| [!UICONTROL Tiempo empleado en la página (granular)] | El tiempo total empleado en cada visita individual, truncado al segundo más cercano. Se trata de una dimensión de nivel de visita individual que incluye vistas de página y eventos de vínculo. A pesar de su nombre, no se limita a la dimensión "página". | Analysis Workspace, Análisis específicos |
| [!UICONTROL Tiempo empleado en la página (general)] | La dimensión granular, agrupada en 10 intervalos distintos; sin embargo, la dimensión agrupada solo cuenta vistas de página (y excluye los eventos de vínculo). Es una dimensión de nivel de visita individual. Los intervalos son:<ul><li>menos de 15 segundos</li><li>de 15 a 29 segundos</li><li>de 30 a 59 segundos</li><li>de 1 a 3 minutos</li><li>de 3 a 5 minutos</li><li>de 5 a 10 minutos</li><li>de 10 a 15 minutos</li><li>de 15 a 20 minutos</li><li>de 20 a 30 minutos</li><li>más de 30 minutos</li></ul> | Analysis Workspace, Informes y análisis, Análisis específicos |

## Cálculo del tiempo empleado

Adobe Analytics utiliza valores explícitos (incluidos eventos de vínculo y vistas de vídeo) para calcular la métrica [!UICONTROL Tiempo empleado].

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. For similar reasons, [!UICONTROL Bounce Visits] (i.e. visits with a single hit) also does not have a 'time spent' associated with it.

The **numerator** in all time spent calculations is total seconds spent.

The **denominator** is not available as a separate metric in Adobe Analytics. Para las métricas de "tiempo empleado" de nivel de visita individual, el denominador son secuencias. Una secuencia es un conjunto consecutivo de visitas individuales en el que una variable dada contiene el mismo valor (por configuración, por propagarse hacia delante o por persistir). 'Propagar hacia delante' se refiere a la persistencia de props entre vistas de página (es decir, a través de eventos de vínculo subsiguientes), con el fin de calcular el tiempo empleado.

* For example, in the case of [!UICONTROL Page Name] or other dimensions at the hit level, the denominator is essentially [!UICONTROL 'Instances'] or [!UICONTROL 'Page Views'], but with reloads and unset values (e.g. link events) counted as a single interaction (a sequence).

* Las visitas de salida y de devolución también se eliminan del denominador porque no se puede saber el tiempo empleado.

## Preguntas frecuentes

**T1: ¿Se pueden aplicar todas las métricas de tiempo empleado a cualquier dimensión?**

A: Las métricas de tiempo empleado que se pueden aplicar a cualquier dimensión son:

* [!UICONTROL Segundos totales empleados]

* [!UICONTROL Tiempo empleado por visita] (segundos)

* [!UICONTROL Tiempo empleado por visitante] (segundos)

* [!UICONTROL Tiempo promedio empleado en el sitio] (segundos)

**Segundo trimestre: ¿Qué dimensión de tiempo empleado se utiliza mejor en los desgloses con otras dimensiones?**

A: The [!UICONTROL Time Spent on Page – granular] dimension is a hit-level dimension. Desglosarla mediante otra dimensión indicará los segundos que duró una visita individual en la que la dimensión de desglose también estaba presente.
En el ejemplo siguiente, el término de búsqueda "classifieds" se asocia con tiempos de visita de 54 segundos, 59 segundos, etc., tal vez indicando que los visitantes invierten tiempo leyendo el contenido devuelto para ese término.

![](assets/time-spent1.png)

**Tercer trimestre: ¿Qué métrica es apropiada para la dimensión de[!UICONTROL Tiempo empleado en la página (granular])?**

A: Cualquier métrica. La dimensión mostrará el tiempo empleado en la visita individual exacta en la que se produjo el evento. Un tiempo empleado mayor significa que un visitante pasó más tiempo en una página (visita individual) en la que se produjo el evento.

![](assets/time-spent2.png)

**T4: ¿En qué se diferencia el tiempo[!UICONTROL promedio invertido en el sitio]del[!UICONTROL tiempo empleado por visita]?**

A: La diferencia es el denominador de la métrica:

* [!UICONTROL El tiempo promedio invertido en el sitio] utiliza las secuencias que incluyen un elemento de dimensión.

* [!UICONTROL El tiempo empleado por visita] utiliza el recuento de visitas

Como resultado, ambas métricas pueden arrojar resultados similares en el nivel de visita, pero distintos en el de visita individual.

## Ejemplos de cálculos de [!UICONTROL tiempo empleado]

Supongamos que el siguiente conjunto de llamadas de servidor es para un único visitante dentro de una sola visita:

| N.º de visita individual de la visita | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **Tiempo de visita transcurrido (en segundos)** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **Segundos empleados** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **Tipo de visita** | Activity Map | Vínculo | Activity Map | Activity Map | Activity Map | Activity Map | Activity Map |
| **Nombre de la página** | Página principal | - | Producto | Página principal | Página principal (recarga) | Carro de compras | Confirmación del pedido |
|  |  |  |  |  |  |  |  |
| **prop1** | A (configurado) | A (propagado hacia delante) | sin configurar | B (conjunto) | B (conjunto) | A(configurado) | C (configurado) |
| **Segundos empleados por prop1** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar1** | Rojo (configurado) | Rojo (persistente) | (caducado) | Azul (configurado) | Azul (conjunto) | Azul (persistente) | Rojo (conjunto) |
| **Segundos empleados de eVar1** | 30 | 50 | - | 10 | 40 | 60 | - |

En base a la tabla anterior, las métricas de tiempo empleado se calculan de la siguiente manera:

| prop1 | Segundos totales empleados | Tiempo empleado por visita | Tiempo empleado por visitante | Recuento de secuencias | Tiempo promedio empleado en el sitio |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| Tiempo no atribuido | 100 | - | - | - | - |

| eVar1 | Segundos totales empleados | Tiempo empleado por visita | Tiempo empleado por visitante | Recuento de secuencias | Tiempo promedio empleado en el sitio |
|---|---|---|---|---|---|
| Rojo | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| Azul | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| Tiempo no atribuido | 100 | - | - | - | - |

Tiempo empleado por visita (granular): 290Tiempo empleado en la página (granular): 10, 30, 40, 50, 60, 100

Algunas notas adicionales para complementar el ejemplo:

* Todos los cálculos del tiempo empleado se basan en el tiempo transcurrido de la visita, que comienza en cero en la primera visita individual de la visita.

* "Segundos empleados" es la diferencia entre la marca de tiempo de la visita actual y la marca de tiempo de la siguiente visita. Como resultado, la última visita individual de la visita (y las devoluciones) carecen de tiempo empleado.

* Una “secuencia” es un conjunto consecutivo de visitas individuales en el que una variable dada contiene el mismo valor (por configuración, por propagarse hacia delante o por persistir). Por ejemplo, prop1 “A” tiene dos secuencias: las visitas individuales 1 y 2, y la visita individual 6. Los valores en la última visita individual de la visita no comienzan una nueva secuencia porque la última visita individual no tiene valor de tiempo empleado. El tiempo promedio empleado en un sitio utiliza secuencias en el denominador.

   * Para los fines del tiempo empleado solamente, las props se "propagan hacia delante" desde las visitas individuales de página hasta las visitas individuales de vínculo subsiguientes, como se muestra arriba para prop1 en la visita individual 2. Esto permite que el valor configurado para prop1 en la visita individual n.º 1 (“A”) acumule el tiempo empleado en la visita individual n.º 2.

   * Las eVars acumulan el tiempo empleado en cualquier visita individual en la que la eVar esté configurada o persista. La persistencia de eVar se define mediante la configuración de eVar en Analytics &gt; Administración.

