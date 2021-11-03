# L. Liskov Substituion Principle

Liskov substitution principle (Princípio de substituição de Liskov) - Se o(x) é uma propriedade dmonstrável dos objetos x de tipo T. Então o(y) deve ser verdadeiro para objetos y de tipo S onde S é um subtipo de T. Simplificando, subtipos precisam ser substituíveis por seus tipos de base, não podendo alterar o comportamento do Tipo no Subtipo. No exemplo quebra o príncipio pois ele altera o comportamento da classe abstrata que ele herda.

Exemplo:

```typescript
export abstract class Discount {
  protected discount = 0;

  calculate(price: number): number {
    return price - price * this.discount;
  }
}

export class NoDiscount extends Discount {
  
  calculate(price: number): number {
    return price;
  }
}
```
