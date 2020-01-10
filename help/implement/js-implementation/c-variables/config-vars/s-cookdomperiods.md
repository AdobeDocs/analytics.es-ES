---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieDomainPeriods

La variable determina el dominio donde se configuran las cookies de [!DNL Analytics] `s_cc` y `s_sq`; para ello, determine el número de puntos en la dirección URL de la página. Algunos complementos también usan esta variable para determinar el dominio correcto donde se configurará la cookie del complemento.

El valor predeterminado para *`cookieDomainPeriods`* es “2”. Este es el valor que se usa si se omite *`cookieDomainPeriods`*. Por ejemplo, si utiliza el dominio `www.mysite.com`, *`cookieDomainPeriods`* debe ser “2”. Para `www.mysite.co.jp`, *`cookieDomainPeriods`* debe ser “3”.

Si *`cookieDomainPeriods`* es “2” pero el dominio contiene tres puntos, el archivo JavaScript intenta configurar las cookies en el sufijo del dominio.

Por ejemplo, si se configura *`cookieDomainPeriods`* en “2” en el dominio `www.mysite.co.jp`, las cookies `s_cc` y `s_sq` se crean en el dominio `co.jp`. Como `co.jp` no es un dominio válido, casi todos los exploradores rechazan estas cookies. Como consecuencia, se pierden los datos del mapa de clics de visitantes y el informe [!UICONTROL Perfil del visitante] &gt; [!UICONTROL Tecnología] &gt; [!UICONTROL Cookies] indica que casi el 100 % de los visitantes rechazan las cookies.

Si *`cookieDomainPeriods`* se establece en "3" pero el dominio solo contiene dos puntos, el archivo JavaScript establece las cookies en el subdominio del sitio. Por ejemplo, si se configura *`cookieDomainPeriods`* en “3” en el dominio `www2.mysite.com`, las cookies `s_cc` y `s_sq` se crean en el dominio `www2.mysite.com`. Cuando un visitante va a otro subdominio del sitio (por ejemplo, `www4.mysite.com`), no se pueden leer todas las cookies configuradas con `www2.mysite.com`.

> [!NOTE] No incluya más subdominios como parte de *`cookieDomainPeriods`*. Por ejemplo, `store.toys.mysite.com` seguiría configurándose con *`cookieDomainPeriods`* en “2”. Esta definición de variable configura correctamente las cookies en el dominio raíz, [!DNL mysite.com]. Si se establece *`cookieDomainPeriods`* como “3” en este ejemplo, las cookies se configurarían en el dominio [!DNL toys.mysite.com], que tiene las mismas implicaciones que en el ejemplo anterior.

Consulte también [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/es-ES/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html).

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N/A | CDP | Afecta a varios informes ya que controla el modo de almacenamiento y gestión de la ID de visitante. | "2" |

>[!NOTE]
>
>Algunos servicios de computación en la nube se consideran dominios de nivel superior, que no permiten la escritura de cookies. (Por ejemplo, `*.googlecode.com`, `compute.amazonaws.com`, `*.herokuapp.com`, etc.). Si implementa en esos servicios, podría verse afectado por la configuración de privacidad de Analytics que elimina a los usuarios que han bloqueado todas las cookies si no cuenta con su propio dominio configurado (por ejemplo, si está probando la implementación). En este caso, cualquier visita para la que el sistema haya determinado que las cookies están deshabilitadas, no son funcionales o no son accesibles queda fuera y se excluye de los informes.

## Ejemplos

Configuración manual de la variable:

```js
s.cookieDomainPeriods = "3";
```

Algunos ejemplos para configurar dinámicamente la variable si su archivo JavaScript principal aloja ambos tipos:

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

## Problemas, preguntas y consejos

* Si nota que faltan los datos del mapa de clics de visitantes o que el informe [!UICONTROL Tráfico] &gt; [!UICONTROL Tecnología] &gt; [!UICONTROL Cookies] muestra un gran porcentaje de visitantes que rechaza las cookies, compruebe que el valor de *`cookieDomainPeriods`* es correcto.

* Si el valor de *`cookieDomainPeriods`* es mayor que el número de secciones del dominio, las cookies se configurarán en el dominio completo. Esto puede provocar la pérdida de datos cuando los visitantes cambien de un subdominio a otro.
* La variable *`cookieDomainPeriods`* se utilizó en implementaciones obsoletas antes de *`trackingServer`* para configurar la cookie de ID de visitante. Aunque solo está presente en código anticuado, si no se define correctamente *`cookieDomainPeriods`* en esta circunstancia, su implementación corre el riesgo de perder datos.
