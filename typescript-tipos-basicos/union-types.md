# Union Types

Quando algo pode ter tipos diferentes, o UNION type pode ser usado, o | significa OU, logo no exemplo abaixo os parametros da função podem ter o tipo Number OU String OU Boolean, representados como number | string | boolean

Exemplo:

```javascript
function addOrConcat( 
a: number | string | boolean, 
b: number | string | boolean): number | string { 
 if (typeof a === 'number' && typeof b === 'number') 
   return a + b; return ${a}${b};
}
```

``
