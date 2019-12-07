---
description: El complemento getValOnce evita que una determinada variable se establezca en el valor definido anteriormente. Para determinar el último valor visto de una variable, el complemento utiliza una cookie. Si el valor actual coincide con el valor de la cookie, la variable se sobrescribe con una cadena vacía antes de ser remitida a los servidores de procesamiento de Adobe. Este complemento resulta útil para evitar la inflación de instancias de variables de conversión que se produce cuando los usuarios actualizan la página o hacen clic en el botón Atrás.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getValOnce
topic: Developer and implementation
uuid: 82fe0da5-3bc4-4632-8c62-7b5683f6b587
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getValOnce

El complemento getValOnce evita que una determinada variable se establezca en el valor definido anteriormente. Para determinar el último valor visto de una variable, el complemento utiliza una cookie. Si el valor actual coincide con el valor de la cookie, la variable se sobrescribe con una cadena vacía antes de ser remitida a los servidores de procesamiento de Adobe. Este complemento resulta útil para evitar la inflación de instancias de variables de conversión que se produce cuando los usuarios actualizan la página o hacen clic en el botón Atrás.

>[!IMPORTANT]
>
>Este complemento no se ha validado para que sea compatible con [AppMeasurement para JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md). Consulte [Asistencia del complemento de AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).

**Parámetros**

```js
s.eVar1=s.getValOnce(variable,cookie,expiration,minute);
```

* **Variable:** la variable que se va a comprobar. Normalmente es la misma variable que se está definiendo.
* **Cookie**: nombre de la cookie que almacena el valor anterior con el que se realizará la comparación. Puede ser cualquier valor.
* (Opcional) **Caducidad:** número de días hasta la caducidad de la cookie. Si no se define o se define en 0, la caducidad predeterminada será la sesión del explorador.
* (Opcional) **Minuto:** si se establece en el valor de cadena *`m`*, el valor de caducidad se definirá en minutos en vez de días. Si no se establece, *`days`* es la caducidad predeterminada.

**Propiedades**

* Este complemento se usa generalmente en variables de conversión. No obstante, se puede utilizar en cualquier variable de [!DNL Analytics].
* Cuando JavaScript detecta esta función, compara el valor definido con el valor almacenado en la cookie. Si el valor definido es distinto al valor de la cookie, se establece el valor definido. Si el valor definido es el mismo que el valor de la cookie, se devuelve una cadena vacía.
* La cookie solo puede almacenar un único valor, lo que significa que para el complemento solo es importante el último valor definido.
* El complemento no impide que todos los valores puedan definir la variable una vez que esté definida. Solo evita que el último valor se defina varias veces de manera consecutiva.
* Si el usuario final bloquea o rechaza las cookies, siempre se devolverá el valor original.
* La sesión del complemento es diferente a lo que [!DNL Analytics] define como una sesión (o visita). [!DNL Analytics] finaliza una sesión tras 12 horas de actividad o 30 minutos de inactividad. Dado que el complemento utiliza la definición de sesión del explorador, solo finalizará cuando el usuario cierre la pestaña o salga del explorador.

   * Si un usuario cierra la página, abre una pestaña diferente y regresa al sitio en los próximos 30 minutos, el complemento creará una sesión nueva y mantendrá abierta la visita de [!DNL Analytics].
   * Si un usuario mantiene abierta la ventana del explorador sin hacer clic en ningún vínculo durante más de 30 minutos, la visita de [!DNL Analytics] caducará mientras que la sesión del explorador se mantendrá abierta.

> [!NOTE] Las instrucciones siguientes exigen modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

## Implementación {#section_177FF7F425B64FFB83CDE15A6ACC8D21}

> [!NOTE]Si su organización utiliza canales de marketing y tiene configuradas reglas basadas en `s.campaign`, se recomienda que no utilice el complemento getValOnce al establecer el valor de `s.campaign`. De hacerlo, podría asignarse un canal incorrecto en una pulsación de una campaña secundaria.

Para implementar este complemento, inserte el código siguiente en el archivo [!DNL s_code.js].

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getValOnce_v1.11 
 */ 
s.getValOnce=new Function("v","c","e","t","" 
+"var s=this,a=new Date,v=v?v:'',c=c?c:'s_gvo',e=e?e:0,i=t=='m'?6000" 
+"0:86400000,k=s.c_r(c);if(v){a.setTime(a.getTime()+e*i);s.c_w(c,v,e" 
+"==0?0:a);}return v==k?'':v");
```

Una vez que implemente el código de arriba, defina la variable deseada mediante la función *`getValOnce`*. A continuación se indican varios ejemplos de implementación:

**Impedir que se defina el mismo valor de campaign si se detecta un valor duplicado en los 30 días siguientes a la configuración de la cookie:** `s.campaign=s.getValOnce(s.campaign,'s_cmp',30);`  **Evita que se defina el mismo valor de eVar1 si se detecta un valor duplicado en los 30 minutos siguientes a la configuración de la cookie:**
`s.eVar1=s.getValOnce(s.eVar1,'s_ev1',30,'m');`  **Evita que el mismo valor de eVar2 se defina varias veces en la misma sesión del explorador:**
`s.eVar2=s.getValOnce(s.eVar2,'s_ev2');`  **Notas**

* Antes de su implementación en un entorno de desarrollo, realice pruebas exhaustivas de las instalaciones de complementos para asegurarse de que la recopilación de datos se comporta según lo esperado.
* Asegúrese de eliminar la cookie o usar valores nuevos únicos durante la prueba, ya que, de lo contrario, las variables no se enviarán.

