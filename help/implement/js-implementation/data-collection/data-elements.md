---
description: Puede capturar en los informes los valores de elementos de formularios tales como botones de opción y casillas de verificación. Esto ayuda a analizar las opciones más seleccionadas en los formularios en línea.
keywords: Implementación de Analytics
seo-description: Puede capturar en los informes los valores de elementos de formularios tales como botones de opción y casillas de verificación. Esto ayuda a analizar las opciones más seleccionadas en los formularios en línea.
seo-title: Recopilación de datos de elementos de formulario
solution: Analytics
title: Recopilación de datos de elementos de formulario
topic: Desarrollador e implementación
uuid: e 0 c 13 b 96-e 1 ca -4744-a 912-60 ca 2 b 8 f 25 c 3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Recopilación de datos de elementos de formulario

Puede capturar en los informes los valores de elementos de formularios tales como botones de opción y casillas de verificación. Esto ayuda a analizar las opciones más seleccionadas en los formularios en línea.

Por ejemplo, si dispone de un botón de opción que permite al usuario especificar un género musical favorito (por ejemplo, rock, rap, clásica o jazz), podrá capturar esta respuesta en una variable para así determinar las preferencias musicales generales de sus usuarios.

La mejor manera para capturar estos datos depende del modo en que se procesan los formularios. También depende de si las selecciones de formularios que se deseen capturar están disponibles en la cadena de consulta de la página que sigue al envío del formulario. Los ejemplos de este artículo están en PHP. No obstante, se pueden adaptar estos conceptos a otro lenguaje en función de su entorno de servidor. 

Esta información está dirigida a usuarios avanzados con amplia experiencia tanto en informes como en implementación. No intente realizar ningún cambio en la implementación sin tener absoluto conocimiento de las consecuencias. Si necesita modificar la implementación, póngase en contacto con el administrador de cuentas de su organización. 

## Método GET {#section_7A2B35822BFF4F6EB57940B31AE6303A}

Si su formulario utiliza un método [!UICONTROL GET] para enviar datos, tiene acceso a los datos deseados en la cadena de consulta de la URL en la página que sigue al envío del formulario. Puede usar el complemento [!UICONTROL getQueryParam] para capturar automáticamente estos datos desde la cadena de consulta y colocarlos en la variable que usted elija.

## Método POST {#section_56715C30EF374BA7AA12B946B50E4A9A}

Si su formulario utiliza un método [!UICONTROL POST] para enviar datos (opción más común), los resultados de cada elemento de formulario específico están disponibles en la variable [!UICONTROL $_POST superglobal]. Para capturarlos en una variable, determine el nombre del elemento de formulario en cuestión. Si se utiliza el ejemplo de género musical mencionado anteriormente, parte del elemento de formulario en cuestión sería así: 

```
<input type="radio" name="music_genre" value="rock">
```

Este botón de opción pertenece al elemento de formulario "music_genre". You then have access to the user's selected value by using $_POST['music_genre']. Esto se podría escribir en una variable en la página que sigue al envío del formulario:

```js
s.eVar1="<?=$_POST['music_genre'];?>"
```

La variable [!UICONTROL eVar1] recibe una copia de cualquier valor que se haya enviado al servidor a través del formulario, tal como se especifica en la propiedad value=.

Si necesita información adicional relativa a este método de implementación personalizado, póngase en contacto con el administrador de cuentas de su organización. Él puede concertar una reunión con uno de nuestros consultores de implementación para proporcionarle la ayuda que necesite.
