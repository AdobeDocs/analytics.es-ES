---
description: Las sesiones según el contexto en los grupos de informes virtuales cambian el modo en que Adobe Analytics calcula las visitas con dispositivos móviles. En este artículo se describen las implicaciones de procesamiento que los hits y eventos de inicio de aplicaciones en segundo plano (todos ellos establecidos por el SDK para móviles) tienen para el modo en que se definen las visitas con dispositivos móviles.
title: Sesiones según el contexto
feature: VRS
exl-id: 5e969256-3389-434e-a989-ebfb126858ef
TQID: 'https://experienceleague.adobe.com/CRYnjIKXNZuu9P-oFB62zrvjRa6TFc1H2-etp8E8ntw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '1600'
ht-degree: 94%
---
# Sesiones según el contexto

Las sesiones según el contexto en los grupos de informes virtuales cambian el modo en que Adobe Analytics calcula las visitas de cualquier dispositivo. En este artículo también se describen las implicaciones de procesamiento que los hits y eventos de inicio de aplicaciones en segundo plano (todos ellos establecidos por el SDK para móviles) tienen para el modo en que se definen las visitas con dispositivos móviles.

Puede definir una visita del modo que desee sin alterar los datos subyacentes para adaptarse al modo en que sus visitantes interactúan con las experiencias digitales.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Sesiones según el contexto](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/virtual-report-suites/context-aware-sessions-in-virtual-report-suites){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Parámetro URL de perspectiva de cliente

El proceso de recopilación de datos de Adobe Analytics le permite establecer un parámetro de cadena de consulta que especifica la perspectiva del cliente (indicada como parámetro de cadena de consulta “cp”). Este campo especifica el estado de la aplicación digital del usuario final. Esto le ayuda a saber si se generó un hit mientras una aplicación móvil estaba en segundo plano.

## Procesamiento de hits en segundo plano

Un hit en segundo plano es un tipo de hit que el SDK para móviles de Adobe versión 4.13.6 o superior envía a Analytics cuando la aplicación realiza una solicitud de seguimiento estando en segundo plano. Algunos ejemplos habituales son:

* Datos enviados durante el cruce de un límite geográfico
* Interacción con una notificación push

Los siguientes ejemplos describen la lógica empleada para determinar cuándo comienza y acaba una visita para cualquier visitante cuando el ajuste “Impedir que los hits en segundo plano inicien una nueva visita” está o no habilitado para un grupo de informes virtuales.

**Si “Impedir que los hits en segundo plano inicien una nueva visita” no está habilitado:**

Si esta función no está habilitada para un grupo de informes virtuales, los hits en segundo plano se tratan como cualquier otro hit, lo que significa que inician nuevas visitas y se comportan igual que los hits en primer plano. Por ejemplo, si se produce un hit en segundo plano menos de 30 minutos (el tiempo de espera de sesión estándar para un grupo de informes) antes de un grupo de hits en primer plano, el hit en segundo plano es parte de la sesión.

![](assets/nogood1.jpg)

Si el hit en segundo plano se produce más de 30 minutos antes de cualquier hit en primer plano, el hit en segundo plano crea su propia visita y el número de estas sería de dos.

![](assets/nogood2.jpg)

**Si “Impedir que los hits en segundo plano inicien una nueva visita” está habilitado:**

Los siguientes ejemplos ilustran el comportamiento de los hits en segundo plano cuando esta función está habilitada.

Ejemplo 1: Se produce un hit en segundo plano un tiempo (t) antes de una serie de hits en primer plano.

![](assets/nogoodexample1.jpg)

En este ejemplo, si *t* es mayor que el tiempo de espera de visita configurado del grupo de informes virtuales, el hit en segundo plano se excluye de la visita formada por los hits en primer plano. Por ejemplo, si el tiempo de espera de visita del grupo de informes virtuales se estableció en 15 minutos y *t* fue 20 minutos, la visita formada por esta serie de hits (indicadas por el contorno verde) excluiría el hit en segundo plano. Esto significa que cualquier eVar establecida con una caducidad de “visita” en la visita en segundo plano **no** persistiría en la siguiente visita, y que un contenedor de segmentos de visita solo incluiría las visitas en primer plano dentro del contorno verde.

![](assets/nogoodexample1-2.jpg)

Por el contrario, si *t* es menor que el tiempo de espera de visita configurado del grupo de informes virtuales, el hit en segundo plano se incluye como parte de la visita, como si fuera un hit en primer plano (como se indica con el contorno verde):

![](assets/nogoodexample1-3.jpg)

Esto significa que:

* Cualquier eVar establecida con una caducidad de “visita” en la visita en segundo plano persiste en su valor en las demás visitas de esta visita.
* Cualquier valor establecido en el hit en segundo plano se incluye en la evaluación de la lógica del contenedor de segmentos en el nivel de visita.

En ambos casos, el recuento total de visitas sería de 1.

Ejemplo 2: Si se produce un hit en segundo plano después de una serie de hits en primer plano, el comportamiento es similar.

![](assets/nogoodexample2.jpg)

Si el hit en segundo plano se produce pasado el tiempo de espera configurado para el grupo de informes virtuales, el hit en segundo plano no es parte de una sesión (el contorno verde):

![](assets/nogoodexample2-1.jpg)

Igualmente, si el periodo de tiempo *t* fue inferior al tiempo de espera configurado del grupo de informes virtuales, el hit en segundo plano se incluye en la visita formada por los hits en primer plano anteriores:

![](assets/nogoodexample2-2.jpg)

Esto significa que:

* Cualquier eVar establecida con una caducidad de “visita” en las visitas en primer plano anteriores persiste en su valor en la visita en segundo plano de esta visita.
* Cualquier valor establecido en el hit en segundo plano se incluye en la evaluación de la lógica del contenedor de segmentos en el nivel de visita.

Como antes, el total de visitas en ambos casos sería de 1.

Ejemplo 3: En algunas circunstancias, un hit en segundo plano puede provocar que lo que eran dos visitas separadas se combinen en una sola. En el siguiente escenario, un hit en segundo plano es precedido y seguido por una serie de hits en primer plano:

![](assets/nogoodexample3.jpg)

Si, en este ejemplo, *t1* y *t2* son inferiores al tiempo de espera de visita configurado para el grupo de informes virtuales, todas estas visitas se combinarían en una sola, aunque la suma de *t1* y *t2* exceda el tiempo de espera de visita:

![](assets/nogoodexample3-1.jpg)

Sin embargo, si *t1* y *t2* son mayores que el tiempo de espera configurado, los hits se separarían en dos visitas distintas:

![](assets/nogoodexample3-2.jpg)

Del mismo modo (como en nuestros ejemplos anteriores), si *t1* es menor que el tiempo de espera y *t2* es mayor que este, la visita en segundo plano se incluiría en la primera visita:

![](assets/nogoodexample3-3.jpg)

Si *t1* es mayor y *t2* es menor que el tiempo de espera, el hit en segundo plano se incluiría en la segunda visita:

![](assets/nogoodexample3-4.jpg)

Ejemplo 4: En escenarios donde se produce una serie de hits en segundo plano dentro del tiempo de espera de visita del grupo de informes virtuales, los hits procedentes de una “visita en segundo plano” invisible no se incluyen en el recuento de visitas y no se puede acceder a ellos desde un contenedor de segmentación de visitas.

![](assets/nogoodexample4.jpg)

Aunque esto no se considere una visita, cualquier eVar establecida que tenga caducidad de visita persiste en su valor en las demás visitas en segundo plano de esta “visita en segundo plano”.

Ejemplo 5: En escenarios donde se producen varios hits en segundo plano sucesivos, seguidos de una serie de hits en primer plano, es posible (dependiendo del tiempo de espera configurado) que los hits en segundo plano mantengan viva una visita más allá del tiempo de espera. Por ejemplo, si la combinación de *t1* y *t2* fuera mayor que el tiempo de espera de visita del grupo de informes virtuales, pero individualmente fueran menores que dicho tiempo de espera, la visita se extendería para incluir ambos hits en segundo plano:

![](assets/nogoodexample5.jpg)

Igualmente, si se produce una serie de hits en segundo plano antes de una serie de eventos en primer plano, se obtiene un comportamiento similar:

![](assets/nogoodexample5-1.jpg)

Los hits en segundo plano se comportan de este modo para preservar cualquier efecto de atribución de eVars u otras variables establecidas durante los hits en segundo plano. Esto permite que los eventos de conversión en primer plano posteriores se atribuyan a acciones realizadas cuando una aplicación estaba en segundo plano. También permite a un contenedor de segmentos de visita incluir los hits en segundo plano que dieron como resultado una sesión en primer plano posterior, lo que resulta útil para medir la efectividad de los mensajes push.

## Comportamiento de la métrica de visitas

El recuento de visitas se basa únicamente en las visitas que incluyen al menos un hit en primer plano. Esto significa que los hits en segundo plano huérfanos o &quot;visitas en segundo plano&quot; no se cuentan en la métrica.

## Comportamiento de tiempo pasado por métrica de visitas

El tiempo pasado se sigue calculando de un modo análogo a como se hace sin hits en segundo plano, empleando el tiempo entre hits. No obstante, si una visita incluye hits en segundo plano (al producirse lo bastante próximos a hits en primer plano), dichos hits se incluyen en el cálculo del tiempo pasado por visita, como si fueran hits en primer plano.

## Configuración del procesamiento de hits en segundo plano

Como el procesamiento de hits en segundo plano solo está disponible para grupos de informes virtuales que utilizan Procesamiento de intervalo de tiempo, Adobe Analytics admite dos modos de procesar los hits en segundo plano para preservar el recuento de visitas en el grupo de informes base que no utiliza Procesamiento de intervalo de tiempo. Para acceder a esta configuración, vaya a las Herramientas de administración de Adobe Analytics, la configuración del grupo de informes base aplicable y, a continuación, vaya al menú &quot;Administración de móviles&quot; y al submenú &quot;Informes de aplicaciones móviles&quot;.

1. “Procesamiento heredado activado”: esta es la configuración predeterminada para todos los grupos de informes. Si se deja activado el procesamiento heredado, los hits en segundo plano se procesan como hits normales en nuestro canal de procesamiento por lo que respecta al grupo de informes base de atribución de tiempo no de informes. Esto significa que cualquier hit en segundo plano que aparezca en el grupo de informes base aumente las visitas como un hit normal. Si no desea que los hits en segundo plano aparezcan en el grupo de informes base, cambie este ajuste a “Desactivado”.
1. “Procesamiento heredado desactivado”: cuando el procesamiento heredado de hits en segundo plano está desactivado, el grupo de informes base ignora los hits en segundo plano, a las que solo se puede acceder si se configura el uso de Procesamiento de intervalo de tiempo en un grupo de informes virtuales creado en este grupo de informes base. Esto significa que cualquier dato captado por los hits en segundo plano y enviado a este grupo de informes base solo aparece en los grupos de informes virtuales que tengan habilitado Procesamiento de intervalo de tiempo.

   Este ajuste está pensado para los clientes que desean aprovechar el nuevo procesamiento de hits en segundo plano sin alterar el recuento de visitas en su grupo de informes base.

En cualquier caso, los hits en segundo plano se facturan al mismo coste que cualquier otro enviado a Analytics.

## Inicio de nuevas visitas tras cada inicio de aplicación

Además del procesamiento de hits en segundo plano, los grupos de informes virtuales pueden forzar que se inicie una nueva visita cada vez que el SDK para móviles envíe un evento de inicio de aplicación. Cuando este ajuste está habilitado, cada vez que el SDK envía un evento de inicio de aplicación, se fuerza el inicio de una nueva visita, haya alcanzado o no cualquier visita actual su tiempo de espera. El hit que contiene el evento de inicio de aplicación se incluye como primer elemento de la nueva visita, incrementa el recuento de visitas y crea un contenedor de visitas propio para la segmentación.
