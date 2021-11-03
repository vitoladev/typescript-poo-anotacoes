# Super

O super serve pra você ter acesso de dentro de uma subclasse as propriedades e métodos de uma super classe.&#x20;

Como no exemplo abaixo a subclasse chama o super para chamar os atributos da super classe e criar um  novo atributo pra si, chamado **sala. **e chama o método **getNomeCompleto() **da super classe utilizando o **super.getNomeCompleto()**

```typescript
export class Pessoa { 
constructor( 
  public nome: string, 
  public sobrenome: string, 
  private idade: number, 
  protected cpf: string, 
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

export class Aluno extends Pessoa { 
constructor( 
nome: string,
sobrenome: string,
idade: number, 
cpf: string, 
public sala: string, ) { 
  super(nome, sobrenome, idade, cpf); 
}
getNomeCompleto(): string { 
     console.log('FAZENDO ALGO ANTES'); 
     const result = super.getNomeCompleto(); 
     return result + ' resultado mudado!!';
 }
```

``
