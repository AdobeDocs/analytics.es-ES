---
description: Los grupos de informes virtuales se pueden utilizar para reemplazar el etiquetado de grupos múltiples. Por ejemplo, en lugar de enviar datos a dos grupos de informes separados, puede enviar datos a uno y utilizar los grupos de informes virtuales para limitar la cantidad de datos a la que tienen acceso los usuarios. Sin embargo, el acceso a los datos es solo una de las razones por las que puede ser beneficiosa la separación de los grupos de informes. Observe detenidamente los siguientes casos de uso antes de realizar cambios de implementación relacionados con los grupos de informes virtuales.
keywords: Grupo de informes virtuales
seo-description: Los grupos de informes virtuales se pueden utilizar para reemplazar el etiquetado de grupos múltiples. Por ejemplo, en lugar de enviar datos a dos grupos de informes separados, puede enviar datos a uno y utilizar los grupos de informes virtuales para limitar la cantidad de datos a la que tienen acceso los usuarios. Sin embargo, el acceso a los datos es solo una de las razones por las que puede ser beneficiosa la separación de los grupos de informes. Observe detenidamente los siguientes casos de uso antes de realizar cambios de implementación relacionados con los grupos de informes virtuales.
seo-title: Consideraciones de etiquetado de grupos múltiples y globales/múltiples grupos
solution: Analytics
title: Consideraciones de etiquetado de grupos múltiples y globales/múltiples grupos
topic: Reports and Analytics
uuid: f 17 d 3659-a 5 b 1-4807-a 01 d-a 1 b 422009 a 64
translation-type: tm+mt
source-git-commit: 800d4ed34a816bd331b339295dc3acd2a03a2cd5

---


# Consideraciones de etiquetado de grupos múltiples y globales/múltiples grupos

Los grupos de informes virtuales (VRS) le permiten ver datos de un grupo de informes que recopila datos de sus propiedades digitales, pero con un segmento aplicado de manera permanente.

Gracias a que los VRS funcionan como grupos de informes y se pueden asignar a grupos de usuarios del mismo modo que los grupos de informes, en algunos casos, pueden reemplazar el etiquetado de grupos múltiples, lo que elimina las [llamadas secundarias al servidor](/help/admin/c-server-call-usage/overage-overview.md). (El etiquetado de grupos múltiples se define como la capacidad para enviar datos a varios grupos de informes utilizando una única solicitud de imagen). Por ejemplo, en lugar de enviar datos de dos de sus marcas en dos grupos de informes “secundarios” separados, además de un grupo de informes “globales” en el que se agrupan datos de distintas marcas, puede enviar datos desde ambas marcas al grupo de informes globales. Entonces, utilizaría VRS para limitar el acceso de los usuarios a los datos (por marca) mediante la réplica de los grupos de informes secundarios.

La sustitución del etiquetado de grupos múltiples con un grupo de informes global y VRS permite simplificar la implementación de Adobe Analytics y reducir el consumo de llamadas al servidor. Además, se aconseja como práctica recomendada. Sin embargo, existen algunas limitaciones importantes de VRS que debe considerar al decidir si utilizar el etiquetado de grupos múltiples o un único grupo de informes globales y VRS. Las siguientes directrices le ayudarán a decidir si la implementación de grupos de informes virtuales creados en un grupo de informes global es la estrategia adecuada.

## Directrices

>[!NOTE]
>
> Las siguientes consideraciones SOLO se aplican a estos casos:
>
>* Está considerando cambiar su implementación para eliminar grupos de informes secundarios y confiar solamente en virtual &gt; grupos de informes para controlar las vistas de los datos de los usuarios finales o
>* Los usuarios de Adobe Analytics en su empresa dependerán únicamente de los grupos de informes virtuales como vista principal de datos.


Si no está seguro de si los casos de uso descritos se aplican a usted y a su organización, consulte con los otros administradores de Adobe Analytics o con el equipo de su cuenta de Adobe. Pueden ayudarle a evaluar las necesidades de la empresa y recomendarle la mejor solución.

Se recomienda utilizar grupos de informes virtuales para reemplazar el etiquetado de grupos múltiples si:

## Los segmentos de publicación de Adobe Analytics en el resto de Adobe Experience Cloud solo se necesitan en el nivel de grupos de informes globales y todos los usuarios que publican segmentos tienen acceso al grupo de informes globales.

Resumen:

* Con los grupos de informes virtuales no se pueden compartir segmentos con Adobe Experience Cloud.
* Los usuarios que necesiten compartir un segmento con Experience Cloud deberán disponer de acceso a un grupo de informes auténtico (principal o secundario).

Actualmente, los segmentos no se pueden publicar en Adobe Experience Cloud desde un grupo de informes virtual para su personalización y segmentación. Todos los usuarios que publiquen segmentos deben tener acceso a un grupo de informes auténtico para este fin. La estrategia de etiquetado de grupos múltiples crea grupos de informes secundarios a nivel de marca, propiedad, región, etc. que permite a los usuarios que no tengan acceso al grupo de informes global publicar segmentos frente al conjunto de datos disponibles para ellos en el grupo de informes secundario.

Por ejemplo, los usuarios solo tienen acceso a grupos de informes virtuales de su región geográfica, pero quiere que puedan crear y compartir segmentos de Adobe Analytics en Adobe Experience Cloud para realizar la segmentación en Adobe Target. En este caso, los usuarios no podrán publicar segmentos y usted debería considerar el uso del etiquetado de grupos múltiples para garantizar que los usuarios puedan publicar segmentos.

## Los informes a tiempo real (o “Datos actuales”) no son necesarios en el nivel del grupo de informes virtuales.

Resumen:

* Los informes a tiempo real no son compatibles con los grupos de informes virtuales porque los datos están segmentados.
* “Datos actuales” no es compatible con los grupos de informes virtuales, ya que no admite segmentación.

[Los informes en tiempo real](/help/admin/admin/realtime/t-realtime-admin.md) y [los "Datos actuales"](../../technotes/latency.md) no están disponibles en los grupos de informes virtuales. Estas funciones de Reports &amp; Analytics proporcionan acceso a ciertos tipos limitados de datos de manera acelerada, en cuestión de segundos o minutos. Una de las limitaciones de estas vistas es que no admiten segmentación; es decir, los datos a tiempo real en Reports &amp; Analytics no se pueden segmentar. Debido a que los grupos de informes virtuales se crean mediante la segmentación, no es compatible con los informes a tiempo real. Esto afecta a los usuarios que responden a las tendencias que tienen lugar en Adobe Analytics en cuestión de segundos o minutos desde la recopilación de datos, por ejemplo, los editores en una sala de prensa que adaptan montones de titulares basados en el consumo de contenido a tiempo real. En este caso, debe hacer una de las siguientes acciones:

* Considerar el uso de etiquetado de grupos múltiples para asegurar que todos los usuarios ven únicamente los datos en tiempo real que deben ver.
* Conceder a estos usuarios acceso a un grupo de informes auténtico (global) si se les debe permitir el acceso al conjunto de datos completo.

## No supera los límites de valor únicos para las dimensiones clave del grupo de informes globales, o no le importa si los usuarios ven “Tráfico bajo” en sus grupos de informes virtuales.

Resumen:

* Los grupos de informes virtuales no tienen límites de valor único propios para las dimensiones, sino que los heredan de su grupo de informes principal.
* Si los usuarios de Adobe Analytics necesitan acceder a todos los valores de una dimensión que recibe con frecuencia más de 500 000 valores únicos al mes, considere seguir con la etiqueta de grupos múltiples.

En casos de alta cardinalidad (grandes cantidades de valores únicos en una dimensión determinada, como SKU o páginas del producto), Adobe Analytics agrupa mensualmente aquellos valores que se encuentran en un elemento de línea “Tráfico bajo” agregado, dentro de cualquier dimensión en un grupo de informes. Los valores que se incluyen en el bloque “Tráfico bajo” no se pueden segmentar. Esto permite que las consultas de Adobe Analytics vuelvan rápidamente, al tiempo que se centran en los primeros 500 000 elementos de línea que se ven con más frecuencia para la dimensión en sus propiedades digitales (por ejemplo, podría ser sus primeros 500 000 nombres de página). Puede obtener más información sobre los límites de valores únicos [aquí](../../technotes/low-traffic.md).

Los grupos de informes virtuales no tienen su propio conjunto de 500 000 valores únicos por dimensión al mes. Si el grupo de informes basado en un VRS supera los 500 000 valores únicos de una dimensión determinada y comienza a combinar valores de baja frecuencia en el elemento de línea “Tráfico bajo” para esa dimensión, es posible que también aparezca “Tráfico bajo” en el grupo de informes virtual.

**Ejemplo**: un conglomerado multimedia posee 100 propiedades web. Además de alojar todos los artículos de los meses anteriores, todas las propiedades publican unos miles de artículos periodísticos mensualmente y se combinan en un grupo de informes globales. Supongamos que en el grupo de informes globales, en la dimensión “Nombre del artículo”, hay 4 millones de nombres de artículos únicos al mes desde la distintas propiedades. Los primeros 500 000 valores que comprenden la mayor parte del tráfico se muestran y se pueden segmentar, pero los 3,5 millones de valores restantes se agrupan en el elemento de línea “Tráfico bajo”.

En este caso, puede crear 100 grupos de informes virtuales para los equipos que trabajan en las propiedades individuales. Aunque esto es aceptable, tenga en cuenta que en la dimensión “Nombre del artículo” de cada grupo de informes virtuales, los valores que se muestran como elementos de línea diferentes son solo aquellos incluidos en los primeros 500 000 en el grupo de informes globales de dicha propiedad. Los grupos de informes virtuales no reciben su propia asignación de 500 000 valores únicos por dimensión. Los valores que se acumulen en el elemento “Tráfico bajo” del grupo de informes globales no se mostrarán de manera individual en el VRS. Esto puede causar confusión entre los usuarios que esperan ver un conjunto completo de valores de dimensión en un grupo de informes virtuales y, en cambio, solo ven los valores de tráfico alto.

Si es consciente de superar a menudo los límites de valores únicos en su grupo de informes globales o en los grupos de informes secundarios existentes, considere si los usuarios necesitan tener acceso a esos valores que no se ven con frecuencia antes de migrar a grupos de informes virtuales. Si los usuarios necesitan tener acceso a todos los valores únicos de una dimensión que superen los límites de valor únicos en su grupo de informes globales, considere seguir utilizando el etiquetado de grupos múltiples para proporcionar este acceso.

Además, tenga en cuenta que el servicio de atención al cliente de Adobe puede incrementar los límites de valor únicos para un grupo de informes globales de manera limitada para una pequeña cantidad de dimensiones, lo cual puede eliminar este problema por completo. Para obtener más información, consulte con su equipo de cuenta y con el servicio de atención al cliente.

## Puede utilizar el conjunto de dimensiones personalizadas (eVars y accesorios) y métricas (eventos) que tiene disponibles en el grupo de informes globales para rastrear todos los puntos de datos críticos en todas las propiedades.

Resumen:

* Los grupos de informes virtuales no tienen conjuntos de dimensiones y métricas propios, sino que los heredan de su grupo de informes principal.
* Por lo tanto, el grupo de informes principal debe poder capturar todas las dimensiones y métricas relevantes para todas las propiedades combinadas en él utilizando únicamente las dimensiones y métricas personalizadas disponibles para el grupo de informes globales (325 y 1000, respectivamente).

Una ventaja actual del etiquetado de grupos múltiples es que puede permitir que distintas propiedades, marcas, regiones, etc. capturen distintos tipos de datos. Por ejemplo, una unidad comercial podría utilizar eVar76 para capturar “Palabras clave de búsqueda interna”, mientras que otra unidad comercial podría utilizar esa misma eVar para capturar “Nombres de vídeo”. Los grupos tienen libertad para implementar Adobe Analytics según sus necesidades.

Con los grupos de informes globales, todas las propiedades deben pasar los mismos puntos de datos a la misma dimensión y métricas. En el ejemplo anterior, estas dos marcas tendrían que alinearse en eVar76 para utilizar tanto “Palabras clave de búsqueda internas” como “Nombres de vídeo” y, luego, ubicar el otro punto de datos en una dimensión diferente en sus respectivas implementaciones. No hacerlo supone dañar las dimensiones y las métricas del grupo de informes globales. Esto tiende a ser un problema en situaciones en las que varias propiedades, marcas, regiones, etc., que son compatibles (con los grupos de informes individuales), utilizan todo su contingente de dimensiones o métricas personalizadas disponibles. Por lo tanto, no podrían reservar algunas de sus dimensiones o métricas para las necesidades de seguimiento de otras propiedades, marcas, regiones, etc.

El número máximo de dimensiones personalizadas de Adobe Analytics por grupo de informes es 325, y el número máximo de eventos personalizados por grupos de informes es 1000. Para pasar a un grupo de informes globales es necesario que todos los puntos de datos críticos en todas las propiedades digitales se puedan rastrear utilizando las mismas 325 dimensiones personalizadas y los 1000 eventos personalizados.

Si se encuentra en esta situación y está considerando utilizar un grupo de informes globales con VRS, consulte las distintas implementaciones de Adobe Analytics en su empresa para evaluar la cantidad de superposición o disonancia en estas implementaciones y ver qué dimensiones o métricas no son indispensables para su éxito comercial. Considere también el uso de [clasificaciones](/help/components/c-classifications2/c-classifications.md) en su grupo global para informar sobre valores que actualmente puedan estar utilizando su propia dimensión. Las clasificaciones están disponibles automáticamente para cualquier VRS ubicado en dicho grupo global. Por ejemplo, en lugar de capturar el “Nombre de producto” en eVar5, cree una clasificación de “Nombre de producto” basada en la dimensión “Producto”.

Si la consolidación de estas dimensiones y eventos personalizados no es viable, Adobe recomienda seguir utilizando el etiquetado de grupos múltiples.

>[!IMPORTANT]
>
>With the introduction of [virtual report suite curation](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md), you can now change the name of a given dimension or &gt;metric on a per-VRS basis. Si segmenta el grupo de informes virtuales de forma limpia, significa que ahora puede utilizar la misma evar, prop o evento para capturar diferentes cosas en diferentes grupos de informes virtuales. Sin embargo, si se pasan dos &gt; distintos tipos de datos en la misma dimensión o métrica, ese punto de datos no se puede utilizar prácticamente en el grupo de informes globales. También podría producir problemas con la atribución, como en este ejemplo: Si un usuario recibe dos &gt; valores para evar 10, una que es una «Campaña interna» en la propiedad A y otra que es un'Nombre de página'en &gt; propiedad B, esto significa que el éxito ahora se divide en «Campaña interna» y en «Nombre de página», que debería &gt; operar en diferentes niveles. Por lo tanto, Adobe generalmente no recomienda utilizar la revisión VRS como solución &gt; para este problema en particular.

## Los segmentos que utiliza con los grupos de informes virtuales no dividen los datos de manera que puedan confundir a los usuarios.

Resumen:

* La segmentación de datos de un grupo de informes globales a grupos de informes virtuales puede crear resultados con matices que pueden confundir a algunos usuarios.
* Tenga en cuenta cómo los segmentos en los grupos de informes virtuales pueden afectar a las dimensiones y capacidades como la página de entrada, el dominio de referencia, las rutas, etc.

Recuerde que un grupo de informes virtuales solo es un segmento aplicado a un grupo de informes; todos los matices en los datos segmentados se ponen en práctica en los grupos de informes virtuales. Los segmentos (y, por tanto, los grupos de informes virtuales) pueden utilizarse para dividir datos de forma que a los usuarios de Adobe Analytics les parecerá poco intuitiva.

Por ejemplo, supongamos que tiene dos marcas, A y B, cuyas propiedades digitales envían datos a un grupo de informes globales. Algunos usuarios pasarán del sitio web A al sitio web B y viceversa, y este movimiento de un sitio a otro es visible en las rutas del grupo de informes global. Sin embargo, si crea grupos de informes virtuales para las marcas A y B, los usuarios que accedan al grupo de informes virtuales B pueden ver resultados no intuitivos para determinadas dimensiones y métricas. Una visita que comenzó en la marca A y finalizó en la marca B no mostrará ninguna página de entrada en el grupo de informes virtuales B, ya que la página de entrada de la visita de sitios cruzados empezó en la marca A, la cual se segmenta fuera de este grupo de informes virtuales.

Un ejemplo similar sucede con el “Número de visitas”. En el grupo de informes virtuales para la marca B, los usuarios pueden ver algunos visitantes que parecen tener una segunda, tercera y cuarta visita, pero no una primera. Esto sucede cuando la primera visita del cliente es a la marca A y todas las visitas subsiguientes son a la marca B. Dado que los datos de la marca A no se incluyen en el grupo de informes virtuales, toda la información sobre la primera visita (incluido el hecho de que se produjo) no se incluye en este grupo de informes virtuales.

Adobe recomienda el uso del etiquetado de grupos múltiples en estos escenarios o en otras situaciones en las que parte del recorrido del cliente puede producirse fuera de un grupo de informes virtuales de forma que pueda confundir a los usuarios. El etiquetado de grupos múltiples le permite hacer el seguimiento de un recorrido a nivel de propiedad cruzada en un grupo de informes globales, pero también le ofrece a equipos individuales su propia vista completa del recorrido a nivel de propiedad individual.

## No es necesario que usted y los usuarios vean transacciones en distintas divisas.

Resumen:

* Actualmente, los grupos de informes virtuales no pueden crear informes en una moneda distinta a la del grupo de informes en el que están basados.
* Adobe Analytics le permite convertir divisas cuando se ejecutan informes, pero la tasa de cambio se basa en el día actual incluso para los datos históricos.

Actualmente, los grupos de informes virtuales no pueden crear informes en una moneda distinta a la del grupo de informes en el que están basados. Si su empresa y sus usuarios de Adobe Analytics realizan los análisis en una sola moneda, no le causará ningún problema. Sin embargo, si tiene una necesidad comercial importante para diferentes equipos regionales que necesitan poder ver los ingresos y métricas similares en su propia moneda local (que se convierte según la tasa de cambio en el momento de la recopilación de datos), debe utilizar el etiquetado de grupos múltiples.

Esto le permite enviar datos a Adobe Analytics en diferentes divisas al mismo tiempo. Con el etiquetado de grupos múltiples, una transacción llevada a cabo en la versión japonesa de su aplicación se puede registrar en dólares estadounidenses en el grupo global. Se puede convertir de yenes al tipo de cambio de un día en concreto, pero seguirá apareciendo en el grupo de informes de Japón en yenes.

>[!NOTE]
>
>Aunque los grupos de informes virtuales no permiten convertir los datos de ingresos en otra moneda a una tasa histórica, puede seguir convirtiendo moneda en un grupo de informes virtuales específico. Puede aplicar el día actual &gt; tasa de cambio a datos históricos si ingresa a Componentes &gt; Configuración de informes.

## Puede utilizar un único archivo de Fuente de datos para recibir todos los datos de un grupo de informes global.

Resumen:

* Las Fuentes de datos solo se pueden crear tomando como modelo grupos de informes principales, no grupos de informes virtuales.
* Sin embargo, puede recibir una Fuente de datos de un grupo de informes globales y, luego, dividirla en marca, propiedad, región, etc.

Las Fuentes de datos le permiten recibir una exportación diaria o por hora de todos sus datos de Adobe Analytics a nivel de “evento” o “visita”. Debido a que las Fuentes de datos no se pueden segmentar previamente antes del envío, usar un grupo de informes globales con grupos de informes virtuales significa que solo puede recibir una Fuente de datos para su grupo de informes globales. No puede establecer Fuentes de datos para grupos de informes virtuales.

Sin embargo, puede configurar tantas Fuentes de datos basadas en grupos de informes principales como desee. Después de recibir estas Fuentes de datos, puede segmentarlas y dividirlas en cualquier configuración útil. Por ejemplo, después de recibir una fuente de datos para un grupo de informes globales, podría cargar la sección de dicha fuente de datos perteneciente a su sitio web en un almacén de datos. De forma simultánea, podría cargar la sección que pertenece a su aplicación móvil en un almacén de datos diferente.

Sin embargo, tenga en cuenta que es posible que algunos campos previamente calculados en la fuente de datos tengan que volver a calcularse tras la recepción. Consulte el elemento 5 (arriba) para ver ejemplos de campos que pueden requerir que se vuelvan a calcular al filtrar una fuente de datos basada en ciertos criterios.

Si su organización necesita las fuentes de datos individuales a nivel de marca, propiedad, región, etc., le recomendamos utilizar el etiquetado de grupos múltiples.

## No utiliza una integración de Exchange (conectores de datos) que permite solo una cuenta de socio por grupo de informes y no tiene varias cuentas de socios que quiera integrar.

Resumen:

* Ciertas integraciones de socios de Adobe en Adobe Analytics están limitadas a una cuenta de socio por grupo de informes.
* Es posible que algunas organizaciones deseen utilizar varias cuentas de socio en Adobe Analytics, lo que requiere el etiquetado de grupos múltiples.

Adobe Exchange le permite integrar otras soluciones de marketing y de tecnología publicitaria en Adobe Analytics. Algunos ejemplos de integraciones disponibles son: publicidad gráfica, correo electrónico, VOC y centro de llamadas. Debido a la variación en la forma en que los datos se recopilan, presentan e integran, algunos socios de Adobe que decida utilizar con Adobe Exchange están limitados a una instancia de integración por grupo de informes. Cada instancia se asigna a una cuenta con el socio.

Un ejemplo de esto es Google DCM. Muchas empresas cuentan con varias cuentas DCM, lo que permite que distintas marcas, unidades comerciales, regiones, etc. administren sus anuncios de visualización de forma independiente. Sin embargo, al integrar DCM en Adobe Analytics, solo puede utilizar una cuenta DCM por grupo de informes. No puede integrar todas sus cuentas DCM en el mismo grupo de informes. Tampoco puede configurar una integración directamente en un grupo de informes virtuales.

Como resultado, el etiquetado de grupos múltiples es la estrategia preferida si distintos equipos de su organización necesitan tener sus propios datos de cuenta individuales en Adobe Analytics para un socio de Adobe Exchange. Si utiliza (o va a utilizar) las integraciones de Adobe Exchange en las que varios grupos administran cuentas diferentes, póngase en contacto con el socio de Adobe para saber si se permiten varias cuentas por grupo de informes.

>[!NOTE]
>
>El término «cuenta» puede significar cosas diferentes para distintos proveedores. En el contexto de la tecnología de mercadotecnia, normalmente no hace referencia a una cuenta de usuario individual, sino a un conjunto de servicios disponibles para un &gt; equipo o organización completo. Por lo tanto, si bien puede tener varios nombres de usuario iniciando sesión en un servicio de socios de Adobe, todos estos nombres de usuario pueden pertenecer a la misma cuenta.

>[!NOTE]
>
>Las métricas «pre-clic» (resumidas/agregadas) que se importan desde un socio de Adobe Exchange no están &gt; disponibles para la segmentación y, por lo tanto, pueden no verse en un grupo de informes virtuales. Algunos ejemplos de estas métricas son: correo electrónico enviado o visualización de impresiones de publicidad; ambos ocurren fuera de la aplicación o fuera de la aplicación y se importan a Adobe &gt; Analytics en un formulario agregado.

## No confía demasiado en las Fuentes de datos de resumen a nivel de propiedad, marca, región, etc. nivel.

Resumen:

* Las “Fuentes de datos de resumen” le permiten importar métricas agregadas a nivel de grupo de informes a Adobe Analytics.
* Cambiar a un grupo de informes globales con grupos de informes virtuales requiere que todas las cargas de “Fuentes de datos de resumen” tengan lugar en el grupo de informes globales.

Las “Fuentes de datos de resumen” le permiten importar métricas previamente agregadas a un grupo de informes principal en Adobe Analytics. Algunos ejemplos de las fuentes de datos de resumen incluyen métricas como “Ingresos sin conexión” o “Vistas de páginas” que se produjeron en otra solución anterior a la implementación de Adobe Analytics. Debido a que las cargas de Fuentes de datos de resumen contienen métricas agregadas, no se pueden segmentar. Por lo tanto, no aparecen segmentadas en los grupos de informes virtuales.

El etiquetado de grupos múltiples permite a su organización importar métricas agregadas a nivel de grupo de informes individuales. Si la marca A desea importar ingresos sin conexión, puede hacerlo por separado de la marca B, y estos datos aparecerán en el grupo de informes de la marca A. La marca B puede hacer lo mismo. Si su organización utiliza o planea utilizar Fuentes de datos de resumen a nivel de propiedad, marca, región, etc., le recomendamos utilizar el etiquetado de grupos múltiples en lugar de los grupos de informes virtuales.

## Pasos a seguir si ha decidido utilizar VRS

Tras haber leído todas las consideraciones anteriores, si ha decidido eliminar las llamadas del servidor secundario y en su lugar usar los grupos de informes virtuales, tendrá que hacer lo siguiente:

**Primero**, cree grupos de informes virtuales para que coincidan con los datos de los grupos de informes secundarios. Segmente en una dimensión personalizada, como “marca”, “plataforma” o “dominio”. Elija una dimensión que facilite distinguir una propiedad digital de otra, y aplique estos segmentos a VRS.

* Si va a migrar desde una implementación de etiquetado de grupos múltiples de Adobe Analytics, recuerde comparar los segmentos de los grupos de informes virtuales con los grupos de informes secundarios existentes antes de migrar los usuarios. Asegúrese de que los segmentos que está utilizando en los grupos de informes virtuales son correctos.

* Si es necesario, ajuste los segmentos en los que se basan los grupos de informes virtuales.

* Como práctica recomendada, utilice [apilar segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md) cuando sea posible para poder editar un segmento en una ubicación y aplicarlo a todos los grupos de informes virtuales que usen dicho segmento. Por ejemplo, si desea crear un VRS para “usuarios móviles de Europa” y otro para “usuarios móviles de Asia”, cree un segmento para usuarios móviles y después separe los segmentos para usuarios de Europa y de Asia. De esta forma, si desea actualizar la definición de su segmento “usuarios móviles”, podrá hacerlo en un solo segmento, sin necesidad de actualizar cada segmento de grupo de informes virtuales por individual.

* Es posible que busque conjuntos de datos mutuamente exclusivos en los grupos de informes virtuales. Por ejemplo, puede que desee ver “Dominio A” y “Dominio B” como grupos de informes separados, y que no quiera ver el tráfico del Dominio A en el grupo de informes del Dominio B. En este caso, utilice un contenedor “visita” para sus segmentos.

**Segundo**, después de confirmar que los grupos de informes virtuales que ha creado están correctamente configurados y que servirán a las necesidades de su equipo, elimine las ID secundarias del grupo de informes de su implementación.

Para eliminar los grupos de informes secundarios:

* En Launch Platform Platform, pulse la «x» junto a cualquier grupo de informes que ya no desee utilizar.
* En DTM, ubique la propiedad y la herramienta de Adobe Analytics en cuestión. En los campos ID de cuenta de producción e ID de cuenta provisional, elimine los ID de los grupos de informes que ya no desee utilizar.
* In legacy JavaScript implementations, locate the `s.account` variable and remove any report suites that you no longer wish to use.

Deje solo los ID del grupo de informes global/superior para recopilar datos de sus sitios y aplicaciones. En la interfaz de Adobe Analytics, en Administrador &gt; Configuración de la empresa, puede ocultar grupos de informes heredados a los usuarios.

Si no puede editar su implementación usted mismo, hágalo con el equipo de su cuenta de Adobe. Ellos podrán explorar las opciones posibles para evitar que Adobe Analytics procese llamadas del servidor secundario.