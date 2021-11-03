# S. - SRP

Esse princípio consiste em criar classes coesas, que seus métodos utilizem apenas as propriedades da própria classe, criando outras classes independentes para fazer as outras funções do programa, fazendo com que cada classe faça apenas um trabalho no código. para executar as funções que foram criadas nas outras classes independentes pode injetar essas dependencias como propriedades de uma classe para o programa funcionar.&#x20;

Exemplo:

```typescript
import { OrderStatus } from './interfaces/order-status';
import { ShoppingCart } from './shopping-cart';
import { Messaging } from '../services/messaging';
import { Persistence } from '../services/persistence';

export class Order {
  private _orderStatus: OrderStatus = 'open';

  constructor(
    /* Injeção de dependencias para a classe Order delegar essas funções para 
    as outras classes */
    private readonly cart: ShoppingCart,
    private readonly messaging: Messaging,
    private readonly persistence: Persistence,
  ) {}

  get orderStatus(): OrderStatus {
    return this._orderStatus;
  }

  checkout(): void {
    if (this.cart.isEmpty()) {
      console.log('Seu carrinho está vazio');
      return;
    }

    this._orderStatus = 'closed';
    // Função de enviar mensagem delegada para a classe messaging
    this.messaging.sendMessage(
      `Seu pedido com total de ${this.cart.total()} foi recebido.`,
    );
    // função de persistencia da compra delegada para a classe persistence
    this.persistence.saveOrder();
    // função de limpar o carrinho delegada para a classe cart
    this.cart.clear();
  }
}

const shoppingCart = new ShoppingCart();
const messaging = new Messaging();
const persistence = new Persistence();
/* classe Order recebendo as outras classes como dependencias 
para delegar as outras funções */
const order = new Order(shoppingCart, messaging, persistence);
```
