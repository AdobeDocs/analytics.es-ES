---
title: Tiempo empleado
description: Una página agregada de dimensiones y métricas de tiempo empleado.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '1577'
ht-degree: 100%

---


# Información general sobre el tiempo empleado

Los productos de Adobe Analytics ofrecen varias métricas y dimensiones de [!UICONTROL “tiempo empleado”].

## Métricas de “tiempo empleado”

| Métrica | Definición | Disponible en |
|---|---|---|
| [!UICONTROL Segundos totales empleados] | Representa el tiempo total durante el cual los visitantes interactúan con un elemento de dimensión específico. Incluye la instancia de un valor y persistencia en todas las visitas individuales posteriores. En el caso de las props, el tiempo empleado también se cuenta en los eventos de vínculo siguientes. | Analysis Workspace, Reports &amp; Analytics, Report Builder (llamado “tiempo total empleado”), Data Warehouse, Ad Hoc Analysis |
| [!UICONTROL Tiempo empleado por visita] (segundos) | *Segundos totales empleados (devoluciones)*<br> representa el tiempo medio durante el cual los visitantes interactúan con un elemento de dimensión específico durante cada visita. | Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis |
| [!UICONTROL Tiempo empleado por visitante] (segundos) | *Segundos totales empleados (visitantes únicos)*<br> representa el tiempo medio durante el cual los visitantes interactúan con un elemento de dimensión específico a lo largo de la duración de la visita (la duración de su cookie). | Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis |
| [!UICONTROL Tiempo promedio empleado en el sitio] (segundos) | Representa el tiempo total durante el cual los visitantes interactúan con un elemento de dimensión específico, por secuencia con un elemento de dimensión. No se limita al promedio del “sitio”, como su nombre sugiere. Consulte la sección “Cómo se calcula el tiempo empleado” para obtener más información sobre las secuencias.<br>**Nota:** Es muy probable que, en el nivel de elemento de dimensión, esta métrica difiera del “Tiempo empleado por visita” debido a diferencias en el denominador del cálculo. | Analysis Workspace, Reports &amp; Analytics (se muestra en minutos), Report Builder (se muestra en minutos), Ad Hoc Analysis |
| [!UICONTROL Tiempo promedio empleado en la página] | Métrica obsoleta.<br> En su lugar, se recomienda el uso de “Tiempo promedio empleado en el sitio” si se necesita el tiempo promedio para un elemento de dimensión. | Report Builder (cuando hay una dimensión en la solicitud) |
| [!UICONTROL Duración total de la sesión], también conocida como [!UICONTROL Duración de la sesión anterior] | Solo SDK de aplicaciones móviles. <br>Se determina para la sesión anterior la próxima vez que se inicia la aplicación. Esta métrica se calcula en segundos y no cuenta cuando la aplicación se encuentra en segundo plano, solo cuando está en uso. Es una métrica de nivel de sesión.<br>Por ejemplo: instalamos la aplicación ABC, la iniciamos, la utilizamos durante 2 minutos y la cerramos. No se envía ningún dato acerca de la duración de la sesión. La próxima vez que la iniciemos, el valor de [!UICONTROL Duración total de la sesión] se establecerá en 120. | Analysis Workspace, Reports &amp; Analytics, Report Builder, interfaz de usuario de Mobile Services |
| [!UICONTROL Longitud promedio de la sesión] (móvil) | *Duración total de la sesión (inicios y primeros arranques)*<br> solo SDK de la aplicación móvil. Es una métrica de nivel de sesión. | Report Builder, interfaz de usuario de Mobile Services, Ad Hoc Analysis |

## Dimensiones de “Tiempo empleado”

| Dimensión | Definición | Disponible en |
|---|---|---|
| [!UICONTROL Tiempo empleado por visita (pormenorizado)] | El tiempo total empleado durante la visita, truncado al segundo más cercano y aplicado a todas las visitas individuales que formaron parte de la visita. Es una dimensión de nivel de visita. | Analysis Workspace, Ad Hoc Analysis |
| [!UICONTROL Tiempo empleado por visita (agrupado)] | La dimensión pormenorizada, agrupada en 9 intervalos distintos. Es una dimensión de nivel de visita. Los intervalos son:<ul><li>Menos de 1 minuto</li><li>1 a 5 minutos</li><li>5 a 10 minutos</li><li>10 a 30 minutos</li><li>30 a 60 minutos</li><li>1 a 2 horas</li><li>2 a 5 horas</li><li>5 a 10 horas</li><li>10 a 15 horas</li></ul>**Nota**: No puede haber bloques superiores a este, ya que las visitas caducan tras 12 horas de actividad. | Analysis Workspace, Reports &amp; Analytics, Report Builder, Ad Hoc Analysis |
| [!UICONTROL Tiempo empleado en la página (pormenorizado)] | El tiempo total empleado en cada visita individual, truncado al segundo más cercano. Es una dimensión de nivel de visita e incluye tanto las vistas de página como los eventos de vínculo. A pesar de su nombre, no se limita a la dimensión “página”. | Analysis Workspace, Ad Hoc Analysis |
| [!UICONTROL Tiempo empleado en la página (agrupado)] | La dimensión pormenorizada, agrupada en 10 intervalos distintos; sin embargo, la dimensión agrupada solo cuenta vistas de página (y excluye los eventos de vínculo). Es una dimensión de nivel de visita individual. Los intervalos son:<ul><li>menos de 15 segundos</li><li>de 15 a 29 segundos</li><li>de 30 a 59 segundos</li><li>de 1 a 3 minutos</li><li>de 3 a 5 minutos</li><li>de 5 a 10 minutos</li><li>de 10 a 15 minutos</li><li>de 15 a 20 minutos</li><li>de 20 a 30 minutos</li><li>más de 30 minutos</li></ul> | Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis |

## Cálculo del “Tiempo empleado”

Adobe Analytics utiliza valores explícitos (incluidos eventos de vínculo y vistas de vídeo) para calcular la métrica [!UICONTROL Tiempo empleado].

>[!NOTE]
>
>Sin eventos de vínculo como las [!UICONTROL vistas de vídeo] o los [!UICONTROL vínculos de salida], no se puede saber el tiempo empleado en la última visita individual de una visita. Por motivos similares, las [!UICONTROL visitas de devolución] (las visitas con una sola visita individual) no tienen asociado un valor de “Tiempo empleado”.

El **numerador** en todos los cálculos de tiempo empleado es “Segundos totales empleados”.

El **denominador** no está disponible como una métrica separada en Adobe Analytics. Para métricas de “Tiempo empleado” de nivel de visita individual, el denominador son secuencias. Una secuencia es un conjunto consecutivo de visitas individuales en el que una variable dada contiene el mismo valor (por configuración, por propagarse hacia delante o por persistir). “Propagarse hacia delante” se refiere a la conservación de las props entre vistas de página (es decir, entre eventos de vínculo subsiguientes) con el propósito de calcular el tiempo empleado.

* Por ejemplo, en el caso de [!UICONTROL Nombre de página] u otras dimensiones de nivel de visitas individuales, el denominador es esencialmente [!UICONTROL “Instancias”] o [!UICONTROL “Vistas de página”], pero contando las recargas y los valores sin configurar (por ejemplo, eventos de vínculo) como una sola interacción (una secuencia).

* Las visitas individuales de Devolución y Salida también se eliminan del denominador porque no es posible saber el “Tiempo empleado”.

## Preguntas frecuentes

**Pregunta 1: ¿Es posible aplicar todas las métricas de “Tiempo empleado” a cualquier dimensión?**

Respuesta: Las métricas de “Tiempo empleado” que se pueden aplicar a cualquier dimensión son:

* [!UICONTROL Segundos totales empleados]

* [!UICONTROL Tiempo empleado por visita] (segundos)

* [!UICONTROL Tiempo empleado por visitante] (segundos)

* [!UICONTROL Tiempo promedio empleado en el sitio] (segundos)

**Pregunta 2: ¿Qué dimensión de tiempo empleado es más apropiada para su desglose con otras dimensiones?**

Respuesta: [!UICONTROL “Tiempo empleado en la página (pormenorizado)”] es una dimensión de nivel de visita individual. Desglosarla mediante otra dimensión indicará los segundos que duró una visita individual en la que la dimensión de desglose también estaba presente.
En el ejemplo siguiente, el término de búsqueda “classifieds” se asocia a los tiempos de visita individual de 54 segundos, 59 segundos, etc., tal vez indicando que los visitantes pasan tiempo leyendo el contenido devuelto por el término de búsqueda.

![](assets/time-spent1.png)

**Pregunta 3: ¿Qué métrica es apropiada para la dimensión [!UICONTROL Tiempo empleado en la página (pormenorizado)]?**

Respuesta: Cualquier métrica. La dimensión muestra el tiempo empleado en la visita individual exacta en la que se produjo el evento. Un tiempo empleado mayor significa que un visitante pasó más tiempo en una página (visita individual) en la que se produjo el evento.

![](assets/time-spent2.png)

**Pregunta 4: ¿En qué se diferencian [!UICONTROL Tiempo promedio empleado en el sitio] y [!UICONTROL Tiempo empleado por visita]?**

Respuesta: La diferencia es el denominador de la métrica:

* [!UICONTROL Tiempo promedio empleado en el sitio] utiliza las secuencias que incluyen un elemento de dimensión.

* [!UICONTROL Tiempo empleado por visita] utiliza el recuento de visitas.

Como resultado, ambas métricas pueden arrojar resultados similares en el nivel de visita, pero distintos en el de visita individual.

**P5: ¿Por qué el desglose de totales con[!UICONTROL Tiempo promedio invertido en el sitio]no coincide con el elemento de línea principal?**

R: Debido a que el [!UICONTROL tiempo promedio invertido en el sitio] depende de secuencias no interrumpidas de una dimensión y el informe interno no depende del informe externo al calcular estas ejecuciones.

Por ejemplo, usemos esta visita:

| visita# | 1 | 2 | 3 |
|---|---|---|---|
| **Segundos empleados** | 30 | 100 | 10 |
| **Nombre de la página** | Página principal | Product | Página principal |
| **date** | 1 de enero | 1 de enero | 1 de enero |

Al calcular el tiempo de espera para la página principal sería (30+10)/2=20, pero desglosar ese valor por día daría (30+10)/1=40, ya que el día tiene una sola ejecución no interrumpida del 1 de enero.

Como resultado, ambas métricas pueden arrojar resultados similares en el nivel de visita, pero distintos en el de visita individual.

## Ejemplos de cálculos de [!UICONTROL Tiempo empleado]

Supongamos que el siguiente conjunto de llamadas de servidor es para un único visitante dentro de una sola visita:

| N.º de visita individual de la visita | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **Tiempo de visita transcurrido (en segundos)** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **Segundos empleados** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **Tipo de visita** | Página | Vínculo | Página | Página | Página | Página | Página |
| **Nombre de la página** | Página principal | - | Product | Página principal | Página principal (recarga) | Carro de compras | Confirmación del pedido |
|  |  |  |  |  |  |  |  |
| **prop1** | A (configurado) | A (propagarse hacia delante) | sin configurar | B (configurado) | B (configurado) | A(configurado) | C (configurado) |
| **Segundos empleados por prop1** | 30 | 50 | - | 10 | 40 | 60 | - |
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

* “Segundos empleados” es la diferencia entre la marca de tiempo de la visita individual actual y la de la visita individual siguiente. Como resultado, la última visita individual de la visita (y las devoluciones) carecen de tiempo empleado.

* Una “secuencia” es un conjunto consecutivo de visitas individuales en el que una variable dada contiene el mismo valor (por configuración, por propagarse hacia delante o por persistir). Por ejemplo, prop1 “A” tiene dos secuencias: las visitas individuales 1 y 2, y la visita individual 6. Los valores en la última visita individual de la visita no comienzan una nueva secuencia porque la última visita individual no tiene valor de tiempo empleado. El tiempo promedio empleado en un sitio utiliza secuencias en el denominador.

   * Solo para los propósitos de Tiempo empleado, las props se “propagan hacia delante” desde las visitas individuales de página hacia las visitas individuales de vínculo subsiguientes, como se muestra arriba para la visita individual n.º 2 de prop1. Esto permite que el valor configurado para prop1 en la visita individual n.º 1 (“A”) acumule el tiempo empleado en la visita individual n.º 2.

   * Las eVars acumulan tiempo empleado en cualquier visita individual en las que estén configuradas o persistan. La persistencia de una eVar se define en la configuración de eVar, en Analytics > Administración.
