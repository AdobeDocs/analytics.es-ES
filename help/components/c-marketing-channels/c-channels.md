---
description: Agregue o habilite los canales de mercadotecnia en el Administrador de canales de mercadotecnia. En los grupos de informes que no tengan canales de mercadotecnia, puede crear varios canales, junto con sus reglas, gracias a una configuración automática. Puede editar los canales predefinidos según sus necesidades o crear otros (hasta un total de 25).
seo-description: Agregue o habilite los canales de mercadotecnia en el Administrador de canales de mercadotecnia. En los grupos de informes que no tengan canales de mercadotecnia, puede crear varios canales, junto con sus reglas, gracias a una configuración automática. Puede editar los canales predefinidos según sus necesidades o crear otros (hasta un total de 25).
seo-title: Administrar canales de mercadotecnia
solution: Analytics
subtopic: Canales de mercadotecnia
title: Administrar canales de mercadotecnia
topic: Reports and Analytics
uuid: 9 d 367 bb 6-a 17 b -49 b 8-9 cd 5-24 fac 35 ae 982
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Administrar canales de mercadotecnia

Agregue o habilite los canales de mercadotecnia en el Administrador de canales de mercadotecnia. En los grupos de informes que no tengan canales de mercadotecnia, puede crear varios canales, junto con sus reglas, gracias a una configuración automática. Puede editar los canales predefinidos según sus necesidades o crear otros (hasta un total de 25).

## Manage marketing channels {#topic_45CF1C6A783B4F96ABF6317EAB6A854F}

Add or enable marketing channels in the [!UICONTROL Marketing Channel Manager]. En los grupos de informes que no tengan canales de mercadotecnia, puede crear varios canales, junto con sus reglas, gracias a una configuración automática. Puede editar los canales predefinidos según sus necesidades o crear otros (hasta un total de 25).

Aquí tiene algunas indicaciones para la creación de canales:

* Planifíquelos con tiempo y haga una lista de todos los canales, de modo que todas las visitas se clasifiquen en el canal correcto.
* Incluya siempre canales para las categorías de visitas [Internas](../../components/c-marketing-channels/c-faq.md#section_179A2BE5C8E24719A9E5C0DC09AF0947) y [Directas](../../components/c-marketing-channels/c-faq.md#section_D0A1DD9D5EEF4A05A1CC81F9EADC074A).

La adición de canales a la página [!UICONTROL Canales de mercadotecnia] se realiza independientemente de la creación de reglas en la página [Reglas de procesamiento de canal de mercadotecnia](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08). Al crear las reglas, se asocian a los canales.

## Agregar canales de marketing {#task_98C9D3F5DBBC4B198E0A9ED4D3891E03}

Agregue canales de marketing en el Administrador de canales de marketing.

>[!NOTE]
>
>No se puede eliminar un canal. Si no desea utilizar un canal, puede deshabilitarlo o cambiarle el nombre y guardarlo para utilizarlo después.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. En la página [!UICONTROL Administrador del grupo de informes], seleccione un grupo de informes.

   Si selecciona varios grupos de informes, debe seleccionar una plantilla que copie la configuración de la plantilla a los grupos de informes seleccionados.

   Consulte [Aplicación de la configuración de un grupo de informes de plantilla a varios grupos de informes](../../components/c-marketing-channels/t-template.md#task_0DE0A320EDA94FC5A6E5912868B6E2DC).

1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Manager]**.

   If your report suite does not have channels defined, the [Auto Setup](../../components/c-marketing-channels/c-channel-autosetup.md#topic_E9ABE9E9E71B4E40A4E7EA9AD2C0372B) page displays.

1. En la página [!UICONTROL Administrador de canales de mercadotecnia]**, haga clic en[!UICONTROL Agregar canal]**.

   Esta opción no está disponible cuando ya se han definido 25 canales.

1. Haga clic en **[!UICONTROL Guardar.]**
1. To configure rules for the channel, click **[!UICONTROL Marketing Channel Processing Rules]**.

   See [Create Marketing Channel processing rules](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08).

## Marketing Channel Manager - interface definitions {#reference_01779A2928054BF48339897D4033AFB9}

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
   <td colname="col2"> <p> Especifica cómo llegó el usuario a su sitio web. Puede seleccionar <span class="uicontrol">En línea</span> o <span class="uicontrol">Sin conexión</span>. Utilice los canales en línea para los visitantes que llegaron mediante un motor de búsqueda o una campaña de correo electrónico. Los canales sin conexión se aplican a los visitantes que hayan encontrado el sitio mediante cupones de periódicos o anuncios en revistas. Por lo general, los canales sin conexión incluyen datos importados a través de las fuentes de datos de informes. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/" scope="external" format="http">Fuentes de datos</a>. </p> <p>See <a href="../../components/c-marketing-channels/t-offline-data.md#task_FC96E6A48F0D4D37A79BD234E90DAA26" type="task" format="dita" scope="local"> Add Offline Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Color </p> </td> 
   <td colname="col2"> <p>El color asociado al canal de mercadotecnia. El color representa el canal en el informe <span class="wintitle">Canal de mercadotecnia</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

