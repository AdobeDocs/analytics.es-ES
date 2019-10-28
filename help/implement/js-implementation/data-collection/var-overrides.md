---
description: Las anulaciones de variables permiten cambiar el valor de una variable para un único seguimiento o una sola llamada de seguimiento de vínculos.
keywords: Implementación de Analytics
seo-description: Las anulaciones de variables permiten cambiar el valor de una variable para un único seguimiento o una sola llamada de seguimiento de vínculos.
seo-title: Anulaciones de variables
solution: Analytics
subtopic: Variables
title: Anulaciones de variables
topic: Desarrollador e implementación
uuid: 3ec09ae8-b9df-426f-8065-42b4518e6c5f
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Anulaciones de variables

Las anulaciones de variables permiten cambiar el valor de una variable para un único seguimiento o una sola llamada de seguimiento de vínculos.

Para anular las variables, cree un nuevo objeto, asigne los posibles valores y pase el objeto como el primer parámetro a `s.t()` o como el cuarto a `s.tl()`:

```js
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
  
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
  
s.t(overrides);  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

```js
s.linkTrackVars="eVar1,eVar2,eVar3,events"; 
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
 
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
 
s.tl(this,'e','AnotherSite',overrides,'navigate')  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

