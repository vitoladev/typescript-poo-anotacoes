# Static

Um método ou atributo estático não pode ser instanciado e não pode ser acessado pela instancia da classe, Apenas pela própria classe.

```typescript
class Pessoa { 
    static idadePadrao = 0; 
    static cpfPadrao = '000.000.000-00';
  constructor( 
    public nome: string, 
    public sobrenome: string, 
    public idade: number, 
    public cpf: string, ) {}
      metodoNormal(): void { 
          console.log(Pessoa.idadePadrao, Pessoa.cpfPadrao); 
      }
      static criaPessoa(nome: string, sobrenome: string): Pessoa {
      return new Pessoa(nome, sobrenome, Pessoa.idadePadrao, Pessoa.cpfPadrao); 
     }
}
```

``
