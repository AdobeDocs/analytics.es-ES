---
description: La función s.t() es la que compila todas las variables definidas en esa página en una solicitud de imagen, y la envía a nuestros servidores.
keywords: track; Implementación de Analytics; seguimiento de páginas; rastrear página
seo-description: La función s.t() es la que compila todas las variables definidas en esa página en una solicitud de imagen, y la envía a nuestros servidores.
seo-title: Función s.t() - Seguimiento de páginas
solution: Analytics
subtopic: Funciones
title: Función s.t() - Seguimiento de páginas
topic: Desarrollador e implementación
uuid: 67696 e 46-1 e 0 d -4200-bfad -4217 d 1023948
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Función s.t() - Seguimiento de páginas

La función s.t() es la que compila todas las variables definidas en esa página en una solicitud de imagen, y la envía a nuestros servidores.

## Propiedades de la función {#section_DB1F3E216DCD4E12AE42BBDCD25B9626}

* Si se elimina la llamada a [!UICONTROL s.t()], los datos no llegarán a [!DNL Analytics]. Varias llamadas a [!UICONTROL s.t()] activan varias solicitudes de imagen (y duplican el tráfico registrado en el sitio).

* Si desea activar más de una solicitud de imagen en una única carga de página, se recomienda usar la función [!UICONTROL s.tl()].
* Activar esta función siempre aumenta las [!UICONTROL vistas de página] y siempre incluye la variable [!UICONTROL s.pageName].

## Implementación {#section_F75C7BD4A8954CD5BE066C6B88A4A01C}

Al generar código en el [!UICONTROL Administrador de códigos], en la parte inferior del código de página se facilita lo siguiente:

```js
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" /></noscript> 
```

Cada línea de código tiene una finalidad específica:

```js
var s_code=s.t();if(s_code)document.write(s_code)//-->
```

Esta línea de código es lo que realmente activa la función JavaScript. La variable [!UICONTROL s_code] y el método document.write que la acompaña es para exploradores que no admiten objetos de imagen (exploradores de Netscape anteriores a la versión 3 e Internet Explorer anterior a la versión 4; se estima que esto supone menos del 0,5 % de todos los usuarios de Internet).

```js
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img  
src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" />
```

Para cualquier otra pregunta sobre la función [!UICONTROL s.t()], póngase en contacto con el Administrador de cuentas de su organización. Él puede concertar una reunión con un consultor de implementación de Adobe para que le facilite asistencia.
