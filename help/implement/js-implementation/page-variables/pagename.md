---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# pageName

La variable contiene el nombre de cada una de las páginas del sitio.


<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
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
   <td> 100 bytes </td> 
   <td> pageName </td> 
   <td> <p>Páginas </p> <p>Rutas </p> </td> 
   <td> URL de la página </td> 
  </tr> 
 </tbody> 
</table>

La variable *`pageName`* debe rellenarse con un valor que los usuarios comerciales reconozcan. En la mayoría de los casos, el valor *`pageName`* no es la dirección URL ni la ruta al archivo. Los valores habituales de *`pageName`* suelen ser “Página de inicio”, “Cierre de compra”, “Gracias por su compra” o “Registro”.

Tenga cuidado de que no aparezcan caracteres de nueva línea, guiones -em o -en u otros caracteres HTML en el nombre de la página y otras variables. Algunos exploradores envían caracteres de nueva línea pero otros no, lo que hace que los datos de Analytics se dividan en dos nombres de página aparentemente iguales. Muchos procesadores de texto y clientes de correo electrónico convertirán automáticamente un guión corto en un guión -en o -em al escribir. Como los guiones -en y -em son caracteres no permitidos en las variables de Analytics (caracteres ASCII con códigos superiores a 127), Analytics no registrará los nombres de página que contengan caracteres no permitidos y, en su lugar, mostrará la dirección URL.

Si *`pageName`* se deja en blanco, se usa la dirección URL para representar el nombre de página. Dejar *`pageName`* en blanco suele causar problemas porque la dirección URL podría no ser siempre la misma para una página (`www.mysite.com` y `mysite.com` son la misma página con direcciones URL diferentes).

**Sintaxis y valores posibles** {#section_7A61EE70F1A84D26B414404998C84BA8}

La variable *`pageName`* debe contener un identificador útil para los usuarios comerciales de Analytics.

```js
s.pageName="page_name"
```

No existen limitaciones de *`pageName`* además de las limitaciones estándar de las variables.

**Ejemplos** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**Parámetros de configuración** {#section_58CBC68C805344A999EB47455FEBA8D5}

Los administradores tienen la posibilidad de cambiar el nombre de página visible en Analytics con la [!UICONTROL Herramienta de asignación de nombres a páginas], lo que resulta potencialmente peligroso y podría afectar negativamente a los informes. Póngase en contacto con el Servicio de atención al cliente de Adobe antes de usar la herramienta [!UICONTROL Nombrar páginas].

**Problemas, preguntas y consejos** {#section_BB41DC9682C34385B9CAA80D5257C113}

Asegúrese de que *`pageName`* no contenga caracteres ilegales.
