# Intersection Types

os Intersection Types juntam os tipos com o &, que significa AND; Logo o tipo criado com intersection tem todas as características dos tipos que foram juntados

Exemplo:

```typescript
type TemNome = { nome: string }; 
type TemSobrenome = { sobrenome: string };
type TemIdade = { idade: number }; 
type Pessoa = TemNome & TemSobrenome & TemIdade; 
```

``
