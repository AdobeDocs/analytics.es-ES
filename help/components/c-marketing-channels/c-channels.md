---
description: Agregue o habilite canales de marketing en el Administrador de canales de marketing. En los grupos de informes que no tengan canales de mercadotecnia, puede crear varios canales, junto con sus reglas, gracias a una configuración automática. Puede editar los canales predefinidos según sus necesidades o crear otros (hasta un total de 25).
subtopic: Marketing channels
title: Administrar Canales de marketing
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Administrar Canales de marketing

Agregue o habilite canales de marketing en el Administrador de canales de marketing. En los grupos de informes que no tengan canales de mercadotecnia, puede crear varios canales, junto con sus reglas, gracias a una configuración automática. Puede editar los canales predefinidos según sus necesidades o crear otros (hasta un total de 25).

Aquí tiene algunas indicaciones para la creación de canales:

* Planifíquelos con tiempo y haga una lista de todos los canales, de modo que todas las visitas se clasifiquen en el canal correcto.
* Incluya siempre canales para las categorías de visitas [Internas](/help/components/c-marketing-channels/c-faq.md) y [Directas](/help/components/c-marketing-channels/c-faq.md).

La adición de canales a la página [!UICONTROL Canales de mercadotecnia] se realiza independientemente de la creación de reglas en la página [Reglas de procesamiento de canal de mercadotecnia](/help/components/c-marketing-channels/t-rules.md). Al crear las reglas, se asocian a los canales.

## Agregar canales de marketing {#add-mktg-channels}

Agregue canales de marketing en el Administrador de canales de marketing.

> [!NOTE] Los canales no se pueden eliminar. Si no desea utilizar un canal, puede deshabilitarlo o cambiarle el nombre y guardarlo para utilizarlo después.

1. Haga clic en **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administración]** &gt; **[!UICONTROL Grupo de informes]**.
1. En la página [!UICONTROL Administrador del grupo de informes], seleccione un grupo de informes.

   Si selecciona varios grupos de informes, debe seleccionar una plantilla que copie la configuración de la plantilla a los grupos de informes seleccionados.

   Consulte [Aplicación de la configuración de un grupo de informes de plantilla a varios grupos de informes](/help/components/c-marketing-channels/t-template.md).

1. Haga clic en **[!UICONTROL Editar configuración]** &gt; **[!UICONTROL Canales de marketing]** &gt; **[!UICONTROL Administrador de canales de marketing]**.

   Si no se han definido canales en el grupo de informes, se abre la página [Configuración automática](/help/components/c-marketing-channels/c-channel-autosetup.md).

1. En la página [!UICONTROL Administrador de canales de mercadotecnia]**, haga clic en[!UICONTROL Agregar canal]**.

   Esta opción no está disponible cuando ya se han definido 25 canales.

1. Haga clic en **[!UICONTROL Guardar.]**
1. Para configurar las reglas del canal, haga clic en **[!UICONTROL Reglas de procesamiento de canal de marketing]**.

   Consulte [Creación de reglas de procesamiento para los canales de marketing](/help/components/c-marketing-channels/t-rules.md).

## Administrador del canal de marketing: definiciones de la interfaz {#mktg-channel-mgr}

Definiciones de los campos de la página [!UICONTROL Administrador del canal de mercadotecnia].

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definición </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Habilitado </p> </td> 
   <td colname="col2"> <p> Habilita o deshabilita el canal de mercadotecnia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre del canal </p> </td> 
   <td colname="col2"> <p>Nombre descriptivo del canal de mercadotecnia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anular canal de último toque </p> </td> 
   <td colname="col2"> <p> Permite sobrescribir un canal de último toque persistente actual con el canal seleccionado. Si selecciona esta casilla, cualquier canal (incluidos el directo y el interno) sobrescribirán el canal que se haya tocado por última vez. Por lo tanto, se atribuirá la conversión a un canal al que, posiblemente, no corresponda el crédito. Por ejemplo, esta opción podría garantizar que el canal directo no reciba el crédito por la conversión si el usuario ha sido adquirido anteriormente mediante el canal Búsqueda natural. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desglose de canal </p> </td> 
   <td colname="col2"> <p>Permite desglosar un canal según el valor especificado. Puede agregar posibles desgloses de canal (subcanales) al crear clasificaciones de canal de mercadotecnia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tipo </p> </td> 
   <td colname="col2"> <p> Especifica cómo llegó el usuario a su sitio web. Puede seleccionar <span class="uicontrol">En línea</span> o <span class="uicontrol">Sin conexión</span>. Utilice los canales en línea para los visitantes que llegaron mediante un motor de búsqueda o una campaña de correo electrónico. Los canales sin conexión se aplican a los visitantes que hayan encontrado el sitio mediante cupones de periódicos o anuncios en revistas. Por lo general, los canales sin conexión incluyen datos importados a través de las fuentes de datos de informes. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/"  >Fuentes de datos</a>. </p> <p>Consulte <a href="/help/components/c-marketing-channels/t-offline-data.md"   > Añadir datos sin conexión</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Color </p> </td> 
   <td colname="col2"> <p>El color asociado al canal de mercadotecnia. El color representa el canal en el informe <span class="wintitle">Canal de mercadotecnia</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

