# Never

Diz que a função nunca vai retornar nada, normalmente esse tipo é usado para enviar erros.

Exemplo:&#x20;

```typescript
export function criaErro(): never { 
   throw new Error('Erro qualquer')
};
```

``
