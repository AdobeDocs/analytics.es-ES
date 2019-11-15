---
title: Tráfico interno
description: El complemento Tráfico interno identifica dinámicamente a los visitantes que provienen de una red interna.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Tráfico interno

El complemento Tráfico interno identifica dinámicamente a los visitantes que provienen de una red interna.

La identificación del tráfico interno y externo promueve una mayor precisión en todos los tipos de informes, al proporcionar un mecanismo que filtra y segmenta los datos que se recopilan. Si se implementa correctamente, también se eliminaría la necesidad de una regla de VISTA o de una regla de procesamiento que sean enfoques típicos para identificar dicho tráfico.

## ¿Cómo funciona el complemento Tráfico interno?

El complemento intenta cargar un archivo que solo estaría disponible en la red interna/intranet, es decir, un píxel transparente 1x1. Si se carga correctamente, el tráfico de ese visitante se identificará como interno. Cualquier otra cosa sería tráfico externo.

## Consideraciones

* El único inconveniente de este enfoque es que se muestra un error 404 en la consola del explorador para los visitantes externos en la primera página de la visita. Esto no afectará a la experiencia del usuario.
* Le recomendamos encarecidamente que obtenga la aprobación de su equipo de Red o InfoSec antes de intentar cargar un píxel alojado internamente.
* Aunque el complemento no moverá el tráfico a otro grupo de informes ni lo excluirá de los informes (como podría hacerse con una regla de VISTA), la lógica personalizada se puede incluir en su implementación, de modo que esta funcionalidad pueda tener lugar en el lado del cliente.

## Implementación

1. Agregue el píxel de intranet: Puede agregar cualquier tipo de archivo en la intranet al que intente acceder el complemento. Se recomienda un píxel transparente 1x1. Debe colocarse en una ubicación de su Intranet a la que se pueda acceder fácilmente desde sus redes internas.
1. Configurar una eVar: Será necesario agregar una eVar dentro del grupo de informes de destino. Debe tener una caducidad de "Visita" y la asignación de "Valor original (primero)".
1. Defina la dirección URL interna: Dentro de las variables de configuración de AppMeasurement y antes de crear una instancia de doPlugins, defina la variable de URL interna (s.intURL) para el píxel o utilice otro archivo para la comprobación de tráfico. Por ejemplo: `s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modify doPlugins and set the eVar: The plugin can then be initialized by including this line of code within the doPlugins section of your AppMeasurement library code, using the eVar defined in step one: `s.eVarXX = s.intCheck();`
The variable value will be set to "internal" or "external".
1. Agregar el código fuente del complemento: Incluya el código de complemento debajo de la sección doPlugins del archivo AppMeasurement.

## Código fuente del complemento

Agregue este código debajo de la sección doPlugins de la biblioteca de AppMeasurement.

```JavaScript
s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");
```

## Otras notas

* Antes de su implementación en un entorno de desarrollo, realice pruebas de las instalaciones de complementos para asegurarse de que la recopilación de datos se comporta según lo esperado.
* Su implementación podría utilizar un nombre de objeto distinto del objeto “s” predeterminado de Adobe Analytics. De ser así, actualice en consonancia el nombre del objeto.
* Si utiliza un sistema de Tag Management, siga sus pasos para actualizar doPlugins y los demás complementos personalizados.
