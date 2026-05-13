---
description: La página Métodos de búsqueda identifica cómo reciben crédito varios informes de métodos de búsqueda para los eventos de éxito de conversión en el sitio. Por ejemplo, si un motor de búsqueda remite a un visitante del sitio que realiza una compra, los métodos de búsqueda especifican la forma en que el motor de búsqueda recibe el crédito por la referencia.
title: Métodos de búsqueda
feature: Admin Tools
role: Admin
exl-id: 58c4510c-2343-4b0a-9c09-5583f6d4250f
TQID: https://experienceleague.adobe.com/eIZhSAm5tZsV4bY3Bznamfq87nhWd82ZwL-M4OIkFSM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 319
ht-degree: 48%

---

# Métodos de búsqueda

La página Métodos de búsqueda identifica cómo reciben crédito varios informes de métodos de búsqueda para los eventos de éxito de conversión en el sitio. Por ejemplo, si un motor de búsqueda remite a un visitante del sitio que realiza una compra, los métodos de búsqueda especifican la forma en que el motor de búsqueda recibe el crédito por la referencia.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Métodos de búsqueda]**

## Descripciones de los métodos de búsqueda {#section_8B6278DB75224EAB9F49D89A86274E8A}

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
   <td colname="col2"> El método de localización que desea modificar </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Asignación </td> 
   <td colname="col2"> Especifica cómo aplicar crédito para una referencia. Las opciones de asignación admitidas incluyen: <p> <span class="uicontrol"> Más reciente (último):</span> otorga todo el crédito al último referente (predeterminado). </p> <p> <span class="uicontrol"> Valor original:</span> otorga todo el crédito al primer referente. </p> <p> <span class="uicontrol"> Lineal:</span> divide el crédito equitativamente entre todos los referentes. </p> </td> 
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
>Todos los métodos de búsqueda caducan al finalizar la visita. Si elige Caduca después de un evento diferente (por ejemplo, Cierre de carro de compras), el Método de localización caduca cuando se produce el cierre de compra de carro de compras durante la visita. Si no se produce un cierre de compra del carro de compras durante la visita, el método de localización caduca cuando finaliza la visita.
