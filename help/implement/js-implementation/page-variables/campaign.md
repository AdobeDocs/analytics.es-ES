---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---



# campaign

La variable identifica las campañas de marketing utilizadas para atraer visitantes a un sitio. El valor de generalmente se toma de un parámetro de cadena de consulta.
https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/page-variables/browserheight.html

<!-- 

campaign.xml

 -->

**Parámetros**

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>255 bytes </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>Conversión &gt; Campañas &gt; Código de seguimiento </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

Todos los elementos de una campaña de marketing deben tener asociado un código de seguimiento único. Por ejemplo, una palabra clave de pago del motor de búsqueda puede tener un código de seguimiento 112233. Cuando alguien hace clic en la palabra clave con el código de seguimiento 112233 y es enrutado al sitio web correspondiente, la variable *`campaign`* registra el código de seguimiento.

Hay dos maneras de rellenar la variable *`campaign`*:

* El complemento [!UICONTROL getQueryParam], usado en el archivo JavaScript, recupera un parámetro de cadena de consulta de la dirección URL. Para obtener más información sobre el complemento [!UICONTROL getQueryParam], consulte [Complementos de implementación](/help/implement/js-implementation/plugins/impl-plugins.md).

* Asigne un valor a la variable *`campaign`* en el HTML de la página web.

Con cualquiera de los métodos para rellenar la variable *`campaign`*, el tráfico del botón Atrás puede aumentar el número real de pulsaciones desde un elemento de campaña.

Por ejemplo, un visitante entra en el sitio haciendo clic en una palabra clave de búsqueda de pago. Cuando el visitante llega a la página de aterrizaje, la dirección URL contiene un parámetro de cadena de consulta que identifica el código de seguimiento de la palabra clave. Después, el visitante hace clic en un vínculo a otra página, pero inmediatamente hace clic en el botón Atrás para volver a la página de aterrizaje. Cuando el visitante llega por segunda vez a la página de aterrizaje, la dirección URL con el parámetro de cadena de consulta identifica de nuevo el código de seguimiento y se registra una segunda pulsación, aumentando incorrectamente el número de pulsaciones.

Para evitar este aumento incorrecto del número de pulsaciones, Adobe recomienda usar el complemento [!UICONTROL getValOnce] para forzar que cada pulsación de la campaña se cuente solo una vez. Para obtener más información sobre el complemento [!UICONTROL getValOnce], consulte [Complementos de implementación](/help/implement/js-implementation/plugins/impl-plugins.md).

**Sintaxis y valores posibles** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

La variable *`campaign`* tiene las mismas limitaciones que todas las demás variables. Adobe recomienda limitar el valor a los caracteres ASCII estándar.

**Distinción entre mayúsculas y minúsculas** {#section_112A9A0F886148B6BEF9A7C94BE0A36F}

Las eVars no distinguen entre mayúsculas y minúsculas, pero se muestran en la escritura en mayúsculas de la primera aparición. Por ejemplo, si la primera instancia de eVar1 es "Sesión iniciada" pero todas las demás instancias se pasan como "sesión iniciada", los informes siempre mostrarán "Sesión iniciada" como valor de eVar.

**Ejemplos** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**Parámetros de configuración** {#section_4083F281968443169EAF8C0E8529D7BC}

Cada valor de campaign permanece activo para un usuario y recibe el crédito por las actividades y los eventos de éxito de dicho usuario hasta que caduque. La caducidad de la variable campaign se modifica en Admin Console.

**Problemas, preguntas y consejos** {#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* Para evitar aumentar incorrectamente el número de pulsaciones, use el complemento [!UICONTROL getValOnce] para que las pulsaciones de una campaña se cuenten solo una vez por sesión. Para obtener más información sobre el complemento [!UICONTROL getValOnce], consulte [Complementos de implementación](/help/implement/js-implementation/plugins/impl-plugins.md).

* Para obtener más información sobre el seguimiento de campañas de marketing y las compras por palabras clave, consulte [Campañas](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html).
* Use [!DNL DigitalPulse Debugger] para ver el valor real de las campañas (v0 en el depurador). Si v0 no aparece en el depurador, no se han registrado datos de la campaña para esa página.
