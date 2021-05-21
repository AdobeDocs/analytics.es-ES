---
title: Solución de problemas de implementación de JavaScript
description: Obtenga más información sobre problemas comunes y prácticas recomendadas para solucionar problemas de la implementación de JavaScript.
exl-id: e7181e78-65bf-446d-8d5c-b47323dbec1d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '694'
ht-degree: 100%

---

# Solución de problemas de implementación de JavaScript

A continuación se indican varias razones por las que su empresa podría tener problemas para obtener datos correctamente en Adobe Analytics.

## Uso de comillas

La mayoría de las variables enviadas a Adobe son cadenas. En JavaScript, puede utilizar comillas simples o dobles.

### Combinación de comillas para definir una variable

Le recomendamos que compruebe que es coherente con los tipos de comillas que utiliza. Si una comilla simple designa el inicio de una cadena, debe utilizarse una comilla simple para cerrarla.

Por ejemplo, tanto `s.eVar1 = 'Value'` como `s.eVar1 = "Value"` son ejemplos válidos. En cambio, `s.eVar1 = 'Value"` no es válido.

### Inclusión de comillas simples o dobles en una cadena

A veces, queremos incluir una comilla simple o doble en una cadena. Por ejemplo: Quiere incluir el valor `Alex's sale` o `John the "Hunter"` en los informes. Existen dos métodos para incluir estos valores:

* **Utilice el otro tipo de comillas**: Por ejemplo, `s.eVar1 = "Alex's sale"` y `s.eVar1 = 'John the "Hunter"'` son ejemplos válidos.
* **Omisión de las comillas**: Utilice una barra invertida para omitir las comillas. `s.eVar1 = 'Alex\'s sale'` y `s.eVar1 = "John the \"Hunter\""` son dos ejemplos válidos.

### Evitar el uso de comillas curvas

Algunos programas convierten automáticamente las comillas neutras (`"..."` y `'...'`) en comillas curvas (`“...”` y `‘...’`). Evite utilizar editores de documentos (como Microsoft Word) o transferir fragmentos de código por correo electrónico. Las comillas curvas no se pueden usar en JavaScript.

## Referencia al objeto Analytics

Todas las variables enviadas a Adobe utilizan el objeto Analytics. La mayoría de las implementaciones utilizan el objeto `s`. Compruebe que, al hacer referencia a variables, incluye el objeto de Analytics en la referencia.

Por ejemplo, `s.eVar1 = 'Value'` es válido, mientras que `eVar1 = 'Value'` no lo es.

## Defina cada variable una vez

Cuando se ejecuta una función de seguimiento (`s.t()`), AppMeasurement toma todas las variables definidas y las compila en una solicitud de imagen. Si define una variable más de una vez en la implementación, solo se utilizará el valor más reciente. Compruebe que todos los valores de las variables contengan el valor correcto cuando se ejecute la función de seguimiento.

## Corrección del uso de mayúsculas y minúsculas en las variables

Algunas variables utilizan letras mayúsculas. Las variables JavaScript distinguen entre mayúsculas y minúsculas. Compruebe que utiliza las mayúsculas y minúsculas correctas al definir variables. Por ejemplo, `s.eVar1 = 'Value'` es válido, mientras que `s.evar1 = 'Value'` no lo es.

## Complementos

Algunas empresas utilizan complementos para mejorar su implementación de Adobe Analytics. Al actualizar las versiones de AppMeasurement, no olvide volver a incluir los complementos instalados. El código creado en el [!UICONTROL Administrador de códigos] no contiene ningún código del complemento. Realice una copia del código existente en caso de que necesite volver a una versión anterior de AppMeasurement.

## Espacios en blanco en valores de variable

En HTML, hay varios caracteres que crean un espacio en blanco. Estos son un espacio, una tabulación y un retorno de carro (o inserción de línea). Consideremos el siguiente ejemplo:

```html
<head>
  <title>
    Home Page
  </title>
</head>
<body>
<script language="javascript">
  s.pageName = document.title;
</script>
</body>
```

En este caso, `document.title` rellena `s.pageName`, que debería recibir el valor &quot;Home Page&quot;. Sin embargo, algunos exploradores pueden interpretar el espacio en blanco de forma diferente. El resultado puede ser uno de los dos ejemplos siguientes:

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

Estos dos valores de variable se consideran independientes en Adobe Analytics. Sin embargo, el espacio en blanco se elimina automáticamente con fines de visualización. El resultado es un informe que muestra dos elementos de línea &quot;Página principal&quot; aparentemente idénticos. Compruebe que los valores de las variables no contengan espacios en blanco antes o después del valor deseado.

## Solicitudes de imagen truncadas

Las implementaciones que rellenan muchas variables con valores largos a veces se pueden ejecutar en solicitudes de imagen truncadas. Algunos exploradores más antiguos, como Internet Explorer, imponen un límite de 2083 caracteres en las direcciones URL de solicitudes de imágenes. Si su organización se enfrenta a solicitudes de imagen muy largas, intente lo siguiente:

* **Utilice el servicio de Experience Cloud ID**: Las bibliotecas de AppMeasurement 1.4.1 y posteriores envían automáticamente solicitudes de imagen mediante el POST HTTP si son demasiado largas. Los datos enviados mediante este método no se truncan independientemente de la longitud. Consulte [Servicio de Adobe Experience Cloud ID](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html) para obtener más información.
* **Usar reglas de procesamiento**: Las [reglas de procesamiento](/help/admin/admin/c-processing-rules/processing-rules.md) pueden copiar valores de una variable a otra. Este método evita que se establezca el mismo valor en varias variables. Por ejemplo:

   Ejecute siempre:<br>
Sobrescribir el valor de prop1 con eVar1<br>
Sobrescribir el valor de eVar2 con eVar1<br>
Sobrescribir el valor de prop2 con eVar1<br>

   Luego establezca eVar1 en la implementación:

   ```js
   s.eVar1 = "The quick brown fox jumps over the lazy dog";
   ```

* **Utilice variables dinámicas**: Si la implementación rellena muchas variables con el mismo valor, puede utilizar [variables dinámicas](/help/implement/vars/page-vars/dynamic-variables.md) para acortar la dirección URL de la solicitud:

   ```js
   s.eVar1 = "The quick brown fox jumps over the lazy dog";
   s.eVar2 = "D=v1";
   s.prop1 = "D=v1";
   s.prop2 = "D=v1";
   ```

* **Use clasificaciones**: Si los nombres de producto o de página son inusualmente largos, puede utilizar un código o valor de identificación y, a continuación, utilizar las [clasificaciones](/help/components/classifications/c-classifications.md) para mostrar un nombre más descriptivo.
