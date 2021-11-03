# Decorators

Decorators funcionam como um objeto impostor, que finge ser seu objeto e pode decorar seu objeto, podendo observar, modificar ou substituir seu objeto. No exemplo a função decoradora decora a classe animal sendo uma classe filha dela, invertendo seus atributos. para o decorator ser chamado basta você colocar @nomedodecorator antes da classe que você quer chamar.

```typescript
@inverteAtributos // chamando decorator
export class Animal {
  constructor(public nome: string, public cor: string) {}
}

function inverteAtributos<T extends new (...args: any[]) => any>(target: T): T {
  // Decorator recebe a classe e decora ela
  return class extends target { // target é a classe que vai ser decorada
    cor: string;
    nome: string;

    constructor(...args: any[]) {
      super(...args);
      this.nome = this.inverte(args[0]);
      this.cor = this.inverte(args[1]);
    }

    inverte(valor: string): string {
      return valor.split('').reverse().join('');
    }
  };
}

const animal = new Animal('Lobo', 'Cinza');
console.log(animal);
```
