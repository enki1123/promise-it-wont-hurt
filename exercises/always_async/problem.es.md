# ¿Las promesas siempre se resuelven de forma asíncrona?

La especificación ES2015 establece que las promesas **no deben** activar su función de resolución/rechazo en el mismo ciclo del bucle de eventos en el que son creadas. Esto es muy importante porque elimina la posibilidad de que el orden de ejecución varíe y resulte en resultados indeterminados.

Puedes esperar que las funciones pasadas al método `then` de una promesa se ejecuten en el **próximo** ciclo del bucle de eventos.

## Tarea

En esta lección, vamos a demostrar que las promesas siempre son asíncronas.

Primero, crea una promesa utilizando el constructor `Promise`.

En el `executor` de la promesa, cumple inmediatamente la promesa con un valor de `'VALOR DE LA PROMESA'`.

Después de la creación de la promesa, pasa `console.log` como el manejador de éxito de la promesa.

Finalmente, imprime "PROGRAMA PRINCIPAL" con `console.log`.

## Pistas

Si la ejecución de la promesa es síncrona, el valor de la promesa ya se conoce después de su construcción. El `console.log` pasado a `then` se ejecutaría tan pronto como se llame a `then`.

Sin embargo, si tu script es exitoso, deberías ver "PROGRAMA PRINCIPAL" antes de "VALOR DE LA PROMESA".

Esto te muestra que a pesar de que la promesa se resuelve de forma síncrona, la función proporcionada no se ejecuta hasta el próximo ciclo del bucle de eventos.