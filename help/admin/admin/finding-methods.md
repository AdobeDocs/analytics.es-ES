---
description: La página Métodos de localización identifica la manera en que los diversos informes de métodos de localización reciben crédito para eventos de éxito de conversión en un sitio. Por ejemplo, si un motor de búsqueda envía a un visitante a un sitio, y este visitante realiza una compra, Métodos de localización especifica cómo debe recibir el crédito el motor de búsqueda para el referente.
title: Métodos de búsqueda
feature: Herramientas de administración
uuid: 1053993e-7fc4-4874-84fa-367ecdcd7b45
exl-id: 58c4510c-2343-4b0a-9c09-5583f6d4250f
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 100%

---

# Métodos de búsqueda

La página Métodos de localización identifica la manera en que los diversos informes de métodos de localización reciben crédito para eventos de éxito de conversión en un sitio. Por ejemplo, si un motor de búsqueda envía a un visitante a un sitio, y este visitante realiza una compra, Métodos de localización especifica cómo debe recibir el crédito el motor de búsqueda para el referente.

**[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Métodos de localización]**.

## Descripciones de los métodos de localización {#section_8B6278DB75224EAB9F49D89A86274E8A}

<table id="table_8ABC1C9BD63F419082E4C4C69E401526"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> El método de búsqueda que se debe modificar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Asignación </td> 
   <td colname="col2"> Especifica cómo aplicar crédito a un referente. Las opciones de asignación que se admiten son las siguientes: <p> <span class="uicontrol"> Más reciente (último):</span> otorga todo el crédito al último referente (predeterminado). </p> <p> <span class="uicontrol"> Valor original:</span> otorga todo el crédito al primer referente. </p> <p> <span class="uicontrol"> Lineal:</span> divide el crédito equitativamente entre todos los referentes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Caduca después </td> 
   <td colname="col2"> 
    <ul id="ul_95EB224CAD164E9997B148E08AFA5F9B"> 
     <li id="li_C240460C21E14AA498D2EA62B9354710"> <span class="uicontrol"> Visita:</span> después de un período de inactividad especificado, por lo general, de unos 30 minutos. </li> 
     <li id="li_A3AE5438919E44B68DF99BEEA60C44EE"> <span class="uicontrol"> Vista de página:</span> cuando se abre cualquier página del sitio. </li> 
     <li id="li_D5E20FEF313E4C5B99E7097CA175761A"> <span class="uicontrol"> Minuto:</span> después de 1 minuto de inactividad. </li> 
     <li id="li_7315AA3EDDBB47A2BEA3C173881378A1"> <span class="uicontrol"> Compra:</span> en el momento de la compra. </li> 
     <li id="li_C0CF07581654472C9C9EC944E6F18164"> <span class="uicontrol"> Vista de producto:</span> cuando el visitante ve una página Web de un producto. </li> 
     <li id="li_A1B04065150B407491D2EC78EC0DBDF5"> <span class="uicontrol"> Apertura de carro:</span> cuando un visitante abre un nuevo carro de la compra en línea. </li> 
     <li id="li_2AA50C6B9CB14500B67909CDF2AA700C"> <span class="uicontrol"> Cierre de carro:</span> cuando un visitante cierra la compra con un carro de la compra en línea. </li> 
     <li id="li_F58CE6FB8DCE4BE4927FFCB35A6D8E31"> <span class="uicontrol"> Adición al carro:</span> cuando un visitante agrega un producto a un carro de la compra en línea. </li> 
     <li id="li_AD7C846F46604FC48E0919ACB7515E14"> <span class="uicontrol"> Retirada del carro:</span> cuando un visitante retira un producto de un carro de la compra en línea. </li> 
     <li id="li_EB66E0563F564C9F985BE922DABD0A56"> <span class="uicontrol"> Apertura de carro:</span> cuando un visitante ve el contenido de un carro de la compra en línea. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Todos los métodos de búsqueda caducan al finalizar la visita. Si elige que caduque después de un evento distinto (por ejemplo, con el cierre de compra del carro), el método de búsqueda caducará cuando se produzca el cierre de compra, durante la visita. Si no se produce el cierre de compra durante la visita, el método de búsqueda caducará cuando la visita finalice.
