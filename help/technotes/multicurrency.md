---
description: Describe cómo definir códigos de moneda objetivo para que funcione la compatibilidad con varias monedas.
title: Compatibilidad con múltiples monedas
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 63a6ca92ae5fe103648c74bd16bcdf90858c71f3

---


# Compatibilidad con múltiples monedas

Este documento describe cómo definir códigos de moneda objetivo para la compatibilidad con varias monedas.

Los códigos de moneda de destino se definen en tres niveles:

## Nivel de página

Puede establecer una variable de JavaScript para la moneda de destino en el nivel de página. El propietario del sitio establece esta variable con el código de moneda correcto de tres letras ISO 4217 (como se enumera a continuación en este documento). Si la variable [currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/vars/config-vars/currencycode.html) no está configurada en este nivel, la moneda predeterminada será la misma que la especificada en el grupo de informes. Si la variable en el nivel de página entra en conflicto con la variable especificada en el grupo de informes, la variable en el grupo de informes tendrá prioridad.


## Nivel de grupo de informes

La moneda **** base se especifica al [crear grupos](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html)de informes. Esta es la configuración predeterminada para moneda y tiene prioridad sobre los códigos de moneda establecidos en el nivel de página. Por lo tanto, si un grupo de informes tiene pedidos que aceptan dólares estadounidenses, euros y libras esterlinas y el grupo de informes tiene un código de moneda predeterminado establecido en &quot;dólares estadounidenses&quot;, la base de datos de informes de back-end traduce todas las transacciones a dólares estadounidenses.

Los informes de marketing utilizan el tipo de cambio en el momento en que se produce la solicitud de imagen para traducir los valores monetarios de nivel de página a los valores monetarios predeterminados del grupo de informes. Los grupos de informes utilizan &quot;dólares estadounidenses&quot; como moneda predeterminada.


## Nivel de informe

Los usuarios pueden establecer la moneda predeterminada de los informes para la sesión de inicio de sesión del usuario. Se puede acceder a esta opción a través del vínculo **Opciones de visualización** de cualquier informe de conversión. Los informes de marketing utilizan el tipo de cambio en el momento en que se ejecuta el informe para convertir los valores monetarios del grupo de informes en valores monetarios especificados por el informe.

## Códigos de moneda admitidos (ISO 4217)

Actualmente, Analytics admite los siguientes formatos de moneda para transacciones de conversión:


&#39;AFA&#39; Afganis de Afganistán (AFA)

&#39;AFN&#39; Afganistán (AFN)

Leke albanés &#39;TODOS&#39; (TODOS)

Dinar argelino &#39;DZD&#39; (DZD)

&#39;AOA&#39; Angola Kwanza (AOA)

&#39;ARS&#39; Peso argentino (ARS)

Drams de Armenia &#39;AMD&#39; (AMD)

Florín de Aruba (GTE)

Dólar australiano &#39;AUD&#39; (AUD)

Manat azerí azerbaiyano &#39;AZM&#39; (AZM)

&#39;AZN&#39; Azerbaiyán nuevos manat (AZN)

Dólar bahameño &#39;BSD&#39; (BSD)

Dinar bahreiní &#39;BHD&#39; (BHD)

&#39;BDT&#39; Taka bangladesí (BDT)

&#39;BBD&#39; Dólar de Barbados (BBD)

Rublos bielorrusos &#39;BYR&#39; (BYR)

Dólar beliceño &#39;BZD&#39; (BZD)

Dólar bermudeño &#39;BMD&#39; (BMD)

Ngultrum butanés &#39;BTN&#39; (BTN)

BOB Bolivia Bolivianos

Marka convertible de Bosnia y Herzegovina (BAM)

Pulas de Botsuana &#39;BWP&#39; (BWP)

&#39;BRL&#39; reales brasileños (BRL)

Dólar de Brunei &#39;BND&#39; (BND)

&#39;BGN&#39; Bulgaria Leva (BGN)

Franco burundiano &#39;BIF&#39;

Rieles camboyanos &#39;KHR&#39; (KHR)

Dólar canadiense &#39;CAD&#39; (CAD)

Escudos de Cabo Verde &#39;CVE&#39; (CVE)

Dólar &#39;KYD&#39; de las Islas Caimán (KYD)

Peso chileno &#39;CLP&#39; (CLP)

Yuan renminbi chino &#39;CNY&#39; (CNY)

Peso colombiano &#39;COP&#39; (COP)

&#39;XOF&#39; Community Financière Africaine Francs BCEAO (XOF)

&#39;XAF&#39; Community Financière Africaine Francs BEAC (XAF)

Franco comorense &#39;KMF&#39; (KMF)

&#39;XPF&#39; Comptoirs Français du Pacifique Francs (XPF)

Franco congoleño &#39;CDF&#39;/Kinshasa (CDF)

Colones costarricenses (CRC)

Kuna croata (HRK)

Peso convertible cubano &#39;CUC&#39;

&#39;CUP&#39; Peso cubano (CUP)

Libra chipriota &quot;CYP&quot; (CYP)

Corona checa &#39;CZK&#39; (CZK)

Corona danesa &#39;DKK&#39; (DKK)

Francos de Djibouti &#39;DJF&#39; (DJF)

Peso dominicano (DOP)

Dólar &#39;XCD&#39; del Caribe Oriental (XCD)

Libra egipcia &#39;EGP&#39; (EGP)

Colones salvadoreños &#39;SVC&#39; (SVC)

&quot;ERN&quot; Eritrea Nakfa (ERN)

ERR &#39;XBT&#39; (XBT)

&quot;EEK&quot; Krooni estonio (EEK)

Birr etíope &#39;ETB&#39; (ETB)

Euro &quot;EUR&quot; (EUR)

Libra malvinense &#39;FKP&#39; (FKP)

Dólar fijiano &#39;FJD&#39; (FJD)

&#39;GMD&#39; Gambia Dalasi (GMD)

&#39;GEL&#39; Georgia Lari (GEL)

&#39;GHC&#39; Cedis de Ghana (GHC)

Cedis (GHS) de Ghana

Libra gibraltareña &#39;GIP&#39; (GIP)

Onzas de oro &#39;XAU&#39; (XAU)

&#39;GTQ&#39; Guatemala Quetzales (GTQ)

Libra guernesca del GGP

Franco guineano &#39;GNF&#39; (GNF)

Dólar guyanés &#39;GYD&#39; (GYD)

Gourdes haitianos &#39;HTG&#39; (HTG)

&quot;HNL&quot; Honduras Lempiras (HNL)

Dólar de Hong Kong &#39;HKD&#39; (HKD)

Florín húngaro &#39;HUF&#39; (HUF)

Corona islandesa &#39;ISK&#39; (ISK)

Rupia india &#39;INR&#39; (INR)

Rupia indonesia (IDR)

Derechos especiales de giro (XDR) del Fondo Monetario Internacional

Rial iraní &#39;IRR&#39; (IRR)

Dinar Iraquí &#39;IQD&#39; (IQD)

Libra de la Isla de Man &#39;IMP&#39; (IMP)

&#39;ILS&#39; Nuevo shéquel israelí (ILS)

Dólar jamaiquino &#39;JMD&#39; (JMD)

Yen japonés &quot;JPY&quot; (JPY)

Libra de Jersey &#39;JEP&#39; (JEP)

Dinar jordano &#39;JOD&#39; (JOD)

Tenge kazajo &#39;KZT&#39; (KZT)

Chelín keniano &#39;KES&#39; (KES)

Dinar kuwaití &quot;KWD&quot;

Som kirguís &#39;KGS&#39; (KGS)

Kips de Laos &#39;LAK&#39; (LAK)

&#39;LVL&#39; Letonia latina (LVL)

Libra libanesa &#39;LBP&#39; (LBP)

Loti de Lesoto &#39;LSL&#39; (LSL)

Dólar liberiano &#39;LRD&#39; (LRD)

Dinar libio &#39;LYD&#39; (LYD)

LTL Lituania Litai (LTL)

&#39;MOP&#39; Patacas de Macao (MOP)

Denar macedonio &#39;MKD&#39; (MKD)

Ariario malgache &#39;MGA&#39; (MGA)

Kwacha malauí &#39;MWK&#39; (MWK)

Ringgits malayos &#39;MYR&#39; (MYR)

Rupia de Maldivas &#39;MVR&#39; (MVR)

&quot;MTL&quot; Malta Liri (MTL)

&#39;MRO&#39; Uguiyas mauritanas (MRO)

Rupia mauritana &#39;MUR&#39; (MUR)

Peso mexicano &#39;MXN&#39; (MXN)

Lei moldavo &#39;MDL&#39; (MDL)

Tugriks de Mongolia &#39;MNT&#39; (MNT)

Dirham marroquí &#39;MAD&#39; (MAD)

Meticais mozambiqueño &#39;MZN&#39; (MZN)

Meticais mozambiqueño &#39;MZM&#39; (MZM)

Kyats de Myanmar (MMK)

Dólar &quot;NAD&quot; de Namibia (NAD)

Rupia nepalesa &#39;NPR&#39; (NPR)

Florín de las Antillas Neerlandesas (ANG)

Dólar neozelandés &quot;NZD&quot; (NZD)

&#39;NIO&#39; Nicaragua Córdobas (NIO)

Nairas de Nigeria &#39;NGN&#39; (NGN)

Won norcoreano &#39;KPW&#39; (KPW)

Corona noruega &#39;NOK&#39; (NOK)

Riales omaníes (OMR)

Rupia pakistaní &#39;PKR&#39; (PKR)

Onzas de paladio &#39;XPD&#39; (XPD)

Balboas panameñas &quot;PAB&quot; (PAB)

Kina de Papúa Nueva Guinea (PGK)

&#39;PYG&#39; Paraguay Guarani (PYG)

Nuevo sol peruano (PEN)

Peso filipino &#39;PHP&#39; (PHP)

Onzas de platino &#39;XPT&#39; (XPT)

Zloty polaco &#39;PLN&#39; (PLN)

&#39;QAR&#39; Riyals de Qatar (QAR)

&quot;ROL&quot; Rumania Lei (ROL)

Nuevo lei rumano (RON)

Rublos rusos &#39;RUB&#39; (RUB)

Rublo ruso &#39;RUR&#39; (RUR)

Franco ruandés &#39;RWF&#39; (RWF)

Libra de Santa Helena (SHP)

Tala de Samoa &#39;WST&#39; (WST)

Dobra de Santo Tomé y Príncipe (STD)

Riyals de Arabia Saudita &#39;SAR&#39; (SAR)

&#39;SPL&#39; Seborga Luigini (SPL)

Dinar serbio &#39;RSD&#39; (RSD)

Dinar serbio &#39;CSD&#39; (CSD)

Rupia &#39;SCR&#39; de Seychelles (SCR)

&quot;SLL&quot; Sierra Leona Leones (SLL)

Onzas de plata &#39;XAG&#39; (XAG)

Dólar singapurense &#39;SGD&#39; (SGD)

Corona eslovaca &#39;SKK&#39; (SKK)

Tólar esloveno &#39;SIT&#39; (SIT)

Dólar &#39;SBD&#39; de las Islas Salomón (SBD)

Chelín somalí &#39;SOS&#39; (SOS)

Rand sudafricano &#39;ZAR&#39; (ZAR)

Won surcoreano &#39;KRW&#39; (KRW)

Rupia de Sri Lanka &#39;LKR&#39; (LKR)

Dinar sudanés &#39;SDD&#39; (SDD)

Libra sudanesa &#39;SDG&#39; (SDG)

Dólar surinamés &#39;SRD&#39; (SRD)

Florín surinamés &#39;SRG&#39; (SRG)

&#39;SZL&#39; Suazilandia Emalangeni (SZL)

Corona sueca &#39;SEK&#39; (SEK)

Franco suizo &#39;CHF&#39; (CHF)

Libra siria &#39;SYP&#39; (SYP)

&#39;TWD&#39; Nuevo dólar taiwanés (TWD)

&#39;TJS&#39; Somoni de Tayikistán (TJS)

Chelín tanzano &#39;TZS&#39; (TZS)

Baht tailandés &#39;THB&#39; (THB)

Pa&#39;anga tonga &#39;TOP&#39; (TOP)

Dólar &#39;TTD&#39; de Trinidad y Tobago (TTD)

Dinar tunecino &#39;TND&#39; (TND)

&#39;TRY&#39; Lira turca (TRY)

&quot;TRL&quot; Liras turcas (TRL)

&#39;TMM&#39; Manat turcomano (TMM)

&#39;TMT&#39; Turkmenistán Nuevos manat (TMT)

Dólar tuvaluano &#39;TVD&#39; (TVD)

Chelín ugandés &#39;UGX&#39; (UGX)

Hryvnia ucraniana &#39;UAH&#39; (UAH)

Dirham de Emiratos Árabes Unidos (AED)

Libra esterlina &quot;GBP&quot; del Reino Unido (GBP)

Dólares de los EE.UU. seleccionados como &quot;USD&quot;

Peso uruguayo &#39;UYU&#39; (UYU)

&#39;UZS&#39; suma uzbeka (UZS)

Vatu VUV de Vanuatu (VUV)

&#39;VEB&#39; Bolívar venezolano (VEB)

&#39;VEF&#39; Venezuela Bolivares Fuertes (VEF)

Dong vietnamita &#39;VND&#39; (VND)

Rial yemení &#39;YER&#39; (YER)

Kwacha zambiano &#39;ZMK&#39; (ZMK)

&#39;ZMW&#39; Kwacha zambiano (ZMW)

Dólar zimbabuense &#39;ZWD&#39; (ZWD)


## Ejemplo de AppMeasurement.js

La `currencyCode` variable se puede definir globalmente en el archivo AppMeasurement.js. La definición de la variable currencyCode en este archivo garantiza que todas las transacciones de moneda utilicen un código de moneda uniforme. El ejemplo siguiente especifica Euros como la `currencyCode` variable en el `CONFIG SECTION` archivo AppMeasurement.js. Todos los eventos de compra se interpretarán mediante informes como transacciones en &quot;euros&quot;.

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
s.account="devnow"
s.currencyCode="EUR"
s.trackInlineStats=true 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
***
    
```

Para obtener más información sobre la edición del archivo AppMeasurement.js, consulte [Inserción de código en el archivo](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)AppMeasurement.js.

## Notas adicionales acerca de la implementación

* Tenga en cuenta que, si bien los códigos de moneda pueden cambiar entre páginas, todos los elementos de línea de conversión definidos en una solicitud de página determinada deben utilizar la misma moneda (por ejemplo, no puede tener euros, libras esterlinas y dólares estadounidenses definidos en la misma vista de página). Si no desea realizar ninguna conversión de moneda, debe dejar el valor currencyCode en blanco. Esto hace que los valores enviados se pasen directamente a los informes sin conversión.

* Si se establece un currencyCode no válido (cualquier valor que no esté en la lista de códigos de moneda admitidos), se excluirá toda la visita y no se recopilarán los datos de esa transacción. Antes de configurarlo `currencyCode` en producción, utilice un grupo de informes de prueba para verificar que los datos se recopilen y que la conversión de moneda sea correcta.

* Las monedas que no utilizan punto (.) como separador se deben modificar para que utilicen un punto en lugar del separador habitual. Por ejemplo: la corona sueca, que emplea una coma (,), deberá modificarse de modo que utilice un punto en lugar de una coma. Analytics utiliza la coma para separar valores y los datos no se pasarán correctamente. El período pasa correctamente el valor a los informes.
