---
title: Tráfico interno
description: El complemento Internal Traffic identifica de forma dinámica a los visitantes que proceden de una red interna.
seo-description: Complemento interno de tráfico
seo-title: Complemento interno de tráfico
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Tráfico interno

El complemento Internal Traffic identifica de forma dinámica a los visitantes que proceden de una red interna.

La identificación del tráfico interno y externo promueve una mayor precisión en todos los tipos de informes, ya que proporciona un mecanismo que filtra y segmenta los datos que se están recopilando. Se implementó correctamente, también se eliminaría la necesidad de una regla de VISTA o de una regla de procesamiento que son enfoques típicos para identificar dicho tráfico.

## ¿Cómo funciona el complemento de tráfico interno?

El complemento intenta cargar un archivo que solo estaría disponible en su red interna/intranet, es decir, un píxel transparente de 1 x 1. Si se carga correctamente, el tráfico para ese visitante será identificado como interno. Todo lo demás sería tráfico externo.

## Consideraciones

* La única desventaja en este método es que se muestra un error 404 en la consola del explorador para visitantes externos en la primera página de su visita. Esto no afectará a la experiencia del usuario.
* Recomendamos enfáticamente que obtenga la aprobación del equipo de red o infosec antes de intentar cargar un píxel alojado internamente.
* Aunque el complemento no moverá tráfico a otro grupo de informes ni lo excluirá de los informes (como se puede hacer con una regla de VISTA), la lógica personalizada se puede incluir en su implementación, de modo que esta funcionalidad pueda llevarse a cabo en el cliente.

## Implementación

1. Agregue el píxel Intranet: Puede agregar cualquier tipo de archivo en la intranet a la que intentaría acceder el complemento. Se recomienda un píxel transparente de 1 x 1. Debe colocarse en una ubicación en la Intranet a la que se pueda acceder desde la red interna.
1. Configurar una evar: Es necesario agregar una evar dentro del grupo de informes de destino. Debe tener una caducidad de «Visita» y asignación de «Valor original (primero)».
1. Definir la dirección URL interna: Dentro de las variables de configuración de appmeasurement y antes de crear doplugins, defina la variable URL interna (s. inturl) para el píxel u otro archivo para la comprobación de tráfico. Por ejemplo: `s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modify doPlugins and set the eVar: The plugin can then be initialized by including this line of code within the doPlugins section of your AppMeasurement library code, using the eVar defined in step one: `s.eVarXX = s.intCheck();`
The variable value will be set to “internal” or “external”.
1. Agregar el código fuente de complemento: Incluya el código de complemento debajo de la sección doplugins del archivo appmeasurement.

## Código fuente del complemento

Agregue este código debajo de la sección doplugins de la biblioteca appmeasurement.

```s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");```

## Other Notes

* Always test plug-in installations to ensure that data collection happens as expected before deploying them in a production environment.
* Your implementation might be using a different object name than the default Adobe Analytics "s" object. If so, please update the object name accordingly.
* If you employ a Tag Management System, please follow its steps to update doPlugins and the other custom plugins.

