---
title: Seguimiento de correo electrónico externo
description: Utilice Adobe Analytics para realizar un seguimiento del contenido del correo electrónico.
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651
workflow-type: ht
source-wordcount: '736'
ht-degree: 100%

---


# Seguimiento de correo electrónico externo

Las empresas usan Analytics para determinar el éxito de una campaña de correo electrónico.

[!DNL Analytics] puede generar informes sobre los datos de análisis de campañas de correo electrónico con algunas métricas clave, entre ellas:

| Métrica | Descripción |
|---|---|
| Pulsaciones | Muestra el número de pulsaciones seguidas desde el correo electrónico hasta la página de aterrizaje. |
| Compras y/o éxitos | Muestra el número de compras como resultado del correo electrónico. |
| Pedidos | Muestra el número de pedidos realizados como resultado del correo electrónico. |
| Rendimiento | Muestra la cantidad en dólares por visita generados a partir del correo electrónico. |
| Conversión | Muestra el número de posibles clientes, registros y otros eventos de éxito generados a partir del correo electrónico. |

Es necesario realizar modificaciones en el cuerpo del correo electrónico HTML y en la biblioteca JavaScript para capturar las métricas clave antes indicadas.

## Implementación {#section_8A42A8F4A6CD4A1BAF4B9F99F709AF7A}

Hay que seguir varios pasos en orden para mostrar correctamente los datos de análisis de la campaña de correo electrónico. A continuación se describen estos pasos:

1. Cree códigos de seguimiento únicos.

   Con frecuencia, los usuarios piden realizar el seguimiento de las recomendaciones de cada campaña única. Depende completamente de ellos, según lo que mejor funcione. Cada usuario es diferente. Adobe recomienda que cada usuario genere códigos de seguimiento descriptivos, tal y como se muestra en el siguiente ejemplo:

   * sc_cid=A1123A321 > &quot;A&quot; marca una campaña afiliada
   * sc_cid=EM033007 > &quot;EM&quot; marca una campaña de correo electrónico
   * sc_cid=GG987123 > &quot;GG&quot; significa Google y es una campaña de búsqueda de pago

   Póngase en contacto con Adobe [!DNL Customer Care] para obtener más información sobre cómo configurar y usar códigos de seguimiento.

1. Agregue parámetros de cadena de consulta a los vínculos de correo electrónico HTML.

   Para realizar un seguimiento de las pulsaciones de un usuario y los eventos de éxito posteriores, es necesario agregar un parámetro de cadena de consulta a cada vínculo dentro del correo electrónico HTML. Puede elegir realizar un seguimiento de cada vínculo por separado o seguirlos todos juntos. Cada vínculo puede tener un código de seguimiento único, o todos los vínculos pueden tener el mismo código de seguimiento. Considere el siguiente vínculo hipotético dentro del correo electrónico a un sitio web:

   ```js
   <a href="https://www.example.com/index.asp">Visit our home page</a>
   ```

   Deben agregarse los siguientes parámetros de cadena de consulta ?sc_cid=112233B al vínculo anterior:

   ```js
   <a href= "https://www.example.com/index.asp?sc_cid=112233B">Visit our home page</a>
   ```

1. Actualice la biblioteca JavaScript.

   Modificar el código en el archivo JavaScript, [!DNL s_code.js], permite capturar cuántos usuarios (y cuáles) pulsaron desde el correo electrónico y participaron en los posteriores eventos de éxito. Para actualizar la biblioteca JavaScript hay que seguir dos pasos.

   1. Personalizar [!DNL s_code.js] mediante una llamada a [!UICONTROL getQueryParam].

      El archivo [!DNL s_code.js] debe colocarse en una ubicación del servidor web en la que todas las páginas web tengan acceso a él. La función *`doPlugins`* en este archivo debe modificarse para que capture los parámetros de cadena de consulta en los vínculos de correo electrónico. Por ejemplo:

      ```js
      /* Plugin Config */ 
      s.usePlugins=true 
      function s_doPlugins(s) { 
       /* Add calls to plugins here */ 
       // External Campaigns 
      s.campaign=s.getQueryParam('source') 
      } 
      s.doPlugins=s_doPlugins 
      ```

      Cada parámetro de cadena de consulta que debe copiarse a una variable debe tener una llamada a [!UICONTROL getQueryParam]. En el ejemplo anterior, el parámetro de cadena de consulta [!UICONTROL sc_cid] se copia en *`campaign`*.

      Solo se necesita la primera llamada a [!UICONTROL getQueryParam] para capturar las pulsaciones. Póngase en contacto con Adobe [!DNL Customer Care] para implementar esta función y asegurarse de que su versión del archivo JavaScript contiene el complemento [!UICONTROL getQueryParam].

   1. Asegúrese de que las etiquetas de código para pegar de JavaScript están en todas las páginas de aterrizaje. Este código para pegar debe hacer referencia a la versión de [!DNL s_code.js] modificada en la parte A.

      Es importante recordar algunos puntos a la hora de actualizar la biblioteca JavaScript. Son:

      * El parámetro de cadena de consulta [!UICONTROL sc_cid] debe ser visible en la dirección URL de la página de aterrizaje final o, de lo contrario, no se registrará ninguna conversión por pulsación.
      * El parámetro [!UICONTROL sc_cid] es un ejemplo de parámetro de cadena de consulta. El complemento [!UICONTROL getQueryParam] puede usar y capturar cualquier parámetro de cadena de consulta. Asegúrese de que los parámetros de cadena de consulta solo se usan para el seguimiento de campañas. Cada vez que los parámetros aparecen en una cadena de consulta, su valor se copia en *`campaign`*.

1. Use [!UICONTROL SAINT] para clasificar los códigos de seguimiento de campaña.

   Se puede usar la [!UICONTROL herramienta para gestión de campañas SAINT] para convertir los códigos de seguimiento en nombres descriptivos. También se puede usar para resumir el éxito de cada campaña de correo electrónico. El paso 5, a continuación, esquematiza el proceso necesario para configurar una campaña de correo electrónico.

1. Consulte las rutas por campaña de correo electrónico (opcional).

   El análisis del control de rutas por campaña de correo electrónico se puede realizar de manera similar al control de rutas por cualquier otra campaña. Puede usar una variable para mostrar el control de rutas por campaña, como se explica en los siguientes pasos:

   1. Consulte con Adobe [!DNL Customer Care] cómo activar el control de rutas para una variable [!UICONTROL Perspectiva personalizada] (prop)

   1. En todas las páginas, copie el nombre de la página en la [!DNL s.prop] designada.
   1. En la página de aterrizaje del correo electrónico, anexe el nombre de la campaña de correo electrónico a la prop. El resultado será el siguiente:

      ```js
      s.prop1="Home Page : 123456"
      ```

      Cuando el control de rutas está habilitado para la variable [!UICONTROL Perspectiva personalizada], puede usar los informes de [!UICONTROL Rutas] (como [!UICONTROL Flujo de página siguiente] o [!UICONTROL Visitas en el orden previsto]) para ver la navegación del visitante desde la página de aterrizaje.

