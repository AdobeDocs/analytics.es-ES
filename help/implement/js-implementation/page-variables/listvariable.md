---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# Variable de lista

También se conoce como List Var. Similar a cómo funcionan las props de lista, las variables de lista permiten incluir varios valores dentro de la misma solicitud de imagen. Actúan de modo similar a las eVars, las cuales persisten más allá de la solicitud de imagen en la que se definieron. Puede usar estas variables para ver la causa y el efecto de varios elementos de una única página como, por ejemplo, listas de productos, listas de preferencias, listas de perfeccionamiento de búsqueda o listas de anuncios en pantalla.


<!-- 

listN.xml (bob edit)

 -->

**Consideraciones**

* Las variables de lista recuerdan sus valores específicos mediante referencia a la cookie VisitorID del explorador del visitante.
* Se almacena un límite de 250 valores máximos una vez por visitante. Si se exceden los 250 valores por visitante, se utilizan los últimos 250 valores. La caducidad de estos valores está basada en la caducidad configurada para la variable.
* Cada valor delimitado puede contener un máximo de 255 caracteres (o menos si se utilizan caracteres multibyte). Esta es la longitud máxima de cada elemento.
* No existe ningún límite para el número de caracteres dentro de esta variable. La única excepción a esta limitación es que los exploradores Internet Explorer antiguos imponen una limitación de 2083 caracteres en todas las solicitudes URL.
* Hay disponible un total de tres variables de lista por grupo de informes.
* El uso de variables de lista requiere el código H23 o superior.
* Las variables de lista pueden clasificarse.
* Si se definen valores duplicados en la misma solicitud de imagen, las variables de lista anulan la duplicación de todas las instancias de esos valores.
* El mayor detalle con el que se pueden segmentar las variables de lista es por visita (o vista de página). Si tiene una variable de lista con tres valores en la misma solicitud de imagen, las reglas de segmentación que coincidan con uno de los valores enviarán los tres al informe. Por el contrario, si una regla de conversión definida coincide con un único valor, se excluyen los tres valores.

**Configuración** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

Puede acceder a la configuración en Admin Console y actualizarla sin tener que involucrar al Servicio de atención al cliente de Adobe:

1. Vaya a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; **[!UICONTROL Grupos de informes]**
1. Seleccione el grupo de informes.
1. Haga clic en **[!UICONTROL Editar configuración]** &gt; **[!UICONTROL Conversión]** &gt; **[!UICONTROL Lista de variables]**.

* **Nombre**: Cada valor delimitado puede contener un máximo de 255 caracteres (o menos si se utilizan caracteres multibyte). Esta es la longitud máxima de cada elemento.
* **Delimitador de valores**: carácter utilizado para separar valores en una variable de lista. Normalmente son caracteres como comas, dos puntos, barras verticales o algún otro similar.

   >[!NOTE]
   >
   >Los caracteres de bytes múltiples no se admiten como delimitadores en variables de lista. El delimitador debe ser de un solo byte.

* **Caducidad**: similar a la caducidad de eVar, determina la cantidad de tiempo que puede transcurrir entre la variable de lista y el evento de conversión para que se relacionen.

   * **A nivel de vista de página o visita**: Los eventos de éxito más allá de la vista de página o la visita no se vincularán con ningún valor que haya dentro de la variable de lista.
   * **En función de un período de tiempo como día, semana, mes, etc.**: Los eventos de éxito que no entren dentro del período de tiempo especificado no se vincularán a ningún valor que haya dentro de la variable de lista. También se puede definir un número de días personalizado.
   * **Eventos de conversión específicos**: Cualquier otro evento de éxito que se active después del evento específico designado no se vinculará con ningún valor que haya dentro de la variable de lista.
   * **Nunca**: Puede transcurrir cualquier cantidad de tiempo entre la variable de lista y el evento de éxito.

* **Asignación**: Esta opción determina cómo dividirán los eventos de éxito el crédito entre los valores:

   * **Total**: Todos los valores de variable definidos antes de la caducidad de la variable obtienen el total del crédito por los eventos de éxito.
   * **Lineal**: Todos los valores de variable definidos antes de la caducidad de la variable obtienen el crédito dividido entre los eventos de conversión.
   * Los valores de variable no se sobrescriben nunca; se suman a los valores que obtienen el crédito por los eventos de éxito.

* **Valores máximos**: Designa el número de valores activos permitidos para esta variable de lista. Por ejemplo, si se establece en 3, solo se guardarán los últimos 3 valores capturados y se descartarán todos los capturados con anterioridad. Tenga en cuenta que si se envían varios valores para la misma variable de lista en la misma visita y se ha restringido el uso de los valores máximos, todos los valores adquirirán la misma marca de tiempo y no puede garantizarse qué valor se guardará.

   Se almacena un límite de 250 valores máximos una vez por visitante. Si se exceden los 250 valores por visitante, se utilizan los últimos 250 valores. La caducidad de estos valores está basada en la caducidad configurada para la variable.

   La opción Valores máximos resulta muy útil para limitar la atribución a un número específico de valores. Por ejemplo, si una variable de lista se establece en "A,B,C" en la primera página de una visita y en "X,Y,Z" en la página siguiente, la atribución se distribuye a estos seis valores en función de la asignación. Si desea limitar la atribución a "X,Y,Z" exclusivamente, puede establecer los valores máximos en tres.

Para establecer o editar las variables de lista, vaya a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; **[!UICONTROL Grupos de informes]** &gt; **[!UICONTROL Editar configuración]** &gt; **[!UICONTROL Conversión]** &gt; **[!UICONTROL Variables de lista]**.

**Ejemplos de implementación** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

En cada uno de los ejemplos siguientes se utiliza una coma como delimitador de valores.

**Definir un valor único en una variable de lista:**

```js
s.list1="Cat";
```

**Pasar varios valores:**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**Atribuir ingresos a una variable de lista:**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

Este resultado mostraría tres elementos de línea con 50 dólares de ingresos cada uno. (Top Banner Ad; Side Bar Ad; and Internal Campaign 1). Tenga en cuenta que el total para este informe anula la duplicación de los ingresos, por lo que el total también reflejaría 50 dólares.

**Atribuir ingresos a una variable de lista que se configuró varias veces durante una visita:**

**Asignación**: Total

**Caducidad**: Visita

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Activity Map </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Página 1 </td> 
   <td colname="col2"> <code> s.list1="value1,value2,value3"; </code> </td> 
   <td colname="col3"> (sin configurar) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Página 2 </td> 
   <td colname="col2"> <code> s.list1="value4,value5,value6"; </code> </td> 
   <td colname="col3"> <p> <code> s.events="purchase"; </code> </p> <p> <code> s.products=";product;1;200" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Resultado**: Todos los valores configurados en la list var1 en cualquier momento durante la visita (value1,value2,value3,value4,value5,value6) obtienen el crédito total de la compra.

