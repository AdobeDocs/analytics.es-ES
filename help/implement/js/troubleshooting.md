---
title: Solución de problemas de implementación de JavaScript
description: Obtenga más información sobre problemas comunes y prácticas recomendadas para solucionar problemas de la implementación de JavaScript.
translation-type: ht
source-git-commit: 8aa6932dcbb6dad88c27ba1cd4f5aad3bafcfc52

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
