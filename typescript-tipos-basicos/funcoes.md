# Funções

Os tipos em funções são muito simples, você envia os parâmetros no tipo e no retorno, que é depois de :

nos Type Alias o retorno é depois de =>

Exemplos:

```typescript
// Type alias         Tipo do parâmetro    retorno
type MapStringsCallback = (item: string) => string;

//               Tipo do parâmetro   retorno
function enviaMensagem(msg: string): string {
    return msg;
}

console.log(enviaMensagem('Mensagem enviada');
```

``
