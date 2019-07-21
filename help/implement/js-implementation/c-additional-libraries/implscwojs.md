---
description: Implemente Analytics con una etiqueta de imagen HTML (solicitud de imagen codificada).
keywords: Implementación de Analytics; HTML image tag; solicitud de imagen codificada
seo-description: Implemente Analytics con una etiqueta de imagen HTML (solicitud de imagen codificada).
seo-title: Implementar Analytics con etiquetas de imagen HTML
solution: Analytics
title: Implementar Analytics con etiquetas de imagen HTML
topic: Desarrollador e implementación
uuid: 0 c 098 a 57-7 c 71-4362-812 c -36 e 37848 a 5 ae
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Implementar Analytics con etiquetas de imagen HTML

Implemente Analytics con una etiqueta de imagen HTML (solicitud de imagen codificada).

A continuación, el explorador solicita la imagen. Los datos se mueven con esta solicitud de imagen mediante variables en la cadena de consulta de la solicitud de imagen. JavaScript combina variables de explorador con variables de page para obtener una solución de recopilación de datos completa. En algunos casos resulta apropiada una etiqueta de imagen creada completamente por el servidor. Los elementos estándar de una implementación basada en JavaScript son los siguientes:

<table id="table_20BBE4387F234CF199E6C99741AF265C"> 
 <tbody> 
  <tr> 
   <td> Código HTML </td> 
   <td> Esta parte consta del código JavaScript que se sitúa en las páginas (o plantillas) HTML y que configura el valor de las variables de JavaScript. </td> 
  </tr> 
  <tr> 
   <td> Biblioteca JavaScript </td> 
   <td> <p>Este archivo contiene código común que: </p> 
    <ul id="ul_ED50D66F2B2B476E8D9063099995998D"> 
     <li id="li_E88F6F28EC8946469ADCEAFF2F0A4EBA">Consulta al explorador acerca de varias propiedades, como la versión de JavaScript, la versión del SO, el tamaño y la resolución del monitor que se está usando, y otras variables </li> 
     <li id="li_5CEBE37709D943B7921447FA7054A565">Codifica y concatena todas las variables en una solicitud de imagen (&lt;img&gt;) que transporta estas variables a los servidores de recopilación de datos. Después, hace referencia a un archivo de biblioteca JavaScript que se carga y se ejecuta. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta &lt;noscript&gt; </td> 
   <td> Se coloca una versión simplificada de la solicitud de imagen en una etiqueta &lt;noscript&gt; que se ejecuta si el usuario ha deshabilitado JavaScript o no tiene funcionalidades de JavaScript. Esta parte de la implementación es opcional y generalmente se aplica a un 2 % de la población de Internet. </td> 
  </tr> 
 </tbody> 
</table>

JavaScript puede detectar opciones de configuración del explorador que no están disponibles para un servidor, por ejemplo, la altura y anchura de la ventana del explorador, la resolución de pantalla y los complementos de Netscape. Si se usa un método del lado del servidor para crear una etiqueta de imagen, estas variables no se pueden capturar. JavaScript establece un número aleatorio en la solicitud de imagen para omitir el almacenamiento en caché del explorador y el servidor proxy. Esto permite realizar el seguimiento de todas las vistas de página de forma precisa. En algunos casos, el código del lado del servidor tiene ventajas sobre el código basado en JavaScript, entre ellas:

* JavaScript es muy preciso (98-100 %). Hay ocasiones en las que se desea la máxima precisión, incluso en situaciones en las que un usuario hace clic rápidamente a otra página antes de que JavaScript se haya ejecutado. Crear la etiqueta de imagen en el lado del servidor aumenta varios puntos el porcentaje de precisión.
* Para rastrear eventos de conversión (como las compras) en los que la precisión es fundamental.
* Esta estrategia también puede utilizarse para rellenar completamente la solicitud de imagen dentro de la variable <noscript> para rastrear usuarios sin JavaScript o con JavaScript deshabilitado.

>[!NOTE]
>
>El uso de etiquetas de imagen generadas por servidor requiere de tiempo adicional para implementarse y es más difícil de depurar, implementar y mantener. Adobe recomienda encarecidamente a sus clientes usar la recopilación de datos basada en JavaScript en todas las páginas siempre que sea posible. Hay varios informes y funciones, incluidos el mapa de clics de visitantes, vínculos de descarga, vínculos de salida y variables de explorador (alto y ancho del explorador, etc.) que no se pueden recopilar o no se admiten con este método de implementación.

