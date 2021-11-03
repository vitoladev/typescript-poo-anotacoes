# Tipos Literais

A chave nome tem o tipo 'Victor' por ele estar como const, logo não pode ter outro valor pois o tipo dela é 'Victor' e não pode ser mudado.

Exemplo:

```typescript
const pessoa = { 
  nome: 'Victor' as const, 
  sobrenome: 'Oliveira', 
};
```

``
