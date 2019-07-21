---
description: Si se produce un error, se notifica en la columna Estado del trabajo.
keywords: Fuente de datos; trabajo; solución de problemas; error; ftp; chdir; connect; login; put
seo-description: Si se produce un error, se notifica en la columna Estado del trabajo.
seo-title: Solución de problemas de los trabajos
solution: Analytics
title: Solución de problemas de los trabajos
uuid: 8 fbb 914 e -03 db -434 e-b 4 d 3-8594144 ff 2 b 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Solución de problemas de los trabajos

Si se produce un error, se notifica en la columna Estado del trabajo.

A continuación, se indican los errores y sus posibles causas:

<table id="table_BE2921B8E7C94B0EB88774321B8692F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Error </th> 
   <th colname="col2" class="entry"> Posibles causas </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Error Chdir de FTP </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_79AB3EA974CC46A0A645A439BC612D88"> 
      <li id="li_4A6A5922275946908E06499E8EAAF18B"> Error de la red o del servidor de destino </li> 
      <li id="li_33393FF286624A63B12991DCE079841D">Problema de permiso de lectura/escritura </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Error de conexión al FTP </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5F926078850D4495B83BC938395CAC6B"> 
      <li id="li_A72A357F6289438EA1A091AC4FD3A3D0"> Problema de autenticación </li> 
      <li id="li_48532C78285E4DB6A47B1435A5FA549B"> Error de la red o del servidor de destino </li> 
      <li id="li_11DF6FA218CA48539C4561695234CA4D"> Problema de permiso de lectura/escritura </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Error de FTP </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_020BA1DC81F645FFABCAD07E51351D1E"> 
      <li id="li_8566EECEFD344BFDB638259474A8E8EA"> Disco lleno o cuota de disco superada </li> 
      <li id="li_15CD50ED54F846F79BFDF25359864C59"> Error de la red o del servidor de destino </li> 
      <li id="li_741A3315C0B940D3A9874F15C78B4F28"> Problema de permiso de lectura/escritura </li> 
      <li id="li_49F707F7F65A443F8AC6E058E3D89B96"> Problema de autenticación </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Error de inicio de sesión en el FTP </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_F7F128ADF1FD4E9D8B79424A6432378E"> 
      <li id="li_68C377CAD50346B1B9937B77E7EB2AAD"> Problema de autenticación </li> 
      <li id="li_7EA91C90FFC0493EA156292620EF1589"> Error de la red o del servidor de destino </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Error Put de FTP </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_760DA2CBD46B4C348BE3B7B43E803FD9"> 
      <li id="li_6578482722E14E998515B4B3EA370C44"> Disco lleno o cuota de disco superada </li> 
      <li id="li_342240DDD9D3423198C23123473D539C"> Error de la red o del servidor de destino </li> 
      <li id="li_44CEFE1D92A74842A6321C416637421F"> Problema de permiso de lectura/escritura </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>