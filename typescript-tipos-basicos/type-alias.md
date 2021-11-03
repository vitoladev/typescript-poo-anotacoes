# Type Alias

É usado para criar um tipo e é util para reutiliza-lo pelo código, facilitando para não precisar digitar o tipo de todos os parâmetros de uma função de novo.

Exemplo:

```typescript
type Idade = number; 
type Pessoa = { 
   nome: string; 
   idade: Idade; 
   salario: number; 
   corPreferida?: string;
 };
```

``
