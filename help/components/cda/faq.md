---
title: Preguntas más frecuentes sobre análisis entre dispositivos
description: Preguntas más frecuentes sobre el análisis entre dispositivos
translation-type: tm+mt
source-git-commit: 087ea279f55d4828d68b1ec16a5505855b34055d
workflow-type: tm+mt
source-wordcount: '1377'
ht-degree: 91%

---


# Preguntas frecuentes

## ¿Cómo puedo usar CDA para ver cómo la gente se mueve de un tipo de dispositivo a otro?

Puede utilizar una visualización de flujo con la dimensión Tipo de dispositivo móvil.

1. Inicie sesión en Adobe Analytics y cree un nuevo proyecto de Workspace en blanco.
2. Haga clic en la pestaña Visualizaciones de la izquierda y arrastre una visualización de Flujo al lienzo de la derecha.
3. Haga clic en la pestaña Componentes de la izquierda y arrastre la dimensión &#39;Tipo de dispositivo móvil&#39; a la ubicación central denominada &#39;Dimensión o elemento&#39;.
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos a páginas posteriores o anteriores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

## ¿Puedo ver cómo se mueven las personas entre distintas experiencias de usuario (p. ej., navegador de escritorio vs. navegador móvil vs. aplicación móvil)?

El uso del tipo de dispositivo móvil, como se ilustra más arriba, permite ver cómo se mueven las personas entre los tipos de dispositivos móviles y los tipos de dispositivos de escritorio. Sin embargo, es posible que desee distinguir los navegadores de escritorio de los navegadores móviles. Una manera de hacerlo es crear una eVar que registre si la experiencia se produjo en un navegador de escritorio, un navegador móvil o una aplicación móvil. A continuación, cree un diagrama de flujo como se ha descrito anteriormente, utilizando la eVar de “experiencia” en lugar de la dimensión Tipo de dispositivo móvil. Esto proporciona una vista ligeramente diferente del comportamiento entre dispositivos.

## ¿Hasta dónde llega la CDA a los visitantes?

La vinculación entre dispositivos de CDA se produce en dos procesos simultáneos.

* El primer proceso se denomina &quot;vinculación activa&quot;, que se produce cuando los datos se transfieren a Adobe Analytics. Durante la vinculación activa, CDA hace lo mejor que puede para reafirmar los datos a nivel de persona. Sin embargo, si la persona es desconocida en el momento de la vinculación activa, CDA vuelve al ID de visitante para representar a la persona.

* El segundo proceso se llama &quot;repetición&quot;. Durante la reproducción, CDA retrocede en el tiempo y repite los datos históricos, cuando es posible, dentro de una ventana retrospectiva especificada. Esta ventana retrospectiva es de 1 día o 7 días, según la configuración del CDA que haya solicitado. Durante la reproducción, CDA intenta repetir las visitas en las que la persona era anteriormente desconocida.

* **Si se utiliza un gráfico del dispositivo**, Adobe mantiene las asignaciones de dispositivos en el gráfico de cooperación y el gráfico privado durante aproximadamente 6 meses. Un ECID que no tenga actividad durante más de seis meses se elimina del gráfico. Los datos ya enlazados en CDA no se ven afectados, pero las visitas posteriores para ese ECID se tratan como una persona nueva.

## ¿Cómo gestiona CDA las visitas con marca de hora?

Adobe trata las visitas con marca de hora como si se hubieran recibido en el momento de la marca de hora, no cuando Adobe recibió la visita. Las visitas con marca de tiempo anteriores a 1 mes nunca se vinculan, ya que están fuera del rango que utiliza Adobe para la vinculación.

## ¿En qué se diferencia CDA del ID de visitante personalizado?

Utilizar el ID de visitante personalizado es un método heredado para [conectar usuarios entre dispositivos](/help/implement/js/xdevice-visid/xdevice-connecting.md). Con una ID de visitante personalizada, se utiliza la [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variable para establecer explícitamente la ID que se utiliza para la lógica del visitante. La `visitorID` variable anula los ID basados en cookies que estén presentes.

Los ID de visitante personalizadas tienen varios efectos secundarios no deseados que la CDA supera o minimiza. Por ejemplo, la metodología de ID de visitante personalizada no tiene capacidades de [repetición](replay.md). Si un usuario se autentica en mitad de una visita, la primera parte de la visita se asocia con un ID de visitante diferente al de la última parte de la visita. Los ID de visitante independientes producen inflación de visitas y visitantes. CDA repite los datos históricos de modo que las visitas no autenticadas pertenecen a la persona correcta.

## ¿Puedo actualizar de ID de visitante personalizado a CDA?

Los clientes que ya utilizan el ID de visitante personalizado pueden actualizar a CDA sin ningún cambio de implementación. La variable `visitorID` sigue utilizándose en el grupo de informes de origen. Sin embargo, CDA ignora la variable `visitorID` en el grupo de informes virtuales si un usuario se autentica.

## ¿Cómo gestiona el gráfico del dispositivo los dispositivos compartidos?

En algunas situaciones es posible que varias personas inicien sesión desde el mismo dispositivo. Algunos ejemplos son un dispositivo compartido en casa, un equipo compartido en una biblioteca o un quiosco en un punto de venta minorista.

* **Si se utiliza un gráfico del dispositivo**, la capacidad de gestionar dispositivos compartidos es limitada. El gráfico del dispositivo utiliza un algoritmo para determinar la propiedad de un “clúster” y puede cambiar cada vez que se publica este clúster. Los usuarios del dispositivo compartido están sujetos al clúster al cual pertenecen.
* **Si utiliza la vinculación basada en el campo**, la propiedad o el eVar que elija para ayudar a identificar a los usuarios que iniciaron sesión sobrescribirá otros identificadores. Los dispositivos compartidos se consideran personas independientes, incluso si se originan en el mismo dispositivo.

## ¿Cómo gestiona el CDA las situaciones en las que una sola persona tiene MUCHOS dispositivos/ECID?

En algunas situaciones, un usuario individual puede asociarse con un gran número de ECID. Esto puede ocurrir si el usuario utiliza muchos navegadores o aplicaciones, y puede exacerbarse si borra las cookies con frecuencia o utiliza el modo de exploración privado o indirecto del explorador.

* **Si se utiliza un gráfico del dispositivo**, CDA limita el número de ECID que se asocia a un ID de usuario determinado a 50. Si un ID de usuario se asocia con demasiados ECID, el gráfico del dispositivo supone que el ID de usuario no es válido y elimina el clúster asociado a dicho ID de usuario. A continuación, se agrega el ID de usuario a una lista de bloqueados para evitar que se añada a otro clúster en el futuro. El resultado en los informes es que el ID de usuario no se vincula entre dispositivos.
* **Si utiliza la vinculación basada en el campo**, el número de dispositivos es irrelevante en favor de la propiedad o el eVar que elija para ayudar a identificar a los usuarios que iniciaron sesión. Un solo usuario puede pertenecer a cualquier número de dispositivos sin afectar a la capacidad de CDA para vincular entre los dispositivos.

## ¿Cuál es la diferencia entre la métrica Personas en CDA y la métrica Visitantes únicos fuera de CDA?

La métrica [Personas](/help/components/metrics/people.md) es similar a la métrica [Visitantes únicos](/help/components/metrics/unique-visitors.md) en el sentido de que informa sobre la cantidad de individuos únicos. Sin embargo, cuando se utiliza el análisis entre dispositivos, se combinan visitantes únicos cuando, de lo contrario, se registran como dos visitantes únicos independientes fuera de CDA. La métrica &#39;Personas&#39; reemplaza la métrica &#39;Visitantes únicos&#39; cuando Analytics entre dispositivos está habilitado. Hay disponible una nueva métrica, [Dispositivos únicos](/help/components/metrics/unique-devices.md), que es aproximadamente igual a Visitantes únicos fuera de Analytics entre dispositivos.

## ¿Cuál es la diferencia entre la métrica &#39;Dispositivos únicos&#39; en CDA y la métrica &#39;Visitantes únicos fuera de CDA?

Estas dos métricas son aproximadamente equivalentes entre sí.

## ¿Puedo incluir métricas de CDA usando la API 2.0?

Sí. Analysis Workspace utiliza la API 2.0 para solicitar datos de los servidores de Adobe, y puede realizar llamadas a la API de vista que Adobe utiliza para crear sus propios informes:

1. Con una sesión iniciada en Analysis Workspace, vaya a [!UICONTROL Ayuda] > [!UICONTROL Habilitar depurador].
2. Haga clic en el icono de depuración en el panel deseado y, a continuación, seleccione la visualización y la hora deseadas de la solicitud.
3. Busque la solicitud JSON, que puede utilizar en su llamada de API a Adobe.

## Los análisis entre dispositivos pueden unir visitantes únicos. ¿Puede unir visitas?

Sí. Si un individuo envía visitas desde dos dispositivos distintos dentro del tiempo de espera de visita del grupo de informes virtuales (30 minutos de forma predeterminada), se vinculan a la misma visita.

## ¿Cuál es el ID de visitante definitivo que utiliza CDA? ¿Puedo exportarlo desde Adobe Analytics?

* **Si se utiliza un gráfico del dispositivo**, el identificador principal es un ID personalizado basado en su clúster.
* **Si se utiliza la vinculación basada en el campo**, el identificador principal es un ID personalizado basado en la propiedad o el eVar que se elija.

Adobe calcula ambos identificadores en el momento de ejecutar el informe, también conocido como [procesamiento de tiempo de los informes](../vrs/vrs-report-time-processing.md). La naturaleza del procesamiento de tiempo de los informes significa que no es compatible con el Data Warehouse, las fuentes de datos u otras funciones de exportación de ofertas de Adobe.

## ¿Cómo puedo pasar del gráfico del dispositivo a la vinculación basada en el campo o viceversa?

Si desea cambiar los métodos de identificación de CDA, póngase en contacto con el administrador de cuentas de su organización. El administrador de cuentas puede aprovisionar al grupo de informes según el método que desee para identificar a las personas. *Se pierden los datos históricos vinculados del método anterior.*

## ¿Cómo gestiona Adobe los límites únicos para un eVar utilizado en la vinculación basada en el campo?

CDA extrae los elementos de dimensión de eVar antes de optimizarlos para la creación de informes. No es necesario preocuparse por los límites únicos para el propósito de CDA. Sin embargo, si ha intentado utilizar esa propiedad o eVar en un proyecto de Workspace, todavía puede ver el elemento de dimensión [(poco tráfico)](/help/technotes/low-traffic.md).
