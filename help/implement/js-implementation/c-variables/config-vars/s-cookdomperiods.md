---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.cookieDomainPeriods

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. Algunos complementos también usan esta variable para determinar el dominio correcto donde se configurará la cookie del complemento.

The default value for  is "2". *`cookieDomainPeriods`* This is the value that is used if *`cookieDomainPeriods`* is omitted. Por ejemplo, si utiliza el dominio `www.mysite.com`, *`cookieDomainPeriods`* debe ser "2". For ,  should be "3".`www.mysite.co.jp`*`cookieDomainPeriods`*

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

For example, if setting  to "2" on the domain , the  and  cookies are created on the domain . *`cookieDomainPeriods`*`www.mysite.co.jp``s_cc``s_sq``co.jp` Como `co.jp` no es un dominio válido, casi todos los exploradores rechazan estas cookies. Como consecuencia, se pierden los datos del mapa de clics de visitantes y el informe [!UICONTROL Perfil del visitante] &gt; [!UICONTROL Tecnología] &gt; [!UICONTROL Cookies] indica que casi el 100 % de los visitantes rechazan las cookies.

Si *`cookieDomainPeriods`* se establece en "3" pero el dominio solo contiene dos puntos, el archivo JavaScript establece las cookies en el subdominio del sitio. For example, if setting  to "3" on the domain , the  and  cookies are created on the domain . *`cookieDomainPeriods`*`www2.mysite.com``s_cc``s_sq``www2.mysite.com` When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. For example,  would still have  set to "2". `store.toys.mysite.com`*`cookieDomainPeriods`* Esta definición de variable configura correctamente las cookies en el dominio raíz, [!DNL mysite.com]. Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

See also s.fpCookieDomainPeriods.[](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | CDP | Afecta a varios informes ya que controla el modo de almacenamiento y gestión de la ID de visitante.  | "2" |

>[!NOTE]
>
>Algunos servicios informáticos en la nube se consideran dominios de nivel superior, que no permiten que se escriban cookies. (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) Si implementa en esos servicios, podría verse afectado por la configuración de privacidad de Analytics que elimina a los usuarios que han bloqueado todas las cookies si no cuenta con su propio dominio configurado (por ejemplo, si está probando la implementación). En este caso, cualquier visita para la que el sistema haya determinado que las cookies están deshabilitadas, no son funcionales o no son accesibles queda fuera y se excluye de los informes.

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

* Si nota que faltan los datos del mapa de clics de visitantes o que el informe [!UICONTROL Tráfico] &gt; [!UICONTROL Tecnología] &gt; [!UICONTROL Cookies] muestra un gran porcentaje de visitantes que rechaza las cookies, compruebe que el valor de *`cookieDomainPeriods`* sea correcto.

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. Esto puede provocar la pérdida de datos cuando los visitantes cambien de un subdominio a otro.
* La variable *`cookieDomainPeriods`* variable was used in deprecated implementations prior to *`trackingServer`* to set the visitor ID cookie. Though only present in outdated code, failure to correctly define  in this circumstance puts your implementation at risk of data loss.*`cookieDomainPeriods`*