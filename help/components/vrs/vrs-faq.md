---
description: Sugerencias y prácticas recomendadas para los nuevos usuarios de los grupos de informes virtuales.
keywords: Grupo de informes virtuales
seo-description: Sugerencias y prácticas recomendadas para los nuevos usuarios de los grupos de informes virtuales.
seo-title: FAQ de VRS
solution: Analytics
title: FAQ de VRS
topic: Reports and Analytics
uuid: 91225743-765 a -4145-9 ce 5-4268 e 80 ea 7 e 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# FAQ de VRS

Sugerencias y prácticas recomendadas para los nuevos usuarios de los grupos de informes virtuales.

<table id="table_4D9DE70984674B65AD7D40E3D1479CD2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta </th> 
   <th colname="col2" class="entry"> Respuesta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>¿Debería consolidar mi implementación desde varios grupos de informes en un único grupo de informes globales y, a continuación, utilizar los grupos de informes virtuales para exponer distintos segmentos de datos a mis usuarios?</b> </td> 
   <td colname="col2"> <p>Quizás. Estas son algunas circunstancias en las que debería <b>considerar si desea continuar con grupos de informes individuales</b>: </p> 
    <ul id="ul_493454A655DE48E0AF94130014203268"> 
     <li id="li_B37C2651D2804FD1B965286C85A765D5">Si tiene variables/dimensiones con un gran número de valores únicos, consolidarlas en un único grupo de informes podría hacer que se superaran los límites de valor único mensual en este grupo global, lo que produciría un truncado (poco tráfico como elemento de línea en los informes). </li> 
     <li id="li_87ABC62EC73D4355A9F768AD1949D3C6">Si necesita informes en tiempo real o de datos actuales para segmentos individuales (p. ej. marcas, unidades comerciales, etc.) de sus datos. </li> 
     <li id="li_7252787B2D4C4756836DAEA0EEC0BF8B">Si varios grupos de informes tienen requisitos únicos para seguimiento (es decir, si utilizan variables y eventos de Adobe Analytics de forma muy diferente), observe que consolidarlos en un grupo de informes globales no le otorgará variables ni eventos adicionales para el seguimiento. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>¿Qué configuración de los grupos de informes virtuales se hereda del grupo de informes superior? </b> </td> 
   <td colname="col2"> <p>Un grupo de informes virtuales (VRS) hereda la mayoría de los niveles de servicio del grupo de informes superior, como la configuración de las eVars, las reglas de procesamiento, las clasificaciones, etc. </p> <p><b>NO</b> se heredan las siguientes opciones de configuración: </p> 
    <ul id="ul_43B0637F095C480B82126C96BFF627FA"> 
     <li id="li_F3DF9D6B0B1A4A46B9D8B1CF2DA09BE3">ID del grupo de informes </li> 
     <li id="li_A735D7BA4DA14DCB8F40D7898A324F1F">Nombre del grupo de informes </li> 
     <li id="li_BF66DD426EE7464CBF7F2EB56B0C3075">Grupos de permisos (los grupos de informes virtuales se pueden asignar a sus propios grupos de permisos) </li> 
    </ul> <p>Nota: Esto no incluye la mayoría de las entidades creadas por el usuario, como marcadores, tableros, informes programados, etc.; estos elementos no se heredan del grupo superior y se pueden crear y utilizar para el VRS de forma específica (más información en la siguiente pregunta). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>¿En qué se diferencia trabajar con un grupo de informes virtuales de hacerlo con un grupo de informes base en la interfaz de usuario de Analytics?</b> </td> 
   <td colname="col2"> <p>Una vez creado, el grupo de informes virtuales se trata como un grupo de informes base en toda la interfaz de usuario y, por lo general, lo admiten las funciones más habituales. Por ejemplo: </p> 
    <ul id="ul_D20435FD9B3546DFB611FD09035BACBB"> 
     <li id="li_4A331EB50B7F43E697F67B4A657B4450">Los grupos de informes virtuales aparecen en el selector de grupos de informes y se pueden seleccionar individualmente como cualquier otro grupo de informes base. </li> 
     <li id="li_6E8C1E45C68943A1BA7C260FA62C40E0">Informes DL, marcadores, tableros, destinos, alertas, segmentos, métricas calculadas, etc.: todos se pueden crear para un grupo de informes virtuales y comportarse de forma independiente con respecto al grupo superior. </li> 
     <li id="li_5701D7F60BF8452CBEC8DFA2072CE8C2">Los grupos de informes virtuales se pueden añadir individualmente a los grupos de permisos como cualquier otro grupo de informes. </li> 
     <li id="li_764475FD352C434D92E876E30699F280">Los segmentos se pueden seguir aplicando cuando se ejecuten informes en el contexto de un VRS. Se apilarán automáticamente con los segmentos del grupo de informes virtuales cuando los datos del informe se estén recuperando. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>¿Cómo se tratan los grupos de informes virtuales en Admin Console y la API de administración? ¿Puedo guardar funciones para ellos como grupos de informes base? </b> </td> 
   <td colname="col2"> <p>No, los grupos de informes virtuales <b>no son compatibles con la mayoría de las funciones de administración</b>. Como se ha mencionado anteriormente, un VRS hereda la mayoría de los niveles de servicio y funciones del grupo superior (por ejemplo, la configuración de eVar, las reglas de procesamiento, las clasificaciones, etc.), por lo que debe modificar este grupo de informes superior para realizar cambios en esta configuración heredada en un VRS. </p> <p>Como resultado, los grupos de informes virtuales aparecen en la interfaz de usuario <b>solo aquí</b>: </p> 
    <ul id="ul_64CF126ACF39453A95BD9FC9D2CFA59B"> 
     <li id="li_08EBF87ADF13400C9DD3FFC2695F5CF9">Administrador de grupos de informes virtuales, donde crea y edita los VRS. <p>( <span class="ignoretag"> <span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol">Componentes</span> &gt; <span class="uicontrol">Grupos de informes virtuales </span> </span>) </p> </li> 
     <li id="li_E2B3F61A3013402697DCF6E0D32A62DC"> Interfaz de administración de usuarios, donde puede editar grupos de permisos personalizados. Esto permite añadir cuentas de VRS a un grupo de permisos y utilizarlas para crear un grupo que solo tenga acceso a grupos de informes virtuales (si el administrador quisiera denegar el acceso al nivel superior y permitir a los usuarios acceder solo a segmentos concretos). <p>( <span class="ignoretag"> <span class="uicontrol"> Administración</span> &gt; <span class="uicontrol">Administración de usuarios </span> </span>) </p> </li> 
    </ul> <p>Nota: Cuando utiliza la API de servicios web y trata de guardar la configuración de la función para un VRS, se produce una excepción. Las funciones solo se pueden establecer para un grupo de informes base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>¿La interfaz de usuario de SiteCatalyst 14 admite grupos de informes virtuales?</b> </td> 
   <td colname="col2"> <p>No, los grupos de informes virtuales no se exponen en SiteCatalyst 14. No aparecerán en el selector de grupos de informes, por lo que no se podrán seleccionar. Sin embargo, sí se exponen grupos de informes virtuales en la interfaz de usuario de Admin Console de SiteCatalyst 14 cuando se edita un grupo. En este caso concreto, los grupos de informes virtuales deben representarse para que no se eliminen por error de un grupo existente que ya puede tener acceso a uno o varios grupos de informes virtuales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> He marcado “comenzar nueva visita al inicio”. ¿Por qué sigo viendo que hay muchas más visitas que inicios?</b> </td> 
   <td colname="col2"> <p> Cuando se activa la opción <span class="uicontrol">comenzar nueva visita al inicio</span>, se sigue aplicando el tiempo de espera. Por tanto, si un usuario utiliza la aplicación durante 10 minutos y deja pasar un minuto entre cada acción, se generará una nueva visita al inicio y otras nueve más, creadas al superarse el tiempo de espera de visita. Para que el número de inicios y de visitas sea lo más parecido posible al utilizar la opción <span class="uicontrol">comenzar nueva visita al inicio</span>, se debe establecer un tiempo de espera mayor que el tiempo de espera de sesión definido en el SDK. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Establezco “comenzar nueva visita al inicio” y configuro un tiempo de espera mayor que el del SDK. ¿Por qué el número de inicios sigue siendo mucho menor que el de visitas?</b> </td> 
   <td colname="col2"> <p> Si el tiempo de espera es mayor que el valor establecido en el SDK, es muy probable que la aplicación esté enviando visitas individuales cuando está en segundo plano, y que dichas visitas individuales se estén registrando como visitas nuevas. Compruébelo utilizando la dimensión Tipo de visita en el grupo de informes principal para ver si se producen visitas individuales en segundo plano. </p> <p> <p>Nota: El SDK solo diferencia las visitas en primer y segundo plano a partir de la versión 4.13.6. Si su versión es anterior, todas las visitas individuales se mostrarán como visitas en primer plano. Si su versión del SDK es la correcta, habilite el ajuste <span class="uicontrol">Impedir que las visitas en segundo plano inicien una nueva visita</span>. </p> </p> <p> <p>Nota: Si deshabilita el procesamiento heredado de las visitas individuales en segundo plano en Admin Console, estas no aparecerán en el grupo de informes principal, pero sí en el grupo de informes virtuales. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> ¿Qué versión del SDK necesito para poder realizar el seguimiento de las visitas individuales en segundo plano?</b> </td> 
   <td colname="col2"> <p> Necesita la versión 4.13.6 o superior del SDK. </p> </td> 
  </tr> 
 </tbody> 
</table>

