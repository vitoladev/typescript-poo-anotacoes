# Factory Method

A intenção é definir uma interface para criar um objeto, mas deixar as subclasses decidirem que classe instanciar. O Factory Method permite adiar a instanciação para as subclasses.

Fábricas são simplesmente operações que criam objetos.

Exemplo:

```typescript
type car = { model: string; motor: string };
type CarPrototype = { showDetails(): void };

const carPrototype: CarPrototype = {
    showDetails(): void {
        console.log(this);
    },
};

const carFactory = (model: string, motor: string): Car & CarPrototype => {
    const idAsAPrivateMember = Math.floor(Math.random() * 1000);
    const carObj = Object.create(carPrototype);
    return Object.assign(carObj, { id: idAsAPrivateMember, model, motor });
};

const car1 = carFactory('Fusca', 'V8');
car1.showDetails(); // { id: 930, model: 'Fusca', motor: 'V8' }
const car2 = carFactory('Celta', 'ABDD1233');
car2.showDetails(); // { id: 672, model: 'Celta', motor: 'ABDD1233' }
```
