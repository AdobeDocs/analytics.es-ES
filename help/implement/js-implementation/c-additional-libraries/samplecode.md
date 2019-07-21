---
description: Ejemplos que ilustran el uso de una etiqueta de imagen generada por el servidor en una página de muestra HTML.
keywords: Implementación de Analytics; variables
seo-description: Ejemplos que ilustran el uso de una etiqueta de imagen generada por el servidor en una página de muestra HTML.
seo-title: Código de muestra
solution: Analytics
title: Código de muestra
topic: Desarrollador e implementación
uuid: 47 e 5 e 82 c-cfb 2-4912-919 b -720 b 2 ee 852 ba
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Código de muestra

Ejemplos que ilustran el uso de una etiqueta de imagen generada por el servidor en una página de muestra HTML.

La tabla siguiente muestra los valores utilizados en el ejemplo.

| Variable | Valor |
|---|---|
| pageName | Confirmación de pedido |
| Dirección URL actual | https://www.somesite.com/cart/confirmation.asp |
| events | purchase,event1 |
| c1 | Registrado |
| purchaseID | 0123456 |
| products | Books;Book Name;1;19.95 |
| state | CA |
| zip | 90210 |
| un número aleatorio | 123456 |

## Ejemplo 1 {#section_91D91CE318AE43F0ADDF6005607E83C7}

El ejemplo siguiente muestra una etiqueta de imagen del lado del servidor. El número aleatorio resaltado impide que la imagen se almacene en caché.

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456. 
<img src="https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS 
<codeph outputclass="syntax">
  /123456?pageName=Order%20 Confirmation&events=purchase%2Cevent1&c1=Registered&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=https%3A//www.somesite.com/cart/confirmation.asp" width="1" height="1" border="0" /> 
 </body> 
 </html> 
  
</codeph outputclass="syntax">
```

## Ejemplo 2 {#section_726D12029583428BA853043F988ED1B8}

El ejemplo siguiente muestra una etiqueta de imagen JavaScript mínima.

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456. 
<script language="javascript"><!— 
s.s_date = new Date(); 
s.s_rdm = s.s_date.getTime(); 
s.s_desturl="<img width=\"1\" height=\"1\" 
src=\"https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS/" + s.s_rdm + 
"?pageName=Order%20Confirmation&events=purchase%2Cevent1&c1=Registered 
&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=http 
s%3A//www.somesite.com/cart/confirmation.asp\">"; 
document.write(s.s_desturl); 
//--></script> 
</body> 
</html> 
```

