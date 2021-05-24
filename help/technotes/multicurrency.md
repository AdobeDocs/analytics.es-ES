---
description: Describe cómo definir códigos de moneda de destino para que funcione la compatibilidad con múltiples monedas.
title: Compatibilidad con múltiples monedas
uuid: null
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: f3eb3c024a80d0b65729929960173f8b3a4267b0
workflow-type: tm+mt
source-wordcount: '1358'
ht-degree: 100%

---

# Compatibilidad con múltiples monedas

Este documento describe cómo definir códigos de moneda de destino para que funcione la compatibilidad con múltiples monedas.

Los códigos de moneda de destino se definen en tres niveles:

## Nivel de página

Puede establecer una variable de JavaScript para la moneda de destino en el nivel de página. El propietario del sitio puede configurar esta variable usando el código de moneda de tres letras correcto según la norma ISO 4217 (los códigos figuran más adelante en este documento). Si la variable [currencyCode](https://docs.adobe.com/content/help/es-ES/analytics/implementation/vars/config-vars/currencycode.html) no está configurada en este nivel, la moneda predeterminada será la misma que la especificada en el grupo de informes. Si la variable en el nivel de página entra en conflicto con la variable especificada en el grupo de informes, la variable en el grupo de informes tendrá prioridad.


## Nivel del grupo de informes

La **moneda de base** se especifica al [crear grupos de informes](https://docs.adobe.com/content/help/es-ES/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html). Esta es la configuración predeterminada para la moneda y tiene prioridad sobre los códigos de moneda establecidos en el nivel de página. Por lo tanto, si un grupo de informes tiene pedidos que aceptan dólares estadounidenses, euros y libras esterlinas, y si el grupo de informes tiene definido el código de moneda predeterminado de “dólares estadounidenses”, la base de datos de creación de informes del backend convertirá todas las transacciones a dólares estadounidenses.

Los informes de marketing utilizan el tipo de cambio disponible en el momento en el que se produce la solicitud de imagen para convertir los valores monetarios del nivel de página a los valores de moneda predeterminados del grupo de informes. Los grupos de informes utilizarán “dólares estadounidenses” como moneda predeterminada.


## Nivel de informe

En este nivel se puede establecer la moneda predeterminada para los informes de la sesión de un usuario. Se puede acceder a esta opción a través del vínculo **Opciones de visualización** de cualquier informe de conversión. Los informes de marketing utilizan el tipo de cambio disponible en el momento en el que se ejecuta el informe para convertir los valores monetarios del grupo de informes a los valores de moneda especificados para el informe.

## Códigos de moneda admitidos (ISO 4217)

Actualmente, Analytics admite los siguientes formatos de moneda para las transacciones de conversión:


‘AFA’ Afganis de Afganistán (AFA)

‘AFN’ Afganis de Afganistán (AFN)

‘ALL’ Leke albanés (ALL)

‘DZD’ Dinar argelino (DZD)

‘AOA’ Kwanza angoleño (AOA)

‘ARS’ Peso argentino (ARS)

‘AMD’ Drams armenios (AMD)

‘AWG’ Florín arubeño (AWG)

‘AUD’ Dólar australiano (AUD)

‘AZM’ Manat azerbaiyano (AZM)

‘AZN’ Nuevo manat azerbaiyano (AZN)

‘BSD’ Dólar bahameño (BSD)

‘BHD’ Dinar bahreiní (BHD)

‘BDT’ Taka bangladesí (BDT)

‘BBD’ Dólar de Barbados (BBD)

‘BYR’ Rublo bielorruso (BYR)

‘BZD’ Dólar beliceño (BZD)

‘BMD’ Dólar bermudeño (BMD)

‘BTN’ Ngultrum butanés (BTN)

‘BOB’ Bolivianos de Bolivia (BOB)

‘BAM’ Marco convertible de Bosnia y Herzegovina (BAM)

‘BWP’ Pulas de Botsuana (BWP)

‘BRL’ Reales brasileños (BRL)

‘BND’ Dólares de Brunei (BND)

‘BGN’ Leva de Bulgaria (BGN)

‘BIF’ Francos burundianos (BIF)

‘KHR’ Rieles camboyanos (KHR)

‘CAD’ Dólar canadiense (CAD)

‘CVE’ Escudo caboverdiano (CVE)

‘KYD’ Dólar de las Islas Caimán (KYD)

‘CLP’ Peso chileno (CLP)

‘CNY’ Yuan renminbi chino (CNY)

‘COP’ Peso colombiano (COP)

‘XOF’ Franco CFA de África Occidental (XOF)

‘XAF’ Franco CFA de África Central (XAF)

‘KMF’ Franco comorense (KMF)

‘XPF’ Franco pacífico francés o franco del CFP (Sucursal Francesa del Pacífico) (XPF)

‘CDF’ Franco congoleño (CDF)

‘CRC’ Colón costarricense (CRC)

‘HRK’ Kuna croata (HRK)

‘CUC’ Peso convertible cubano (CUC)

‘CUP’ Peso cubano (CUP)

‘CYP’ Libra chipriota (CYP)

‘CZK’ Corona checa (CZK)

‘DKK’ Corona danesa (DKK)

‘DJF’ Francos de Djibouti (DJF)

‘DOP’ Peso dominicano (DOP)

‘XCD’ Dólar del Caribe Oriental (XCD)

‘EGP’ Libra egipcia (EGP)

‘SVC’ Colón salvadoreño (SVC)

‘ERN’ Nakfa de Eritrea (ERN)

&#39;XBT&#39; ERR (XBT)

‘EEK’ Krooni estonio (EEK)

‘ETB’ Birr etíope (ETB)

‘EUR’ Euro (EUR)

‘FKP’ Libra malvinense (FKP)

‘FJD’ Dólar fijiano (FJD)

‘GMD’ Dalasi de Gambia (GMD)

‘GEL’ Lari de Georgia (GEL)

‘GHC’ Cedis de Ghana (GHC)

‘GHS’ Cedis de Ghana (GHS)

‘GIP’ Libra gibraltareña (GIP)

‘XAU’ Onzas de oro (XAU)

‘GTQ’ Quetzales guatemaltecos (GTQ)

‘GGP’ Libra de Guernsey (GGP)

‘GNF’ Franco guineano (GNF)

‘GYD’ Dólar guyanés (GYD)

‘HTG’ Gourdes haitianos (HTG)

‘HNL’ Lempiras hondureñas (HNL)

‘HKD’ Dólar de Hong Kong (HKD)

‘HUF’ Florín húngaro (HUF)

‘ISK’ Corona islandesa (ISK)

‘INR’ Rupia india (INR)

‘IDR’ Rupia indonesia (IDR)

‘XDR’ Derechos especiales de giro del Fondo Monetario Internacional (XDR)

‘IRR’ Rial iraní (IRR)

‘IQD’ Dinar Iraquí (IQD)

‘IMP’ Libra manesa (IMP)

‘ILS’ Nuevo shéquel israelí (ILS)

‘JMD’ Dólar jamaicano (JMD)

‘JPY’ Yen japonés (JPY)

‘JEP’ Libra de Jersey (JEP)

‘JOD’ Dinar jordano (JOD)

‘KZT’ Tenge kazajo (KZT)

‘KES’ Chelín keniano (KES)

‘KWD’ Dinar kuwaití (KWD)

‘KGS’ Som kirguí (KGS)

‘LAK’ Kips de Laos (LAK)

‘LVL’ Lat letón (LVL)

‘LBP’ Libra libanesa (LBP)

‘LSL’ Maloti de Lesotho (LSL)

‘LRD’ Dólar liberiano (LRD)

‘LYD’ Dinar libio (LYD)

‘LTL’ Litai lituano (LTL)

‘MOP’ Patacas de Macao (MOP)

‘MKD’ Dinar macedonio (MKD)

‘MGA’ Ariary malgache (MGA)

‘MWK’ Kwacha malauí (MWK)

‘MYR’ Ringgits malayos (MYR)

‘MVR’ Rupia maldiva (MVR)

‘MTL’ Lira maltesa (MTL)

‘MRO’ Uguiyas mauritanas (MRO)

‘MUR’ Rupia de Mauricio (MUR)

‘MXN’ Peso mexicano (MXN)

‘MDL’ Lei moldavo (MDL)

‘MNT’ Tugriks de Mongolia (MNT)

‘MAD’ Dirham marroquí (MAD)

‘MZN’ Metical mozambiqueño (MZN)

‘MZM’ Metical mozambiqueño (MZM)

‘MMK’ Kyats de Myanmar (MMK)

‘NAD’ Dólar de Namibia (NAD)

‘NPR’ Rupia nepalesa (NPR)

‘ANG’ Florín antillano holandés (ANG)

‘NZD’ Dólar neozelandés (NZD)

‘NIO’ Córdobas nicaragüenses (NIO)

‘NGN’ Nairas nigerianas (NGN)

‘KPW’ Won norcoreano (KPW)

‘NOK’ Corona noruega (NOK)

‘OMR’ Riales omaníes (OMR)

‘PKR’ Rupia pakistaní (PKR)

‘XPD’ Onzas de paladio (XPD)

‘PAB’ Balboas panameñas (PAB)

‘PGK’ Kina de Papúa Nueva Guinea (PGK)

‘PYG’ Guaraní paraguayo (PYG)

‘PEN’ Nuevo sol peruano (PEN)

‘PHP’ Peso filipino (PHP)

‘XPT’ Onzas de platino (XPT)

‘PLN’ Zloty polaco (PLN)

‘QAR’ Rial catarí (QAR)

‘ROL’ Leu rumano (ROL)

‘RON’ Nuevo leu rumano (RON)

‘RUB’ Rublos rusos (RUB)

‘RUR’ Rublos rusos (RUR)

‘RWF’ Franco ruandés (RWF)

‘SHP’ Libra de Santa Helena (SHP)

‘WST’ Tala de Samoa (WST)

‘STD’ Dobra de Santo Tomé y Príncipe (STD)

‘SAR’ Riyal saudí (SAR)

‘SPL’ Luigini de Seborga (SPL)

‘RSD’ Dinar serbio (RSD)

‘CSD’ Dinar serbio (CSD)

‘SCR’ Rupia de Seychelles (SCR)

‘SLL’ Leone de Sierra Leona (SLL)

‘XAG’ Onzas de plata (XAG)

‘SGD’ Dólar singapurense (SGD)

‘SKK’ Corona eslovaca (SKK)

‘SIT’ Tolar esloveno (SIT)

‘SBD’ Dólar de las Islas Salomón (SBD)

‘SOS’ Chelín somalí (SOS)

‘ZAR’ Rand sudafricano (ZAR)

‘KRW’ Won surcoreano (KRW)

‘LKR’ Rupia esrilanquesa (LKR)

‘SDD’ Dinar sudanés (SDD)

‘SDG’ Libra sudanesa (SDG)

‘SRD’ Dólar surinamés (SRD)

‘SRG’ Florín surinamés (SRG)

‘SZL’ Emalangeni de Suazilandia (SZL)

‘SEK’ Corona sueca (SEK)

‘CHF’ Franco suizo (CHF)

‘SYP’ Libra siria (SYP)

‘TWD’ Nuevo dólar taiwanés (TWD)

‘TJS’ Somoni de Tayikistán (TJS)

‘TZS’ Chelín tanzano (TZS)

‘THB’ Baht tailandés (THB)

‘TOP’ Pa‘anga de Tonga (TOP)

‘TTD’ Dólar de Trinidad y Tobago (TTD)

‘TND’ Dinar tunecino (TND)

‘TRY’ Lira turca (TRY)

‘TRL’ Lira turca (TRL)

‘TMM’ Manat turcomano (TMM)

‘TMT’ Nuevo manat turcomano (TMT)

‘TVD’ Dólar tuvaluano (TVD)

‘UGX’ Chelín ugandés (UGX)

‘UAH’ Grivna ucraniana (UAH)

‘AED’ Dirham de Emiratos Árabes Unidos (AED)

‘GBP’ Libra esterlina (GBP)

‘USD’ Dólar estadounidense (USD)

‘UYU’ Peso uruguayo (UYU)

‘UZS’ Som uzbeko (UZS)

‘VUV’ Vatu de Vanuatu (VUV)

‘VEB’ Bolívar venezolano (VEB)

‘VEF’ Bolívar fuerte venezolano (VEF)

‘VND’ Dong vietnamita (VND)

‘YER’ Rial yemení (YER)

‘ZMK’ Kwacha zambiano (ZMK)

‘ZMW’ Kwacha zambiano (ZMW)

‘ZWD’ Dólar zimbabuense (ZWD)


## Ejemplo de AppMeasurement.js

La variable `currencyCode` se puede definir globalmente en el archivo AppMeasurement.js. Definir la variable currencyCode en este archivo garantiza que todas las transacciones monetarias utilicen un código de moneda homogéneo. El ejemplo siguiente especifica Euros como la variable `currencyCode` en la `CONFIG SECTION` del archivo AppMeasurement.js. El sistema de informes interpretará todos los eventos de compra como transacciones en “euros”.

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

## Notas adicionales acerca de la implementación

* Tenga en cuenta que, si bien los códigos de monedas pueden cambiar de página a página, todos los elementos de línea de conversión definidos en una determinada solicitud de página deben utilizar la misma moneda (por ejemplo, no es posible tener euros, libras esterlinas y dólares estadounidenses definidos en la misma vista de página). Si no desea realizar ninguna conversión de moneda, debe dejar el valor currencyCode en blanco. Esto hace que los valores enviados pasen directamente a los informes sin conversión.

* Si se establece un currencyCode no válido (cualquier valor que no esté en la lista de códigos de moneda admitidos), se excluirá toda la visita y no se recopilarán los datos de esa transacción. Antes de configurar `currencyCode` en producción, utilice un grupo de informes de prueba para verificar que los datos se recopilen y que la conversión de moneda sea correcta.

* Las monedas que no utilizan punto (.) como separador se deben modificar para que utilicen un punto en lugar del separador habitual. Por ejemplo: la corona sueca, que emplea una coma (,), deberá modificarse de modo que utilice un punto en lugar de una coma. Analytics utiliza la coma para separar valores, por lo que los datos no se transferirían correctamente. Si se utiliza un punto, los valores se transmitirán correctamente a los informes.
