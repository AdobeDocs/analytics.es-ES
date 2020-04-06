---
description: 'Configurar la integración de DFA implica las siguientes tareas '
keywords: DFA
title: Integración de DFA
topic: Data connectors
uuid: 972a9d62-24fd-4463-a34c-5ec0b926e81e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Integración de DFA {#dfa-integration}

Configurar la integración de DFA implica las siguientes tareas:

## Configurar la integración de DFA {#configure-the-dfa-integration}

Siga los pasos de la integración de Data Connectors de DFA.

Las páginas de configuración proporcionan información general sobre la integración, junto con vínculos útiles para obtener más información. Esta integración conlleva tarifas tanto de Adobe como de DoubleClick. Póngase en contacto con los Representantes de ventas correspondientes para ambas organizaciones y asegúrese de comprender la estructura de tarifas.

1. Inicie sesión en [!DNL Adobe Analytics].
1. Haga clic **[!UICONTROL Admin]** > **[!UICONTROL Data Connectors]**.

   ![](assets/data_connectors.png)

1. Localice **[!UICONTROL DoubleClick DFA]** y haga clic en **[!UICONTROL Add New]**.

   ![Resultado](assets/wizard-01.png)

   On each page of the Integration Wizard, provide the required information, then click **[!UICONTROL Next]**. En la tabla siguiente se explica la información necesaria para completar la integración mediante el asistente.

<table id="table_8F6F7F304C36431DA5FD6E5D54F60FC0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página del asistente # </th> 
   <th colname="col2" class="entry"> Campo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Nombre de la integración </td> 
   <td colname="col3"> El nombre de la integración que Genesis muestra en la Lista de integración activa en el grupo de informes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Dirección de correo electrónico de integración </td> 
   <td colname="col3"> Dirección de correo electrónico que recibe todas las notificaciones relacionadas con esta integración. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Nombre de usuario </td> 
   <td colname="col3"> Nombre de usuario de la API de DFA que se va a usar con esta integración. Para habilitar un usuario para el inicio de sesión de API, compruebe el atributo de API en la interfaz de DFA. Después de habilitar el inicio de sesión de API, aparece un campo de contraseña para proporcionar una contraseña al usuario. Esta contraseña se introduce junto con el nombre de usuario en el asistente de autenticación. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Contraseña </td> 
   <td colname="col3"> La contraseña de la API de DFA. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> ID del anunciante </td> 
   <td colname="col3"> <p>ID del anunciante de DFA o ID de configuración de Floodlight principal. Data Connectors utiliza este ID para identificar al anunciante de DFA para rastrear (versión 1.5 de la integración). Este ID del anunciante no se usa en la versión 2.0 de la integración (se busca y usa el ID de configuración de Floodlight principal). Consulte las instrucciones en pantalla </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> Variable de publicidad DFA </td> 
   <td colname="col3"> La eVar de Analytics que recibe datos de atributo, impresiones y clics de campaña de DFA. Generalmente, es la eVar de código de seguimiento ( <span class="varname">s.campaign</span>), pero puede elegir cualquier eVar disponible. Data Connectors también agrega las siguientes clasificaciones relacionadas con DFA a la eVar seleccionada: <p><b>Campañas</b>: Colección de anuncios ofrecidos a varios sitios que transmiten mensajes comunes. </p> <p><b>Nombre</b>del sitio: Sitio en el que se publicó el anuncio. </p> <p><b>Nombre</b>de la publicidad: El nombre del anuncio, tal como se define en la cuenta de DFA. </p> <p><b>Nombre</b>de ubicación del sitio: El sitio Web y la página donde se presentó la publicidad. </p> <p><b>Herramienta</b>Envío: DoubleClick para anunciantes. </p> <p><b>Canal</b>: Publicidad de pancarta. </p> <p><b>Estructura</b>de costes: CPM, CPC o Fijo, según la estructura de costo de la publicidad. </p> <p><b>Nombre</b>creativo: El nombre del elemento creativo asociado con un ID de anuncio/colocación/elemento creativo. </p> <p><b>DFA &gt; Anulación de duplicación de SearchCenter</b>: especifica que el DFA debería colocar valores en variables de Searchcenter cuando se generan clics o visualizaciones de DFA </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Impresiones </td> 
   <td colname="col3"> Evento personalizado que recibe datos de métricas de Impresiones DFA. Las impresiones indican el número de veces que se ha servido la publicidad. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Clics </td> 
   <td colname="col3"> Seleccione el Evento personalizado que recibe los datos de la métrica Clics de DFA. Los clics indican la cantidad de veces que los visitantes hicieron clic en el anuncio según las mediciones del redireccionamiento de DFA. La métrica de clics se correlaciona con la métrica de clics de Analytics. <p>Nota: Los clics de DFA y los clics de Analytics podrían no coincidir exactamente debido a diferencias en la forma en que se recopilan los datos.  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Variable de Vista </td> 
   <td colname="col3"> <p>La eVar de Analytics que recibe datos de Vista de DFA. La variable de Vista ayuda a observar cómo las pulsaciones de vista afectan las tasas de conversión del sitio. </p> <p>Data Connectors agrega a esta eVar las mismas clasificaciones relacionadas con DFA que a la variable de publicidad de DFA (ver arriba). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Tiempo desde la última Vista (variable de intervalo de tiempo de vista a través) </td> 
   <td colname="col3"> La eVar de Analytics que recibe datos de Tiempo desde la última Vista de DFA. El Tiempo desde la última Vista indica la cantidad de tiempo que ha transcurrido desde la última vista publicitaria. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Vistas </td> 
   <td colname="col3"> Evento personalizado que recibe datos de métricas de Vistas de DFA. Use el evento de visualizaciones con la variable de visualización para ver qué campañas no influenciaron un clic directo, pero pueden haber participado en direccionar tráfico al sitio en algún momento posterior. <p>Data Connectors cambia el nombre del evento personalizado seleccionado a “Visualizaciones”. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Error en consulta DFA </td> 
   <td colname="col3"> (Opcional) La eVar de Analytics que recibe los códigos de mensaje de error de consulta DFA notificados. Los posibles códigos de mensajes DFA incluyen: 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>: No hay cookie DoubleClick. </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b>: El usuario ha exclusión. </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>: No hay historial de campañas. </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>: Error de Consulta (tiempo de espera, servidor inactivo, etc.) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Evento de tiempo de espera </td> 
   <td colname="col3"> <p>El Evento de contador de Analytics que se incrementa cada vez que caduca el temporizador <span class="varname">s.maxDelay</span> sin recibir respuesta de los servidores de DFA. Use este evento para configurar la variable <span class="varname">s.maxDelay</span> Ajuste de s.maxDelay</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Actualizaciones de sitios web para la Integración de DFA {#web-site-updates-for-the-dfa-integration}

Una vez que Genesis ha configurado el grupo de informes de Analytics para la integración de DFA, se debe hacer lo siguiente para configurar el sitio web y el entorno de DFA para admitir la integración:

### Verifique el espacio de cookie en el dominio {#verify-cookie-space-on-the-domain}

La integración de Data Connectors para DFA requiere que establezca una cookie en el dominio de la página.

Aunque es raro, algunos dominios han alcanzado la capacidad máxima de cookies para algunos exploradores Web. Para impedir que la experiencia de exploración de un visitante en el sitio web se vea afectada, consulte con el equipo de desarrollo u operaciones de red, o con el grupo de ingeniería para verificar si al agregar otra cookie al dominio de las páginas que se use para la integración de DFA no afecta a la experiencia del usuario. También deberá seleccionar un nombre para la cookie.

### Actualizar el parámetro de cadena de consulta de DFA {#update-your-dfa-query-string-parameter}

Si ya ha estado rastreando campañas de publicidad con Adobe Analytics antes de la integración de DFA, es posible que todas las campañas (correo electrónico, búsqueda o titular) utilicen el mismo parámetro de cadena de consulta para identificar el ID de campaña de referencia en la página de aterrizaje.

Para comprender cuándo se deben solicitar datos de visualizaciones y clics desde datos de DFA para sus campañas de publicidad de DFA, Data Connectors necesita identificar cuándo un visitante ha hecho clic en un anuncio de titular de campaña de DFA. Para que sea posible, debe agregar un parámetro de cadena de consulta diferenciado a la dirección URL de la página de aterrizaje de la campaña de publicidad de DFA. De esta manera, Data Connectors puede distinguir entre páginas de campañas de publicidad de DFA y entre otras páginas de campañas de publicidad que usted podría tener en el sitio web. La variable `dfa_overrideParam` en el complemento JavaScript utilizado para DFA.

>[!CAUTION]
>
>Aunque la variable Campaña se puede usar para otras campañas, no la use para campañas de DFA. Si establece la variable de Campaña en una página de aterrizaje de campaña de DFA, Adobe no puede unir las impresiones y los clics con accesos a campaña de DFA. Una vez por visita, los servidores de recopilación de Adobe comprueban en servidores DFA si hay un clic o una visualización previos. Por este motivo, incluya el código de complemento de DFA solamente en páginas de aterrizaje comunes para evitar redireccionamientos innecesarios que pueden ralentizar los tiempos de carga de las páginas, particularmente para usuarios con conexiones a Internet más lentas.

## Actualizar el código de la recopilación de datos de su sitio web {#update-your-web-site-s-data-collection-code}

La integración de Genesis para DFA aprovecha el ID de configuración de Floodlight DFA (dfa_SPOTID), que mejora la coherencia de informes entre el sistema de recopilación de datos de Adobe y DFA.

>[!NOTE] El término Spotlight se cambió a Floodlight en una versión reciente de DFA de Google. El parámetro JavaScript `dfa_SPOTID` recibió su nombre por la terminología de Spotlight pero se usa para ambas versiones.

Para habilitar la integración de DFA en el sitio Web, debe actualizar el código de recopilación de datos JavaScript agregando lo siguiente:

* Módulo Integrate para DFA
* Adición al código de recopilación

### Módulo Integrate para DFA {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

La integración de DFA aprovecha el módulo Integrate de Adobe Experience Cloud, que agrega funcionalidad al código de recopilación de datos de JavaScript principal (`s_code.js`). El módulo Integrate se incluye como parte del archivo .zip cuando se descarga el código de AppMeasurement para JavaScript desde el Administrador de códigos. Póngase en contacto con un consultor de Adobe solo si necesita ayuda adicional.

Inserte el código del módulo Integrate en la sección `Modules` del archivo `s_code.js` de su sitio web.

### Adición al código de la recopilación {#section-8f98c727f1ba414fb8b4f02d696b8791}

Según las selecciones al activar la integración de DFA en el asistente de integración, Data Connectors generan y le envían un correo electrónico con una adición personalizada a su código de recopilación de datos JavaScript. Inserte este código en la sección principal del archivo `s_code.js` (no en la función `doPlugins` u otra función).

El código de muestra aparece a continuación con fines ilustrativos únicamente; use el código que recibió por correo electrónico después de completar el asistente de integración de Data Connectors.

El código de recopilación consta de los siguientes componentes:

* Configuración de integración de DFA
* Complementos requeridos por la integración

**Configuración de integración de DFA**

```
/************************** DFA VARIABLES **************************/ 
var dfaConfig = { 
   CSID:              "1234567", 
   SPOTID:            "29876543", 
   tEvar:             "eVar17", 
   errorEvar:         "eVar59", 
   timeoutEvent:      "event76", 
   requestURL:         "http://fls.doubleclick.net/ 
json?spot=[SPOTID]&src=[CSID]&var=[VAR]&host=integrate.112.2o7.net%2 
Fdfa_echo%3Fvar%3D[VAR]%26AQE%3D1%26A2S%3D1&ord=[RAND]", 
 
   maxDelay:          "1500", 
   visitCookie:       "s_dfa", 
   clickThroughParam: "CID", 
   searchCenterParam: "s_kwcid", 
   newRsidsProp:      undefined 
}; 
/************************ END DFA Variables ************************/ 
```

El bloque Configuración de integración de DFA establece las variables requeridas por la integración de DFA. Los valores de cada una de estas variables provienen de las siguientes fuentes:

**CSID**: ID del cliente. Generado por DFA una vez que usted completa el asistente de integración. Data Connectors rellena previamente esta variable con el ID CS de DFA, y también le envía este valor en el correo electrónico de configuración una vez que completa el asistente de integración. Esta variable no es necesaria si el servicio de publicidad avanzado está habilitado en su cuenta.

**SPOTID**: Configuración de Floodlight (anteriormente denominada ID de Spotlight). Data Connectors rellena previamente esta variable con el ID de configuración de Floodlight DFA según la información de cuenta DFA especificada en el asistente de integración.

**tEvar**: Variable de transferencia. Data Connectors rellena previamente esta variable con el nombre de la variable de Analytics que especificó para la variable de Visualización en el asistente de integración. No cambie este valor sin una cuidadosa coordinación con los servicios de ingeniería o ingeniería de Adobe.

**errorEvar**: Variable de error. Data Connectors rellena previamente esta variable con el nombre de la variable de Analytics que especificó para la variable de Error en consulta DFA en el asistente de integración.

**timeoutEvent**: Evento de tiempo de espera. Data Connectors rellena previamente esta variable con el nombre de la variable de Analytics que especificó para la variable de Evento de tiempo de espera en el asistente de integración.

**requestURL**: El host de DFA remoto en consulta para información de publicidad. No cambie este valor a menos que Adobe se lo indique.

**maxDelay**: Especifica la cantidad de tiempo que el código de recopilación de datos JavaScript espera una respuesta del servidor de Floodlight DFA, en milisegundos. Adobe recomienda experimentar con este valor para hallar el valor óptimo según el tráfico del sitio. Por ejemplo: al aumentar este valor generalmente se recopilan más datos de DFA, pero se aumenta el riesgo de perder los datos de visitante base si el visitante abandona el sitio durante el período de demora. Al reducir este valor, disminuye el riesgo de perder datos de visitas, pero puede reducir la cantidad de datos de DFA enviados con los datos de visitas de Adobe.

**visitCookie**: Nombre de la cookie utilizada para restringir las llamadas de DFA a una vez por visita.

**clickThroughParam**: un parámetro de consulta, generalmente incluido en todos los anuncios, que notifica al módulo Integrate de que acaba de producirse un clic. La presencia de este parámetro en la cadena de consulta hace que la solicitud se realice en los servidores de Floodlight DFA sin importar si el visitante ya se ha consultado en los últimos 30 minutos.

**newRsidsProp**: (Opcional) Asignado a una variable de propiedad de tráfico no utilizada. La integración de DFA recopila y almacena este valor en la cookie de visita para identificar los grupos de informes que recopilaron datos para un visitante en particular. Esta propiedad solo se necesita con implementaciones personalizadas con los servicios de ingeniería de Adobe.

**Complementos requeridos por la integración**

La adición Código de recopilación incorpora complementos adicionales que mejoran el funcionamiento de la integración de DFA:

* Limita las consultas de DFA a una vez por visita
* Proporciona flexibilidad en el nombre de la cookie. Aunque la mayoría de las organizaciones utilizan s_dfa, puede utilizar cualquier nombre de cookie válido para la integración de DFA.
* Elimina redirecciones innecesarias. Debido a que los datos de vista se recopilan en tiempo real, los servidores de recopilación de Adobe y DFA podrían intercambiar datos en cada vista de página. El complemento bloquea estos intercambios de datos cuando la información no es necesaria.

>[!CAUTION]
>
>Uno de los mecanismos que el complemento usa para eliminar consultas de DFA innecesarias es una cookie de visita basada en el dominio. Un grupo de informes de integración que abarca varios dominios infla datos de clic y visualización cuando los visitantes abarcan varios dominios después de una visualización o un clic influenciados por DFA.

## Confirmar una integración DFA correcta {#confirming-a-successful-dfa-integration}

Después de haber realizado todas las actualizaciones de sitios web que se requieran, puede usar un visualizador de tráfico de red, como Charles*, Chrome Developer Tools o Firebug* para confirmar que DFA se está comunicando con los servidores de recopilación de Adobe.

Después de haber implementado el archivo `s_code.js` que se puede usar con DFA, use el visualizador de tráfico de red para ver las solicitudes entre los servidores de recopilación de datos de Adobe y DFA, buscando lo siguiente:

* Una solicitud al servicio `fls.doubleclick.net/json` de DFA. Este servicio puede responder de forma diferente en función de la versión de DFA que esté utilizando. Con la versión 1.5 de Integración de DFA:

   * Un redireccionamiento HTTP 302 a [!DNL ad.doubleclick.net]. Enviará una etiqueta Location: en la respuesta que contiene información acerca del visitante del anuncio.
   * Esta etiqueta Location ocasiona un redireccionamiento a [!DNL integrate.112.2o7.net/dfa_echo]. Este servicio traduce la información sobre el visitante de publicidad en una cadena codificada JSON (JavaScript Object Notati on). Estos datos se devuelven con una respuesta HTTP de 200 OK.

* Con DFA Integration versión 2.0 (Servicio de publicidad avanzado habilitado):

   * [!DNL fls.doubleclick.net] responderá directamente con 200 OK.

En cualquier caso, una solicitud correcta resultará en una solicitud a los servidores de recopilación de datos de Adobe que contenga el parámetro vX, donde X es el número de eVar de Vista. Este valor de parámetro toma la forma: DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX. Esta cadena contiene datos sobre el último clic y la última impresión del visitante actual.

## Ajuste de s.maxDelay {#tuning-s-maxdelay}

Lograr una implementación correcta de DFA implica optimizar s.maxDelay para el sitio específico.

En general, la decisión de aumentar o reducir *`s.maxDelay`* implica un equilibrio entre obtener más datos de visitantes de DFA y poner en peligro la recopilación de datos de visitantes de Adobe. Al aumentar *`s.maxDelay`* se obtienen más datos del visitante de DFA, pero cuando se coloca excesivamente alto, podría poner en riesgo la recopilación de datos de visitantes de Adobe. Al reducir s.maxDelay se garantiza la recopilación de datos del visitante de Adobe, pero podría perder datos del visitante de DFA.

*`s.maxDelay`* encapsula más que solo el tiempo en la comunicación de red para ponerse en contacto con DFA; también representa demoras del explorador para activar y evaluar el JavaScript desde el cual se basan estas comunicaciones. Esto se debe a que el módulo Integrate inicia el temporizador de *`s.maxDelay`* después de haber insertado el elemento HTML en el DOM que extrae los datos del servidor de Floodlight de DFA. La cantidad de tiempo que tarda el explorador en iniciar la solicitud HTTP en función de este nuevo elemento HTML varía según otras imágenes o archivos JavaScript que se carguen simultáneamente, la velocidad del equipo de visitantes y las implementaciones específicas del explorador. Además, cuando los datos JSON se recuperan del servidor de Floodlight DFA, el explorador debe evaluar el JavaScript. De nuevo, el explorador lo controla completamente y se puede retrasar si hay grandes cantidades de código JavaScript ejecutándose simultáneamente o muchas solicitudes JavaScript asincrónicas.

Teniendo en cuenta esto, *`s.maxDelay`* debe establecerse en función de la complejidad de la página de aterrizaje más la demora de red con DFA. En algunos sitios, una forma posible de reducir la complejidad es activar el código de recopilación de Adobe al principio de la carga de página, de modo que haya menos movimiento en el explorador cuando se solicita el servidor de Floodlight.

La variable Timeout es absolutamente necesaria al ajustar *`s.maxDelay`*, porque se incrementa cada vez que se alcanza el tiempo de espera s.maxDelay. A la hora de decidir si aumentar o disminuir *`s.maxDelay`* recomendamos seguir este proceso:

1. Recopile varios días de datos con *`s.maxDelay`* en un valor determinado.
1. Ejecute un [!DNL Daily Unique Visitors Report] para el intervalo de tiempo.
1. Ejecute el [!DNL Timeout Event Report] para comprobar la cantidad de tiempos de espera que están surgiendo. Recuerde que un tiempo de espera solo se recopila una vez por visitante.

Ahora teniendo las cifras a mano, compute

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

Observe que el Porcentaje de tiempo de espera está considerando todos los visitantes al sitio. Algunos de esos visitantes no se habrían vinculado a DFA en absoluto, por lo que el tiempo de espera es engañoso. Para mejorar este cálculo, otro análisis podría considerar solamente los visitantes únicos de las páginas con el `clickThroughParam` establecido (por ejemplo, `?CID=1`). Esto mostrará más precisión.

Si el Porcentaje de tiempo de espera es muy bajo, considere la posibilidad de reducir *`s.maxDelay`*. Si es muy alto, incremente *`s.maxDelay`*. Al disminuir *`s.maxDelay`*, tiene que volver a ejecutar el [!DNL Timeout Report] para asegurarse de que los tiempos de espera no se incrementan de forma notable. Al aumentar *`s.maxDelay`*, saque un [!DNL Page Views Report] para asegurarse de que las vistas de página no decaen debido a la pérdida de datos. Cada vez que *`s.maxDelay`* cambie, observe los datos durante varios días para asegurarse de que los datos representen una tendencia y no solo una fluctuación día a día.

La configuración recomendada para *`s.maxDelay`* es el punto en el cual se minimiza el porcentaje de tiempo de espera mientras que las Vistas de página no caen.

Se espera que los tiempos de espera disminuyan al pasar a la versión 2.0 de la integración, debido a las eliminaciones de las redirecciones 302. Los hallazgos iniciales con clientes beta han mostrado una reducción constante de los tiempos de espera y, por lo tanto, se están recopilando más datos de DFA
