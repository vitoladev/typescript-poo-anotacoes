# O. - Open/closed principle

Esse príncipio diz que entidades devem estar abertas para extensões e fechadas para modificações, por exemplo se você tiver que dar descontos em um ecommerce, seria interessante você criar uma classe abstrata para poder expandir criando descontos dos variados tipos mas sem mudar essa lógica.

```typescript
export abstract class Discount {
  protected discount = 0;

  calculate(price: number): number {
    return price - price * this.discount;
  }
}

export class FiftyPercentDiscount extends Discount {
  protected readonly discount = 0.5;
}

export class TenPercentDiscount extends Discount {
  protected readonly discount = 0.1;
}

export class NoDiscount extends Discount {}

```

