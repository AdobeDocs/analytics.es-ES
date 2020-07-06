---
description: Descubra las prácticas recomendadas y vea ejemplos de cómo completar las diversas reglas que puede configurar para sus canales de marketing.
title: Preguntas más frecuentes sobre los Canales de mercadotecnia
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 88%

---


# Preguntas más frecuentes sobre los Canales de mercadotecnia

Consulte [Creación de reglas de procesamiento de canal de marketing](/help/components/c-marketing-channels/c-rules.md) para ver las definiciones de los campos que aparecen en la página [!UICONTROL Reglas de procesamiento de canal de marketing].

## Preguntas frecuentes {#faq}

Cada implementación de las reglas de procesamiento de canales de marketing podría diferir según sus códigos de seguimiento. La configuración de las reglas que proporcionen los resultados que necesita podría requerir cierta creatividad para resolver los problemas.

**Pregunta**: mis códigos de seguimiento no se rigen por ningún patrón y tengo que especificar miles de ellos para el canal Afiliados.

* Utilice el proceso de eliminación. Si los canales Correo electrónico y Afiliados utilizan el mismo parámetro de cadena de consulta pero solamente tiene unos cuantos códigos de seguimiento de correo electrónico, puede especificar los códigos de seguimiento de correo electrónico en un conjunto de reglas que definan el correo electrónico. Luego, clasifique todos los demás códigos de seguimiento con *`affiliates.`*
* En su sistema de correo electrónico, agregue un parámetro de cadena de consulta a todas las direcciones URL de páginas de aterrizaje, como *`&ch=eml`*. Cree un conjunto de reglas que detecte si el parámetro de consulta ch es igual a *`eml`*. Si no contiene *`eml`*, entonces es un afiliado.

**Pregunta**: Los dominios de referencia contienen más datos de lo que tenía previsto.

* Es posible que los dominios de referencia estén demasiado arriba en la lista de reglas de procesamiento. Dicho conjunto de reglas debería ser uno de los últimos (o el último): el orden de procesamiento es importante.

**Pregunta**: he creado una regla que concuerda con un parámetro de cadena de consulta y que no funciona.

* Compruebe que el nombre del parámetro esté especificado en los campos del parámetro de la cadena de consulta (normalmente, un valor alfanumérico). Asegúrese, también, de que el valor del parámetro se especifica después del operador, como se muestra en el siguiente ejemplo de regla de correo electrónico.

   ![](assets/example_email.png)

**Pregunta**: ¿por qué se atribuye todo mi tráfico de último contacto a un dominio interno?

* Hay una regla que concuerda con el tráfico interno. Recuerde que estas reglas se procesan con cada visita que el visitante haga al sitio, y no solo con la primera visita. Si tiene alguna regla similar a *`Page URL exists`* sin ningún otro criterio, con cada visita sucesiva a su sitio web, se encuentran coincidencias con ese canal, porque siempre existe una URL de página.

**Pregunta**: ¿cómo se depura el tráfico que se muestra en No se ha identificado el canal, en el informe?

* Las reglas se procesan en orden. Si no se encuentra ninguna concordancia con un criterio específico, las visitas caen en una de estas tres categorías:

1. Sin referente (visita directa).

2. Referente interno, en la primera página de la visita.

3. Problema técnico de procesamiento en la página.

Asegúrese de tener un canal para estas tres posibilidades. Por ejemplo, cree reglas como estas:

1. **[!UICONTROL Referente]** y **[!UICONTROL No existe]** y **[!UICONTROL Es la primera página de la visita]**. (Consulte [Directas.](/help/components/c-marketing-channels/c-faq.md))

2. **[!UICONTROL El referente coincide con los filtros de dirección URL internos]** y **[!UICONTROL Es la primera página de la visita]**. (Consulte [Internas](/help/components/c-marketing-channels/c-faq.md).)

3. **[!UICONTROL Referente]** y **[!UICONTROL Existe]** y **[!UICONTROL El referente no concuerda con los filtros de dirección URL internos]**.

Por último, cree el canal *Otros* para que capture las visitas restantes, tal como se describe en [No se ha identificado el canal](/help/components/c-marketing-channels/c-faq.md#no-channel-identified).

## Relación entre primer y último contacto

Para comprender la interacción entre las dimensiones de primer y último toque heredadas y confirmar que las sobrescrituras funcionan según lo esperado, puede extraer un informe de canal de primer toque, subrelacionado con un informe de canal de último toque, con la métrica de éxito clave agregada en (ver ejemplo más abajo). En el ejemplo se muestra la interacción entre los canales de primer y último contacto.

![](assets/int-channel3.png)

La intersección donde el primer toque es igual que el último toque es la diagonal de la tabla. Tanto la actualización directa como la actualización de sesión solo obtienen crédito de último toque si también son canales de primer toque, ya que no pueden tomar crédito de otros canales persistentes (filas resaltadas).

## Razones por las que no se identificó ningún Canal {#no-channel-identified}

Cuando las reglas no capturan datos o si las reglas no se han configurado correctamente, el informe muestra los datos en la fila [!UICONTROL No se ha identificado el canal] del informe. Por ejemplo, puede crear un conjunto de reglas denominado *Otro* al final del orden de procesamiento, que también identifique el tráfico interno.

![](assets/example_other.png)

Este tipo de regla sirve de captador global para asegurar que el tráfico de los canales siempre coincide con el tráfico exterior y normalmente no finaliza en **[!UICONTROL Ningún canal identificado]**. Tenga cuidado de no crear una regla que identifique también el tráfico interno. Asignar al valor del canal **[!UICONTROL Dominio de referencia]** o **[!UICONTROL Dirección URL de página]** es el modo más frecuente y útil de crear una regla Otro que funcione.

>[!NOTE]
>
>Debería haber todavía algún tráfico de canal que podría caer en la categoría Ningún canal identificado. Por ejemplo: un visitante viene al sitio, crea un marcador de una página y en la misma visita, vuelve a la página a través del marcador. Debido a que esta no es la primera página de la visita, irá al canal Directo o al canal Otros porque no hay dominio de referencia.

## Razones para la actualización interna de la sesión {#internal}

La actualización de la sesión de último toque solo se puede producir si también fue el primer toque (consulte &quot;Relación entre el primer y el último toque&quot; más arriba). Los escenarios siguientes explican cómo la actualización de la sesión podría ser un canal de primer toque.

**Escenario 1: tiempo de espera de sesión**

Un visitante llega al sitio web y luego deja la pestaña abierta en el navegador para usarla días más tarde. El periodo de interacción del visitante caduca (o elimina voluntariamente sus cookies) y utiliza la pestaña abierta para volver a visitar el sitio web. Dado que la dirección URL de referencia es un dominio interno, la visita se clasificará como “Actualización de sesión”.

**Escenario 2: no todas las páginas del sitio están etiquetadas**

Un visitante llega a la página A que no está etiquetada y luego se mueve a la página B que está etiquetada. La página A se trataría como el referente interno y la visita se clasificaría como “Actualización de sesión”.

**Escenario 3: redirecciones**

Si no se configura una redirección para pasar datos del referente a la nueva página de llegada, se pierden los datos del referente de entrada real y ahora la página de redirección (probablemente una página interna) aparece como el dominio de referencia. La visita se clasificará como “Actualización de sesión”.

**Escenario 4: tráfico entre dominios**

Un visitante pasa de un dominio que se activa con el grupo A a un segundo dominio que se activa con el grupo B. Si en el grupo B los filtros de URL internos incluyen el primer dominio, la visita en el grupo B se registrará como interna, ya que los canales de marketing la ven como una nueva visita en el segundo grupo. La visita se clasificará como “Actualización de sesión”.

**Escenario 5: largos tiempos de carga de la página de entrada**

Un visitante llega a la página A, que tiene mucho contenido, y el código de Adobe Analytics se encuentra en la parte inferior de la página. Antes de cargar todo el contenido (incluida la solicitud de imagen de Adobe Analytics), el visitante hace clic en la página B. La página B activa su solicitud de imagen de Adobe Analytics. Dado que la solicitud de imagen de la página A nunca se cargó, la segunda página aparece como la primera visita individual en Adobe Analytics, con la página A como referente. La visita se clasificará como “Actualización de sesión”.

**Escenario 6: se eliminan las cookies en el sitio intermedio**

Un visitante ingresa al sitio y luego borra las cookies a mitad de la sesión. Los canales de primer y último contacto se restablecerían y la visita se clasificaría como “Actualización de sesión” (porque el referente sería interno).

