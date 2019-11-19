---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: edf88e40cae8b6886b04257f266666c13a37f88d

---


# eVarN

Las variables [!UICONTROL eVar] se usan para generar informes personalizados.

<!-- 

eVarN.xml

 -->

Cuando se establece un valor en una eVar para un visitante, el valor se recuerda hasta que caduca. Cualquier evento de éxito que encuentra el visitante mientras la eVar está activa se cuenta hacia el valor eVar.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 255 bytes | V1-v75 ( [o v100 o v250](/help/implement/js-implementation/page-variables/page-variables.md)) | Conversión personalizada | "" |

**Caducidad**

Las `eVars` caducan después del período de tiempo que especifique. Cuando la eVar caduca, ya no recibe el crédito por los eventos de éxito. Las eVars también se pueden configurar para que caduquen cuando se produzcan eventos de éxito. Por ejemplo, si tiene una promoción interna que caduca el final de una visita, la promoción interna recibe el crédito solo por las compras o registros que se produzcan durante la visita en la que se activaron.

Hay dos maneras de que una eVar caduque:

* Puede configurar la eVar para que caduque después de un período de tiempo o evento especificados.
* Puede forzar la caducidad de una eVar, lo que resulta útil cuando se cambia el propósito de una variable.

Si se usa una eVar en mayo para reflejar promociones internas y caduca después de 21 días, y en junio se usa para capturar palabras clave de búsqueda interna, el 1 de junio, debe forzar la caducidad o restablecer la variable. Al hacerlo, no se incluyen los valores de la promoción interna en los informes de junio.

**Distinción entre mayúsculas y minúsculas**

Las eVars no distinguen entre mayúsculas y minúsculas, pero se muestran en la escritura en mayúsculas de la primera aparición. Por ejemplo, si la primera instancia de eVar1 es "Sesión iniciada" pero todas las demás instancias se pasan como "sesión iniciada", los informes siempre mostrarán "Sesión iniciada" como valor de eVar.

**Contadores**

Aunque las eVars se usan habitualmente para guardar valores de cadena, también se pueden configurar para que actúen como contadores. Las eVars son útiles como contadores para contar el número de acciones que un usuario realiza antes de un evento. Por ejemplo, puede usar una eVar para capturar el número de búsquedas internas antes de la compra. Cada vez que un visitante realiza una búsqueda, la eVar debe contener un valor de '+1'. Si un visitante realiza cuatro búsquedas antes de una compra, verá una instancia con cada recuento total: 1.00, 2.00, 3.00 y 4.00. Sin embargo, solo el valor 4.00 recibe el crédito por el evento purchase (métricas de pedidos e ingresos). Solo se permiten números positivos como valores de un contador eVar.

**Subrelaciones**

Uno de los requisitos habituales para un informe de eVar personalizado es la posibilidad de desglosar un informe de eVar personalizado por otro. Por ejemplo, si una eVar contiene el sexo y otra contiene el sueldo, puede preguntarse lo siguiente: de las mujeres visitantes de mi sitio, ¿cuántos ingresos generaron las mujeres que ganan más de 50.000 euros al año? Las eVars con subrelaciones completas admiten este tipo de desglose en los informes. Por ejemplo, si la eVar del sexo tiene habilitadas subrelaciones completas, todos los demás informes de eVar personalizados se pueden desglosar por sexo, y el sexo se puede desglosar por todos los demás. Para ver la relación entre dos informes, solo uno de ellos necesita tener habilitadas las subrelaciones completas. De forma predeterminada, los informes Campaña, Productos y Categoría están completamente subrelacionados (cualquier eVar se puede desglosar por campaña o productos).

**Sintaxis y valores posibles**

Aunque se puede cambiar el nombre de las eVars, siempre se debe hacer referencia a ellas en el archivo JavaScript por eVarX, donde X es un número entre 1 y 75 ([ o 100 o 250](/help/implement/js-implementation/page-variables/page-variables.md)).

```js
s.eVarX="value"
```

Cuando no se usan como contadores, las eVars tienen las mismas limitaciones que todas las demás variables. Si la eVar es un "contador", se espera que reciba valores numéricos como "1" o "2,5". Si se especifican más de dos decimales, el contador de eVar redondea a dos decimales. Un contador de eVar no puede contener números negativos.

**Ejemplos**

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**Parámetros de configuración**

Las eVars se pueden configurar en Analytics &gt; Administración &gt; Grupos de informes &gt; Editar configuración &gt; Conversión &gt; Variables de conversión]. Todas las eVars se pueden configurar con un Nombre, Tipo, Asignación, Caduca después de o Restaurar. Cada opción de configuración se trata por separado.

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Configuración </th> 
   <th class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nombre </td> 
   <td> Permite cambiar el nombre del informe de eVar en <span class="keyword">Analytics </span>. <p>Se debe hacer referencia a la eVar como s.eVarX en el código JavaScript, independientemente del nombre que se le asigne al informe en <span class="keyword">Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td> Tipo </td> 
   <td> Permite mostrar si la eVar es una Cadena de texto o un Contador. </td> 
  </tr> 
  <tr> 
   <td> Asignación </td> 
   <td> Se usa para configurar qué valor de la eVar recibe el crédito por los eventos de éxito. <p>Si Asignación se configura como "Más reciente (último)", B recibe el crédito. </p> <p>Si Asignación se configura como "Valor original (primero)", A recibe el crédito. </p> <p>Si Asignación se configura como "Lineal", tanto A como B reciben el crédito por la mitad del valor de la compra. </p> </td> 
  </tr> 
  <tr> 
   <td> Caduca después de </td> 
   <td> Permite determinar si una eVar expira cuando se produzca un evento específico, como una compra, o después de un período de tiempo personalizado o predefinido. </td> 
  </tr> 
  <tr> 
   <td> Restaurar </td> 
   <td> Al seleccionar la casilla <span class="wintitle">Restaurar</span> para una eVar y hacer clic en <span class="wintitle">Guardar</span> en la parte inferior de la página, todos los valores de esa eVar caducan inmediatamente. Cuando esto sucede, solo los nuevos valores de la eVar reciben el crédito por los eventos de éxito. </td> 
  </tr> 
 </tbody> 
</table>

**Problemas, preguntas y consejos**

* A diferencia de las variables [!UICONTROL prop], las variables eVar no pueden ser listas de valores delimitados. Si rellena una eVar con una lista de valores, por ejemplo, "uno,dos,tres,", en los informes aparecerá exactamente esa cadena.
* Los contadores de eVar no pueden contener números negativos.
