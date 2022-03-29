# week2_day2
Context, function invocation &amp; parameters, object destructuring, spread op, async methods, variable scope


## Main points: functions

A nivel de nomenclatura, existen:

- **Funciones nominales**: disponen de declaración e invocación, con alta reusabilidad.
  ````javascript
  function sayHi(name){
    console.log(`¡Hola, ${name}!`)
  }
  ````
- **Funciones anónimas**: no disponen de declaración, solo de invocación. Usadas en un único contexto.
  ````javascript
  names.forEach(function(elm) => {
     console.log(`¡Hola, ${elm}!`)
  })
  ````
  
A nivel de estructura, existen: 
- **Function statement**: _hoisted_, disponen de al palabra reservada `function`, de paréntesis para sus parámetros y de bloque:
  ````javascript
  function getTotals(subtotal, tax){
    return subtotal + tax
  }
  ````
- **Function expression**: no _hoisted_, asignan a una constante o variable una función anónima - ya sea arrow o `function`.
  ````javascript
  const getTotals = function(subtotal, tax) {
    return subtotal + tax
  }
  ````
Las funciones pueden recibir argumentos en forma de parámetros, y retornar datos. Es posible implementar como último parámetro el operador de propagación para crear un array con los parámetros restantes (REST PARAMETERS):
  ````javascript
  const getInvoiceTotal = (tax, ...products) => tax + products.reduce((acc, product) => acc + produc.price, 0)
  ````
  
## Main points: variable scope
- Las variables declaradas dentro de un bloque o función se denominan **locales** o **privadas**, accesibles únicamente dentro de ese contexto.
- Las variables declaradas fuera de cualquier bloque o función se denominan **globales** o **públicas**, accesibles desde cualquier parte del script.


## Main points: async programming

- Javascript es un lenguaje <strong>de subproceso único</strong> (<a href="https://en.wikipedia.org/wiki/Thread_(computing)#Single_threading">single-threaded</a>), por lo que no puede performar múltiples tareas a la vez.
- Asimismo es <strong>síncrono</strong>, dado que las tareas se ejecutan una detrás de otra siguiendo la secuencia del programa, donde tareas de alto coste en términos de tiempo generan cuellos de botella naturales en el flujo de la misma.
- En base a esta naturaleza, dispone de diversos recursos de carácter asíncrono que permiten gestionar tareas programadas y/o paralelas. Entre ellos, encontramos métodos no bloqueantes como `.setTimeout()` o `.setInterval()`.

## Main points: callbacks

Un <em>callback</em> es una función que recibe como parámetro otra función, invocándola en su interior:
````javascript
function foo = callback => callback()
````
