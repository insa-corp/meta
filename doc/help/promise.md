# Promise

## Links

 * [Bluebird - Why Promises](http://bluebirdjs.com/docs/why-promises.html)
 * [MDN - Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

## Description

Promises are a functionnality to manage async operations.
It helps to disociate the parameters of the operation from the result's processing.

For example: you do not have to provide a callback at the function call & you can chain async operations.

## Error handling

On of the main strength of promises is that they simplify the error control flow to mimic a synchronous execution with
try/catch statements.

The promise logic is wrapped inside a function: this way, when a synchronous error is thrown, this error is catched
and handled as an async error so we just need to handle async errors.

Example (french): https://gist.github.com/Demurgos/905e4ead069770f64a38#file-asyncdivide-ts-L40

