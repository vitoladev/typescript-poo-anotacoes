# D. Dependency Inversion Principle

Módulos de alto nível não devem depender de módulos de baixo nível. Ambos devem depender de abstrações. Dependa de abstrações. não de implementações. ou seja, não dependa da classe concreta, e sim de uma abstração como uma interface ou classe abstrata. Abstrações não devem depender de detalhes. Detalhes devem depender de abstrações.

Classes de baixo nível são classes que executam tarefas (os detalhes)

Classes de alto nível são classes que gerenciam as classes de baixo nível

```typescript
export class Order { // Classe de alto nível
  private _orderStatus: OrderStatus = 'open';

  constructor(
    /*Injeção de dependencias para a classe Order delegar essas funções 
    para outras classes, usando interfaces para cumprir com o princípio
    de inversão de dependencia para as classes de baixo nível.*/
    private readonly cart: ShoppingCartProtocol, // Classes de baixo nível
    private readonly messaging: MessagingProtocol,
    private readonly persistence: PersistenceProtocol,
    private readonly costumer: CostumerOrder,
  ) {}
}
```
