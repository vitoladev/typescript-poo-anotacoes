# Herança

A herança acontece quando uma classe herda todos os atributos e métodos de outra classe. No typescript a palavra que simboliza a herança é a extends.

Exemplo:

```typescript
class Pessoa { 
    constructor( 
      public nome: string,
      public sobrenome: string, 
) {}
getIdade(): number { 
return this.idade; 
  }
getCpf(): string { 
return this.cpf;
  }
 getNomeCompleto(): string { 
return this.nome + ' ' + this.sobrenome;
   }
 }
// Classe que herda de Pessoa
class Aluno extends Pessoa { 
 getNomeCompleto(): string { 
   return 'Isso vem do aluno: ' + this.nome + ' ' + this.sobrenome; 
  }
}
```

