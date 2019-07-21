---
description: Muestra un promedio de la distancia recorrida en una visita para que se active cada valor. Esta métrica es muy valiosa a la hora de determinar hasta qué punto de una página determinada o valor de prop llegan los usuarios durante una visita. Profundidad promedio de la página está disponible en cualquier variable que tenga las rutas activadas.
seo-description: Muestra un promedio de la distancia recorrida en una visita para que se active cada valor. Esta métrica es muy valiosa a la hora de determinar hasta qué punto de una página determinada o valor de prop llegan los usuarios durante una visita. Profundidad promedio de la página está disponible en cualquier variable que tenga las rutas activadas.
seo-title: Profundidad promedio de la página
solution: Analytics
title: Profundidad promedio de la página
topic: Métricas
uuid: 4 d 8 a 3 a 3 c-c 698-4210-8 dd 8-a 02 a 1638483 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Profundidad promedio de la página

Muestra un promedio de la distancia recorrida en una visita para que se active cada valor. Esta métrica es muy valiosa a la hora de determinar hasta qué punto de una página determinada o valor de prop llegan los usuarios durante una visita. Profundidad promedio de la página está disponible en cualquier variable que tenga las rutas activadas.

Por ejemplo, si una visita contiene la ruta siguiente: Página A &gt; Página B &gt; Página C &gt; Página D &gt; Página E &gt; Página F, la profundidad es un índice que muestra dónde está la página. Por ejemplo: la “Página A” tiene una profundidad de 0, mientras que la “Página F” tiene una profundidad de cinco. El promedio se basa en una combinación de todas las visitas. Una profundidad de página cuyo valor sea inferior a uno (por ejemplo: 0,9), se corresponderá con el valor medio de todas las páginas visitadas con anterioridad a la página en cuestión.

La [!UICONTROL profundidad de página] ayuda a conocer la posición de una determinada página en la ruta del usuario, independientemente de las páginas siguientes o anteriores de esta ruta. Como tal, ayuda a proporcionar una perspectiva de cómo encaja la página en la imagen general de la experiencia del usuario dentro del sitio. Esta perspectiva se puede ver mejor en el informe [!UICONTROL Páginas].

<table id="table_E92B185A487C40E28C70EA30EDF73A40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Usos </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tráfico </td> 
   <td colname="col2"> <p>Cálculo de los eventos de página y las páginas vistas divididas por las visitas; muestra el promedio de clics de una página. Considere la misma ruta de visita: </p> <p>A &gt; B &gt; B &gt; C &gt; D &gt; B </p> <p>El número de clics se calcula por página y por evento de página, incluidas las recargas de página cuando está habilitada la opción "Contabilizar instancias repetidas" (esta opción está habilitada de manera predeterminada en el Ad Hoc Analysis, y siempre está habilitada en Marketing Reports and Analytics). En esta visita, la página A recibe 0 clics. Para la página B, el número de clics sería 1, 2 y 5. Para calcular la media sería [(1+2+5) / 3] para una Profundidad promedio de la página de 2,67 para la página B. </p> <p>Cuando está deshabilitada la opción "Contabilizar instancias repetidas", la página B recibe 1 y 4. La segunda visita no se contabilizará. El cálculo sería [(1+4) / 2 = 2,5]. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conversión </td> 
   <td colname="col2"> N/A </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Informe de profundidad de página](/help/components/c-variables/dimensionslist/reports-page-depth.md)

