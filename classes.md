# Classes

Jeito mais longo de criar classes em typescript.

```typescript
class Empresa { 
     public readonly nome: string; 
     private readonly colaboradores: Colaborador[] = []; 
     protected readonly cnpj: string;
    constructor(nome: string, cnpj: string)  { 
    this.nome = nome; 
    this.cnpj = cnpj;
}
```

Jeito simplificado

```typescript
class Colaborador { 
    constructor( 
       public nome: string, 
       public sobrenome: string,
 ) {} 
}
```
