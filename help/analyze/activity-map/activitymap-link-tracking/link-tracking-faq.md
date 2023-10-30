---
description: Preguntas frecuentes sobre el seguimiento de vínculos en Activity Map.
title: Preguntas frecuentes sobre el seguimiento de vínculos
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: a0b8f61c3728c5867640ce20768614c8d79ca657
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 100%

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

La identificación de vínculos y regiones de Activity Map se lleva cabo cuando los usuarios hacen clic en una página.

## ¿De qué elementos se realiza el seguimiento de forma predeterminada?

Si se da un evento de clic en un elemento, este tiene que pasar algunas comprobaciones para determinar si AppMeasurement lo tratará como un vínculo. Las comprobaciones son las siguientes:

* ¿Se trata de una etiqueta `A` o `AREA` con una propiedad `href`?
* ¿Hay un atributo `onclick` que define la variable `s_objectID`?
* ¿Se trata de una etiqueta `INPUT` o un botón `SUBMIT` con un valor o texto secundario?
* ¿Se trata de una etiqueta `INPUT` con el tipo `IMAGE` y una propiedad `src`?
* ¿Es un `BUTTON`?

Si la respuesta a alguna de estas preguntas es Sí, el elemento se trata como vínculo y se le realiza un seguimiento.

>[!IMPORTANT]
>
>AppMeasurement no considera las etiquetas de botón con el atributo type=&quot;button&quot; como vínculos. Considere la posibilidad de quitar el atributo type=&quot;button&quot; de las etiquetas de botón y añadir en su lugar role=&quot;button&quot; o submit=&quot;button&quot;.

>[!IMPORTANT]
>
>Las etiquetas de anclaje con un “href” que comienza con “#” se consideran una ubicación de destino interna con AppMeasurement, no un vínculo (ya que no se abandona la página). De forma predeterminada, Activity Map no realiza el seguimiento de estas ubicaciones de destino internas. Rastrea únicamente los vínculos que conducen al usuario a una nueva página.

## ¿Cómo realiza Activity Map el seguimiento de otros elementos HTML visuales?

a. A través de la función `s.tl()`.

Si el clic se produjo a través de una invocación de `s.tl()`, Activity Map también recibirá este evento de clic y determinará si se encontró la variable de cadena `linkName`. Durante la ejecución de `s.tl()`, el linkName se definirá como ID del vínculo de Activity Map. El elemento donde se hizo clic y que originó la llamada de `s.tl()` se utilizará para determinar la región. Ejemplo:

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. A través de la variable `s_objectID`. Ejemplo:

    ``` 
    
    &lt;img onclick=&quot;s_objectID=&#39;abc&#39;;&quot; src=&quot;someimageurl.png&quot;/>
    &lt;a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&#39;abc&#39;;&quot; >
    Link Text Here
    &lt;/a>
    
    ```

>[!IMPORTANT]
>
>Tenga en cuenta que es obligatorio el uso de un punto y coma (;) de cierre al usar `s_objectID` en Activity Map.

## ¿Pueden dar ejemplos de vínculos de los que se realizará un seguimiento?

### Ejemplo 1

```
  <a href="/home>Home</a>
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

1. Razón: la etiqueta de anclaje no tiene un `href` válido:
   `<a name="innerAnchor">Section header</a>`

1. Razón: no aparecen `s_ObjectID` ni `s.tl()`:    

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. Razón: no aparecen `s_ObjectID` ni `s.tl()`:  

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. Razón: falta la propiedad “src” en un elemento de entrada de formulario:

   `<input type="image"/>`

