---
description: Las sesiones según el contexto en los grupos de informes virtuales cambian el modo en que Adobe Analytics calcula las visitas con dispositivos móviles. En este artículo se describen las implicaciones de procesamiento que las visitas individuales y eventos de inicio de aplicaciones en segundo plano (todos ellos establecidos por el SDK para móviles) tienen para el modo en que se definen las visitas con dispositivos móviles.
title: Sesiones según el contexto
uuid: d354864a-9163-4970-a3a0-f2e9729bdbe3
translation-type: tm+mt
source-git-commit: 3997889ae72920d719203edbb159b55b983158e7

---


# Sesiones según el contexto

Las sesiones con contexto en los grupos de informes virtuales cambian la forma en que Adobe Analytics calcula las visitas desde cualquier dispositivo. En este artículo también se describen las implicaciones de procesamiento de las visitas individuales en segundo plano y los eventos de inicio de la aplicación (ambos definidos por el SDK móvil) en la definición de las visitas con dispositivos móviles.

Puede definir una visita como desee sin alterar los datos subyacentes para que coincida con la forma en que sus visitantes interactúan con sus experiencias digitales.

## Parámetro URL de perspectiva de cliente 

El proceso de recopilación de datos de Adobe Analytics le permite establecer un parámetro de cadena de consulta que especifica la perspectiva del cliente (denominado parámetro de cadena de consulta &quot;cp&quot;). Este campo especifica el estado de la aplicación digital del usuario final. Esto le ayuda a saber si se generó una visita mientras una aplicación móvil estaba en segundo plano.

## Procesamiento de visitas en segundo plano 

Una visita en segundo plano es un tipo de visita que se envía a Analytics desde la versión 4.13.6 y posteriores del SDK de Adobe Mobile cuando la aplicación realiza una solicitud de seguimiento mientras se encuentra en segundo plano. Algunos ejemplos típicos de esto son:

* Datos enviados durante el cruce de una valla geográfica
* Una interacción de notificación push

Los siguientes ejemplos describen la lógica utilizada para determinar cuándo una visita inicio y finaliza para cualquier visitante cuando la opción &quot;Impedir que las visitas en segundo plano inicien una nueva visita&quot; está o no habilitada para un grupo de informes virtuales.

**Si “Impedir que las visitas en segundo plano inicien una nueva visita” no está habilitado:**

Si esta función no está habilitada para un grupo de informes virtuales, las visitas en segundo plano se tratan igual que cualquier otra visita, lo que significa que tienen el inicio de nuevas visitas y actúan igual que las visitas en primer plano. Por ejemplo, si una visita en segundo plano se produce menos de 30 minutos (el tiempo de espera de sesión estándar para un grupo de informes) antes de un conjunto de visitas en primer plano, la visita en segundo plano es parte de la sesión.

![](assets/nogood1.jpg)

Si la visita en segundo plano se produce más de 30 minutos antes de cualquier visita en primer plano, la visita en segundo plano crea su propia visita, para un recuento total de visitas de 2.

![](assets/nogood2.jpg)

**Si “Impedir que las visitas en segundo plano inicien una nueva visita” está habilitado:**

Los siguientes ejemplos ilustran el comportamiento de las visitas en segundo plano cuando esta función está habilitada.

Ejemplo 1: Se produce una visita en segundo plano un tiempo (t) antes de una serie de visitas en primer plano.

![](assets/nogoodexample1.jpg)

En este ejemplo, si *t* es bueno al tiempo de espera de visita configurado del grupo de informes virtuales, la visita en segundo plano se excluye de la visita formada por las visitas en primer plano. Por ejemplo: si el tiempo de espera de visita del grupo de informes virtuales se estableció en 15 minutos y *t* fue de 20 minutos, la visita formada por esta serie de visitas (mostrada por el contorno verde) excluiría la visita en segundo plano. Esto significa que cualquier eVar configurada con una caducidad de &quot;visita&quot; en la visita en segundo plano **no persistirá** en la siguiente visita y un contenedor de segmento de visita solo incluirá las visitas en primer plano dentro del contorno verde.

![](assets/nogoodexample1-2.jpg)

Por el contrario, si *t* es menor que el tiempo de espera de visita configurado del grupo de informes virtuales, la visita en segundo plano se incluye como parte de la visita como si fuera una visita en primer plano (como se muestra en el contorno verde):

![](assets/nogoodexample1-3.jpg)

Esto significa que:

* Todas las eVars configuradas con caducidad de &quot;visita&quot; en la visita en segundo plano conservan sus valores en las demás visitas individuales de esta visita.
* Todos los valores configurados en la visita en segundo plano se incluyen en la evaluación de la lógica de contenedor del segmento de nivel de visita.

En ambos casos, el recuento total de visitas sería 1.

Ejemplo 2: Si se produce una visita en segundo plano después de una serie de visitas en primer plano, el comportamiento es similar.

![](assets/nogoodexample2.jpg)

Si la visita en segundo plano se produce después del tiempo de espera configurado del grupo de informes virtuales, la visita en segundo plano no forma parte de una sesión (se describe en verde):

![](assets/nogoodexample2-1.jpg)

Del mismo modo, si el período de tiempo *t* era menor que el tiempo de espera configurado del grupo de informes virtuales, la visita en segundo plano se incluye en la visita formada por las visitas en primer plano anteriores:

![](assets/nogoodexample2-2.jpg)

Esto significa que:

* Cualquier eVar establecida con caducidad de &quot;visita&quot; en las visitas en primer plano anteriores persiste en sus valores en la visita en segundo plano de esta visita.
* Todos los valores configurados en la visita en segundo plano se incluyen en la evaluación de la lógica de contenedor del segmento de nivel de visita.

Como antes, el recuento total de visitas en ambos casos sería 1.

Ejemplo 3: En algunas circunstancias, una visita en segundo plano puede provocar que lo que eran dos visitas separadas se combinen en una sola. En el siguiente escenario, una visita en segundo plano va precedida y seguida de una serie de visitas en primer plano:

![](assets/nogoodexample3.jpg)

Si, en este ejemplo, *t1* y *t2* son ambos menores que el tiempo de espera de visita configurado para el grupo de informes virtuales, todas estas visitas se combinarían en una sola visita, incluso si *t1* y *t2* juntos son buenos que el tiempo de espera de visita:

![](assets/nogoodexample3-1.jpg)

Sin embargo, si *t1* y *t2* son buenos al tiempo de espera configurado para el grupo de informes virtuales, estas visitas se separarían en dos visitas distintas:

![](assets/nogoodexample3-2.jpg)

Del mismo modo (como en nuestros ejemplos anteriores), si *t1* es menor que el tiempo de espera y *t2* es menor que el tiempo de espera, la visita en segundo plano se incluiría en la primera visita:

![](assets/nogoodexample3-3.jpg)

Si *t1* es bueno al tiempo de espera y *t2* es menor que el tiempo de espera, la visita en segundo plano se incluirá en la segunda visita:

![](assets/nogoodexample3-4.jpg)

Ejemplo 4: En escenarios donde se produce una serie de visitas en segundo plano dentro del tiempo de espera de visita del grupo de informes virtuales, las visitas procedentes de una “visita en segundo plano” invisible no se incluyen en el recuento de visitas y no se puede acceder a ellas desde un contenedor de segmentación de visitas.

![](assets/nogoodexample4.jpg)

Aunque esto no se considere una visita, cualquier eVar establecida que tenga caducidad de visita persiste en su valor en las demás visitas en segundo plano de esta “visita en segundo plano”.

Ejemplo 5: En escenarios donde se producen varias visitas en segundo plano sucesivas, seguidas de una serie de visitas en primer plano, es posible (dependiendo del tiempo de espera configurado) que las visitas en segundo plano mantengan viva una visita más allá del tiempo de espera. Por ejemplo, si *t1* y *t2* juntos fueran buenos que el tiempo de espera de visita del grupo de informes virtuales pero individualmente fueran inferiores al tiempo de espera, la visita se extendería para incluir ambas visitas en segundo plano:

![](assets/nogoodexample5.jpg)

Del mismo modo, si se produce una serie de visitas en segundo plano antes de una serie de eventos en primer plano, se produce un comportamiento similar:

![](assets/nogoodexample5-1.jpg)

Las visitas en segundo plano se comportan de este modo para preservar cualquier efecto de atribución de eVars u otras variables establecidas durante las visitas en segundo plano. Esto permite que los eventos de conversión en primer plano posteriores se atribuyan a acciones realizadas mientras una aplicación estaba en segundo plano. También permite que un contenedor de segmentos de visita incluya visitas en segundo plano que resultaron en una sesión en primer plano posterior, lo que resulta útil para medir la eficacia de los mensajes push.

## Comportamiento de la métrica de visitas 

El recuento de visitas se basa únicamente en el número de visitas que incluyen al menos una visita en primer plano. Esto significa que las visitas en segundo plano huérfanas o las &quot;visitas en segundo plano&quot; no se contabilizan en la métrica Visita.

## Comportamiento de tiempo pasado por métrica de visitas 

El tiempo empleado se sigue calculando de forma análoga a cómo se hace sin visitas en segundo plano usando el tiempo entre visitas individuales. Aunque, si una visita incluye visitas en segundo plano (porque se produjeron lo suficientemente cerca de las visitas en primer plano), dichas visitas se incluyen en el cálculo del tiempo empleado por visita como si fueran visitas en primer plano.

## Configuración del procesamiento de visitas en segundo plano 

Como el procesamiento de visitas en segundo plano solo está disponible para grupos de informes virtuales que utilizan Procesamiento de intervalo de tiempo, Adobe Analytics admite dos modos de procesar las visitas en segundo plano para preservar el recuento de visitas en el grupo de informes base que no utiliza Procesamiento de intervalo de tiempo. Para acceder a esta configuración, vaya a la Consola de administración de Adobe Analytics, vaya a la configuración del grupo de informes base aplicable y, a continuación, vaya al menú &quot;Administración de móviles&quot; y, a continuación, al submenú &quot;Sistema de informes de aplicaciones móviles&quot;.

1. &quot;Procesamiento heredado activado&quot;: Esta es la configuración predeterminada para todos los grupos de informes. Si se deja el procesamiento heredado en, las visitas en segundo plano se procesan como visitas normales en la canalización de procesamiento en lo que se refiere al grupo de informes base de Atribución de tiempo no de informes. Esto significa que cualquier visita en segundo plano que aparezca en el grupo de informes base incrementa las visitas como una visita normal. Si no desea que las visitas en segundo plano aparezcan en el grupo de informes base, cambie esta configuración a &quot;Desactivado&quot;.
1. &quot;Procesamiento heredado desactivado&quot;: Con el procesamiento heredado de visitas en segundo plano desactivado, el grupo de informes base ignora las visitas en segundo plano enviadas al grupo de informes base y solo se puede acceder a ellas cuando un grupo de informes virtuales creado en este grupo de informes base está configurado para utilizar Procesamiento de intervalo de tiempo. Esto significa que los datos capturados por las visitas en segundo plano enviadas a este grupo de informes base solo aparecen en un grupo de informes virtuales habilitado para Procesamiento de intervalo de tiempo.

   Esta configuración está dirigida a los clientes que deseen aprovechar el nuevo procesamiento de visitas en segundo plano sin alterar el recuento de visitas de su grupo de informes base.

En cualquier caso, las visitas en segundo plano se facturan al mismo costo que cualquier otra visita enviada a Analytics.

## Inicio de nuevas visitas tras cada inicio de aplicación 

Además del procesamiento de visitas en segundo plano, los grupos de informes virtuales pueden forzar una nueva visita a inicio cada vez que el SDK móvil envía un evento de inicio de la aplicación. Con esta configuración habilitada, cada vez que se envía un evento de inicio de aplicación desde el SDK, se fuerza una nueva visita al inicio independientemente de si una visita abierta ha alcanzado su tiempo de espera. La visita que contiene el evento de inicio de la aplicación se incluye como la primera visita en la siguiente visita, incrementa el recuento de visitas y crea un contenedor de visitas distinto para la segmentación.
