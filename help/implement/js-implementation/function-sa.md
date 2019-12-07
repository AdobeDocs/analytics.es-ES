---
description: La función s.sa() permite cambiar en cualquier momento y de forma dinámica un grupo de informes en la página, antes o después de que la solicitud de imagen se active.
keywords: Analytics Implementation
subtopic: Functions
title: Función s.sa()
topic: Developer and implementation
uuid: a6aacd10-2a5b-448b-b3b7-bed5590b71d4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

