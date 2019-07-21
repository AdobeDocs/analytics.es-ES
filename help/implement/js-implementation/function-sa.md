---
description: 'La función s.sa() permite cambiar en cualquier momento y de forma dinámica un grupo de informes en la página, antes o después de que la solicitud de imagen se active. '
keywords: Implementación de Analytics
seo-description: 'La función s.sa() permite cambiar en cualquier momento y de forma dinámica un grupo de informes en la página, antes o después de que la solicitud de imagen se active. '
seo-title: La función s.sa()
solution: Analytics
subtopic: Funciones
title: Función s.sa()
topic: Desarrollador e implementación
uuid: a 6 aacd 10-2 a 5 b -448 b-b 3 b 7-bed 5590 b 71 d 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Función s.sa()

La función s.sa() permite cambiar en cualquier momento y de forma dinámica un grupo de informes en la página, antes o después de que la solicitud de imagen se active. 

Si su organización desea enviar datos a otros grupos de informes sin una recarga de página, es muy recomendable utilizar esta función.

Esta información está dirigida a usuarios avanzados con amplia experiencia tanto en informes como en implementación. No intente realizar ningún cambio en la implementación sin tener absoluto conocimiento de las consecuencias. Si necesita modificar la implementación, póngase en contacto con el administrador de cuentas de su organización. 

## Propiedades de la función {#section_E10CB41A0CF749F4A24C8377958E3671}

La configuración de esta función toma todas las variables previamente definidas y permite utilizarlas en otro grupo de informes.

## Ejemplos de implementación {#section_14B0B8C853244D5F82B08B995773640C}

Envío de datos de vídeo a un grupo de informes mientras se envía el resto a otro grupo:

```js
// Set in the core JS file by default 
var s=s_gi('prodrsid'); 
 
// Define this when a user interacts with a video 
s.sa('videorsid'); 
s.t(); // Sends an image request
```

Uso del etiquetado de grupos múltiples y s.sa():

```js
// Set in the core JS file by default 
var s=s_gi('rsid1'); 
 
// Call the function when you wish to change report suites 
s.sa('rsid1,rsid2'); 
s.t();
```

