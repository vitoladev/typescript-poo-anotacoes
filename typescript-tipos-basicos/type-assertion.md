# Type Assertion

Type Assertion é converter o tipo para quando você ter certeza que algo existe, para o elemento não poder ser possivelmente undefined, refinando o tipo.

Exemplo:

```javascript
const body3 = document.querySelector('body') as HTMLBodyElement; 
body3.style.background = 'red';
```

``
