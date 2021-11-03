# Composição

É quando um objeto é parte de outro objeto, como por exemplo um Motor é parte de um Carro, logo o Carro depende do Motor para ter suas funcionalidades como ligar, acelerar, parar, desligar, etc.

```typescript
export class Carro {
  private readonly motor = new Motor();

  ligar(): void {
    this.motor.ligar();
  }

  acelerar(): void {
    this.motor.acelerar();
  }

  parar(): void {
    this.motor.parar();
  }

  desligar(): void {
    this.motor.desligar();
  }
}

export class Motor {
  ligar(): void {
    console.log('Motor está ligado...');
  }

  acelerar(): void {
    console.log('Motor está acelerando...');
  }

  parar(): void {
    console.log('Motor está parado...');
  }

  desligar(): void {
    console.log('Motor está desligado...');
  }
}

const carro = new Carro();

carro.ligar();
carro.acelerar();
carro.parar();
carro.desligar();

```
