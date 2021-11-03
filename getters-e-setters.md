# Getters e Setters

**Getter **é usado para ter o valor do atributo privado da classe

**Setter **é usado para configurar o valor do atributo privado da classe&#x20;

Ambos se comportam como atributos, logo quando você tenta acessar o CPF do exemplo abaixo com c**onsole.log(pessoa.cpf); **o que te retorna o valor do atributo cpf é o **getter**.

Quando você tenta mudar o valor do CPF com **pessoa.cpf = '123.456.798-99', **você está usando o setter, logo quando tem algum valor pra ser mudado o **setter **é chamado e quando é usado só pra pegar o valor é o **getter**

```typescript
class Pessoa { 
  constructor( 
    private nome: string, 
    private sobrenome: string, 
    private idade: number, 
    private _cpf: string, 
) { 
     this.cpf = _cpf;
 }
  set cpf(cpf: string) { 
       console.log('SETTER CHAMADO'); 
       this._cpf = cpf; 
    }
  get cpf(): string { 
       console.log('GETTER CHAMADO');
       return this._cpf.replace(/\D/g, ''); 
    } 
}
```

``
