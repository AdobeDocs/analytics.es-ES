---
title: Reglas de procesamiento de canales de marketing
description: Las reglas de procesamiento de canales de mercadotecnia averiguan si la visita de un visitante cumple los criterios asignados a un canal. Las reglas procesan cada visita que realizan los usuarios a su sitio web. Cuando una regla no cumple los criterios de un canal, o si las reglas no están configuradas correctamente, el sistema asigna la visita a No se ha identificado el canal.
translation-type: tm+mt
source-git-commit: c10a12781a8fe52b7b897cd337dc686aa0bbb240

---


# Reglas de procesamiento de canales de marketing

Las reglas de procesamiento de canales de mercadotecnia averiguan si la visita de un visitante cumple los criterios asignados a un canal. Las reglas procesan cada visita que realizan los usuarios a su sitio web. Cuando una regla no cumple los criterios de un canal, o si las reglas no están configuradas correctamente, el sistema asigna la visita a No se ha identificado el canal.

Pautas importantes para la creación de reglas:

* Ordene las reglas en el orden en el que desee que se procesen.
* Al final de la lista, introduzca un captador global como, por ejemplo, Otras. Esta regla identifica el tráfico externo, pero no el interno.

   Consulte [No se ha identificado el canal.](/help/components/c-marketing-channels/c-faq.md)

> [!NOTE] A pesar de que estas reglas no afectan a los informes externos a los canales de marketing, sí afectan a la recopilación de datos del canal de marketing. Los datos recopilados con estas reglas son 100 % permanentes y las reglas alteradas tras la colección de datos no son retroactivas. It is strongly recommended to review and consider all circumstances before saving [!UICONTROL Marketing Channel Processing Rules] to mitigate data being collected in incorrect channels.

## Requisitos previos

* Consulte la información conceptual de [Introducción a los canales](/help/components/c-marketing-channels/c-getting-started-mchannel.md)de mercadotecnia.
* Cree uno o más canales para poder asignarles reglas. Consulte [Agregar canales de marketing.](/help/components/c-marketing-channels/c-channels.md)

## Creación de reglas de procesamiento para los canales de mercadotecnia

Cree reglas de procesamiento de canales de mercadotecnia que averigüen si la visita de un visitante cumple los criterios asignados a un canal.

Este procedimiento emplea una regla de correo electrónico como ejemplo. En este ejemplo, se presupone que ha agregado un canal de correo electrónico a su lista de canales de la página Administrador de canales de mercadotecnia.

1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Selección de un grupo de informes.

   If your report suite does not have channels defined, the [!UICONTROL Marketing Channels: Auto Setup] page displays.

   See [Run the Automatic Setup](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Haga clic **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

   ![Resultado](assets/marketing_channel_rules.png)

1. En el **[!UICONTROL Add New Rule Set]** menú, seleccione **[!UICONTROL Email]**.

   Al hacerlo, no selecciona el canal, sino que selecciona una plantilla que rellena la regla con algunos parámetros necesarios.

   ![Resultado](assets/example_email.png)

   Utilice lógica booleana (instrucciones de if / then) para configurar una regla. Por ejemplo, en la regla de canal de correo electrónico, proporcione la configuración o la información resaltada en la siguiente instrucción de regla:

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   En este ejemplo, *`<value>`* es el parámetro de cadena de consulta que usa en su campaña de correo electrónico, como *`eml`*.
1. Para continuar creando reglas, haga clic en **[!UICONTROL Add Rule]**.
1. Para priorizar las reglas, arrástrelas a la posición que corresponda.
1. Haga clic en **[!UICONTROL Save.]**

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes y ejemplos](/help/components/c-marketing-channels/c-faq.md)


## Criterios de regla de canal de mercadotecnia

Esta tabla de referencia define los campos, las opciones y los atributos de visita que puede seleccionar en la página Reglas de procesamiento de canal de mercadotecnia.

| Término | Definición |
|--- |--- |
| Todos | Activa este canal solamente cuando todas las reglas de la regla numerada son verdaderas. |
| Cualquiera | Activa este canal cuando cualquiera de las reglas del conjunto de reglas es verdadera. Esta opción está disponible solamente si existe más de una regla en la regla numerada. |
| ID de AMO | El código de seguimiento principal utilizado por las integraciones de Advertising Cloud y Advertising Analytics. Cuando se habilita una de estas integraciones, puede usar el prefijo del código de seguimiento para identificar canales específicos de Advertising Cloud. Utilice “AMO ID” para comenzar con “AL” para la búsqueda, “AC” para la visualización o “AO” para Social. Cuando se utiliza el ID de AMO en los canales de marketing, las métricas de clics, costes e impresiones se pueden atribuir al canal correcto (cuando no se configuren, estas métricas irán a Directas o a Ninguna). |
| AMO ED ID | Código de seguimiento secundario utilizado por Advertising Cloud. El propósito principal de este código de seguimiento es servir como clave para enviar datos de vuelta a Ad Cloud. Sin embargo, también se puede utilizar para identificar Mostrar clics respecto a Mostrar vistas si desea verlas como dos canales de marketing independientes. Esto se puede hacer configurando que la lógica del canal de marketing para “AMO EF ID” termine con “:d” para las visualizaciones de pulsaciones o que “AMO EF ID” termine con “:i” para Mostrar vistas. Si no desea dividir Mostrar en dos canales, utilice la dimensión de ID de AMO en su lugar. |
| Variables de conversión | Contiene eVars que se han habilitado para este grupo de informes y se aplica solamente cuando las variables se definen mediante el código de Adobe en la página.  Consulte la Guía de implementación . |
| Existe | Se ofrecen varias opciones, entre ellas:<ul><li>**No existe**: indica que el atributo de visita no existe en la solicitud. Por ejemplo, en un dominio referente, si el usuario escribe una dirección URL o hace clic en un marcador, el atributo de dominio referente no existe.</li><li>**Está vacío**: indica que existe un atributo de visita que, generalmente, es un parámetro de eVar o de cadena de consulta, pero que no hay ningún valor asociado al atributo de visita.</li><li>**No contiene**: permite especificar, por ejemplo, que un dominio referente no contiene un valor específico (a diferencia de la opción &quot;Contiene&quot;.)</li></ul> |
| Identificar el canal como | Asocia la regla con un canal de mercadotecnia que haya agregado a la página Administrador de canales de mercadotecnia.  Consulte Agregar canales de marketing . |
| Concuerda con las reglas de detección de búsqueda paga | Búsqueda paga detectada por Adobe. Las búsquedas pagas se dan cuando las empresas pagan una tarifa al motor de búsqueda para que las incluyan en las listas de su sitio. Por lo general, la búsqueda paga aparece en la parte superior o en el lado derecho de los resultados de búsqueda. |
| Concuerda con las reglas de detección de búsqueda natural | Búsqueda no paga detectada por los informes de Adobe. |
| El referente concuerda con los filtros de dirección URL internos | Visita cuya dirección URL de página coincide con un filtro de dirección de URL interno, tal como se define en el grupo de informes de las Herramientas de administración. |
| El referente no concuerda con los filtros de dirección URL internos | La dirección URL de referencia no coincide con un filtro de dirección de URL interno, tal como se define en el grupo de informes de las Herramientas de administración. Puede utilizar esta configuración con  URL de página  y  Existe  para definir una regla de captador global y evitar que las visitas se dirijan a la sección del informe  No se ha identificado el canal . |
| Hacer caso omiso de visitas que coincidan con los filtros de direcciones de URL internas | (Para los referentes) Realiza un seguimiento, solamente, de las visitas que provienen de sitios de referencia externos. Por lo general, se deja sin activar, salvo que desee incluir el tráfico interno. |
| Es la primera página de la visita | Primera página de una visita detectada por los informes de Adobe. |
| Página | El nombre de una página web del sitio que está etiquetada con la señalización web de Adobe. Este valor equivale a  s.pageName . Algunos ejemplos son `Home Page` y `About Us`. |
| Dominio de página | The domain of the page on which the visitor lands, such as `products.example.co.uk`. |
| Dominio y ruta de página | Dominio y ruta, como `products.example.co.uk/mens/pants/overview.html` . |
| Dominio raíz de página (TLD+1) | El dominio raíz de la página donde aterriza el visitante como, por ejemplo, ejemplo.es . |
| URL de la página | La dirección URL de una página web de su sitio. |
| Dominio de referencia | The domain your visitors came from before they visited your site, for example, referrers coming from `abcsite.com` versus `xyzsite.com`. |
| Parámetro de cadena de consulta | If a page URL on your site looks like `https://example.com/?page=12345&cat=1`, then page and cat are both query string parameters. (Consulte `https://en.wikipedia.org/wiki/Query_string`.)  Puede especificar solamente un parámetro de cadena de consulta por cada conjunto de reglas. To add additional query string parameters, use `ANY` as your operator, then add new query string parameters to the rule. |
| Referente | Ubicación de la página web (dirección URL completa) en la que se encontraban los visitantes antes de entrar en el sitio. El referente existe fuera del dominio que haya definido. |
| Dominio y ruta de referencia | Una concatenación del dominio de referencia y la ruta URL. Algunos ejemplos son:    `www.example.com/products/id/12345` O bien `ad.example.com/foo` |
| Parámetro de referencia | Un parámetro de cadena de consulta de la dirección URL de referencia. For example, if your visitors come from `example.com/?page=12345&cat=1`, then page and cat are the referring parameters. |
| Dominio raíz de referencia | El dominio raíz del referente. El referente existe fuera del dominio que haya definido. |
| Motor de búsqueda | Un motor de búsqueda, como Google o Yahoo!, que trajo visitantes al sitio. |
| Palabras clave de búsqueda | Una palabra que se utiliza para llevar a cabo una búsqueda mediante un motor de búsqueda. |
| Motor de búsqueda + Palabras clave | Una concatenación de la palabra clave de búsqueda y el motor de búsqueda que identifica de forma exclusiva el motor de búsqueda. Por ejemplo, si busca la palabra ordenador, el motor de búsqueda y la palabra clave se identifican de este modo: `Search Tracking Code = "<search_type>:<search engine>:<search keyword>" where    search_type = "n" or "p", search_engine = "Google", and search_keyword = "computer"`**Nota:**n = natural; p = de pago |
| Definir el valor del canal en | Además de saber qué canal de marketing lleva al visitante a su sitio, puede saber también qué anuncio de banner, palabra clave de búsqueda o campaña de correo electrónico dentro del canal recibe crédito por la actividad del visitante en el sitio. Este identificador es un valor de canal que se almacena junto con el canal. A menudo, este valor es un identificador de campaña integrado en la página de aterrizaje o en la dirección URL de referencia; en otros casos es la combinación del motor de búsqueda y la palabra clave de búsqueda, o bien, la dirección URL de referencia que identifica de forma más correcta al visitante en un canal particular. |

## Canal interno (actualización de sesión)

El canal interno (con frecuencia denominado “actualización de sesión”) consiste en visitas al sitio donde la dirección URL de referencia coincide con la configuración de los filtros de URL internos en Admin Console, lo que significa que el visitante vino desde dentro del sitio para iniciar la visita.

![](assets/int-channel1.png)

### Prácticas recomendadas sobre anulaciones

Se recomienda desactivar la opción de anulación del último contacto para los canales directos e internos, de modo que no puedan tomar crédito de otros canales de último contacto persistentes (o entre sí).

>[!NOTE]Este documento supone que la actualización directa y de sesión tienen la opción “Anular” desactivada.

![](assets/int-channel2.png)

### Periodo de interacción

Los canales de primer y último contacto de un visitante se restablecen tras 30 días de inactividad en ese navegador.

>[!NOTE] 30 días es el valor predeterminado y se puede modificar según sea necesario mediante la configuración de la administración.

Si el visitante utiliza el sitio con frecuencia, la ventana de participación se abrirá. Debe estar inactivo durante 30 días para que caduque el periodo y se restablezcan los canales.
Ejemplo:

* Día 1: el usuario llega al sitio y este aparece en la pantalla. Los canales de primer y último contacto se definirán como “Pantalla”.

* Día 2: el usuario entra al sitio a través de una búsqueda natural. El primer contacto permanece como “Pantalla” y el último contacto se establece como “Búsqueda natural”.

* Día 35: el usuario no ha accedido al sitio en 33 días y regresa usando la pestaña que había abierto en su navegador. Suponiendo que se trate de una ventana de participación de 30 días, la ventana se habría cerrado y las cookies del canal de marketing habrían caducado. El canal de primer contacto y último contacto se restablecerán y se configurarán en Actualización de sesión, ya que el usuario accedió con una URL interna.

### Relación entre primer y último contacto

Para comprender la interacción entre el primer y el último contacto, y confirmar que las anulaciones funcionan según lo esperado, puede extraer un informe de canal de primer contacto, subrelacionado con un informe de canal de último contacto, con la métrica de éxito clave en (ver ejemplo más abajo). En el ejemplo se muestra la interacción entre los canales de primer y último contacto.

![](assets/int-channel3.png)

La intersección en la que el primer contacto es igual que el último contacto se resalta en naranja. Tanto la actualización directa como la actualización de sesión solo obtienen crédito de último contacto si también son el canal de primer contacto, ya que no pueden tomar crédito de otros canales persistentes (filas resaltadas en gris).

### ¿Por qué se produce la actualización de la sesión?

Como sabemos que la actualización de sesión de último contacto solo puede producirse si también fue el primer contacto, los escenarios siguientes explican cómo la actualización de sesión puede ser un canal de primer contacto.

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
