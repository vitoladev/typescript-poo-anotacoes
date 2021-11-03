# Builder

A intenção do Builder é separar a construção de um objeto complexo da sua representação de modo que o mesmo processo de construção possa criar diferentes representações.

### Visão geral do Builder

* O padrão sugere a separação do código que cria e o código que usa o objeto, visando separar a construção de um objeto complexo do código cliente que usa o objeto.
* Trata da criação de objetos completos, que tem construtor muito complexo e vários objetos para composição
* Permite a criação de um objeto em etapas
* Permite o encadeamento de chamadas de métodos
* O objeto final pode variar de acordo com a necessidade
* É um padrão complexo
* Permite que o objeto final varie em dados e tipo



### Aplicabilidade

* Use o Builder quando a criação do objeto se torna complexa
* Use o Builder quando quiser que o código seja capaz de gerar diferentes representações do mesmo objeto

### Consequências

O que é bom ou ruim no Builder:

**Bom:**

* Separa criação de utilização de objetos
* O cliente não precisa criar objetos diretamente
* O mesmo código pode construir objetos diferentes
* Ajuda na aplicação dos princípios SRP e OCP

**Ruim:**

* O código final pode se tornar muito complexo

```typescript
import { MealBuilderProtocol } from '../interfaces/meal-builder-protocol';
import { Rice, Beans, Meat, Beverage, Dessert } from './meals';

export class MealBox implements MealCompositeProtocol {
  private readonly _children: MealCompositeProtocol[] = [];

  getPrice(): number {
    return this._children.reduce((sum, meal) => sum + meal.getPrice(), 0);
  }

  add(...meal: MealCompositeProtocol[]): void {
    meal.forEach((item) => this._children.push(item));
  }
}



export class MainDishBuilder implements MealBuilderProtocol {
  private _meal: MealBox = new MealBox();

  reset(): this {
    this._meal = new MealBox();
    /* reseta o objeto retornando a classe que ele abstrai
    */
    return this;
  }

  makeMeal(): this {
    const rice = new Rice('Arroz', 5);
    const beans = new Beans('Feijão', 10);
    const meat = new Meat('Carne', 20);
    this._meal.add(rice, beans, meat);
    /* retorna a instância da classe permitindo o encadeamento
     na chamada de métodos */
    return this;
  }

  makeBeverage(): this {
    const beverage = new Beverage('Bebida', 7);
    this._meal.add(beverage);
    return this;
  }

  getMeal(): MealBox {
    return this._meal;
  }

  getPrice(): number {
    return this._meal.getPrice();
  }
}

const mainDishBuilder = new MainDishBuilder();
/*
Retorna a refeição com arroz, feijão e carne, 
ocultando do cliente esses dados quando chamado em outro módulos
*/
mainDishBuilder.makeMeal().makeBeverage().getMeal(); 
```
