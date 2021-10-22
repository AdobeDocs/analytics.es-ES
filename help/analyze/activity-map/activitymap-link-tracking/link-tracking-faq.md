---
description: Preguntas frecuentes sobre el seguimiento de vínculos en Activity Map.
title: Preguntas frecuentes sobre el seguimiento de vínculos
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: 2a20ce50f773c82856da59154bb212f1fca2b7ea
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 43%

---

# Preguntas frecuentes sobre el seguimiento de vínculos

Preguntas frecuentes sobre el seguimiento de vínculos en Activity Map.

>[!CAUTION]
>
>Si activa el seguimiento de Activity Map, **es posible que recopile información de identificación personal (PII)**. Dicha información se puede utilizar, tanto por sí sola como con otros datos, para identificar o localizar a una persona única, para ponerse en contacto con ella o para identificar a una persona en contexto.

A continuación se indican algunos casos conocidos en los que pueden recopilarse datos PII con el seguimiento de Activity Map:

* Vínculos `Mailto`. Un vínculo mailto es un tipo de vínculo HTML que activa el cliente de correo predeterminado en el equipo para enviar un mensaje de correo electrónico.
* Los vínculos de `User ID` pueden aparecer en el encabezado o pie de página de un sitio web una vez que el usuario ha iniciado sesión.
* Para las instituciones financieras, es posible que se muestre como vínculo el número de cuenta. Al hacer clic en dicho vínculo, se recopilará el texto que contenga.
* Los sitios web de entidades sanitarias también pueden mostrar datos PII como vínculos. Al hacer clic en dichos vínculos, se recopilará el texto que contengan, por lo que se recopilarán datos PII.

## ¿Cuándo se produce el seguimiento de vínculos?

La identificación de vínculos y regiones de Activity Map se produce cuando los usuarios hacen clic en una página.

## ¿De qué elementos se realiza el seguimiento de forma predeterminada?

Si se produce un evento de clic en un elemento, este tiene que pasar algunas comprobaciones para determinar si AppMeasurement lo tratará como un vínculo. Las comprobaciones son:

* ¿Es esto una `A` o `AREA` con un `href` propiedad?
* ¿Hay un `onclick` atributo que establece un `s_objectID` variable?
* ¿Es esto una `INPUT` o `SUBMIT` con un valor o texto secundario?
* ¿Es esto una `INPUT` etiqueta con tipo `IMAGE` y `src` propiedad?
* ¿Es esto una `BUTTON`?

Si la respuesta a alguna de estas preguntas es Sí, el elemento se trata como vínculo y se le realiza un seguimiento.

>[!IMPORTANT]
>
>AppMeasurement no considera las etiquetas Button con el atributo type=&quot;button&quot; como vínculos. Considere la posibilidad de quitar type=&quot;button&quot; de las etiquetas Button y agregar en su lugar role=&quot;button&quot; o submit=&quot;button&quot;.

>[!IMPORTANT]
>
>AppMeasurement considera una etiqueta de anclaje con un &quot;href&quot; que comienza con &quot;#&quot; una ubicación de destino interna, no un vínculo (ya que no abandona la página). De forma predeterminada, Activity Map no realiza el seguimiento de estas ubicaciones de destino internas. Rastrea únicamente los vínculos que conducen al usuario a una nueva página.

## ¿Cómo realiza el Activity Map el seguimiento de otros elementos del HTML visual?

a. A través de la función `s.tl()` función.

Si el clic se produjo mediante un `s.tl()` invocación de , el Activity Map también recibirá este evento de clic y determinará si `linkName` se ha encontrado la variable de cadena . Durante `s.tl()` , el linkName se establecerá como ID del vínculo del Activity Map. El elemento en el que se hizo clic que originó la variable `s.tl()` para determinar la región. Ejemplo:

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. A través de la función `s_objectID` variable. Ejemplo:

    &quot; 
    
    &lt;img onclick=&quot;s_objectID=&amp;#39;abc&amp;#39;;&quot; src=&quot;someimageurl.png&quot; />
    &lt;a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&amp;#39;abc&amp;#39;;&quot;>
    Vincular texto aquí
    &lt;/a>
    
    &quot;

>[!IMPORTANT]
>
>Se requiere un punto y coma de cierre (;) al usar `s_objectID` en Activity Map.

## ¿Pueden dar ejemplos de vínculos de los que se realizará un seguimiento?

### Ejemplo 1

```
  <a hef="/home?lang=en>Home</a>
```

### Ejemplo 2

```
 <input type="submit" value="Submit"/>
```

### Ejemplo 3

```
  <input type="image" src="submit-button.png"/>
```

### Ejemplo 4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### Ejemplo 5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## ¿Pueden dar ejemplos de vínculos de los que NO se realizará un seguimiento?

1. Motivo: La etiqueta delimitadora no tiene un valor válido `href`:
   `<a name="innerAnchor">Section header</a>`

1. Motivo: Ni `s_ObjectID` nor `s.tl()` presente:

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. Motivo: Ni `s_ObjectID` nor `s.tl()` presente:

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. Motivo: falta la propiedad &quot;src&quot; en un elemento de entrada de formulario:

   `<input type="image"/>`

