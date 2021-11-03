# Prototype

A intenção é especificar os tipos de objetos a srem criados usando uma instância-protótipo e criar novos objetos pela cópia desse protótipo.

### Visão geral do padrão Prototype

* O tipo de objeto a ser criado é determinado pleo objeto protótipo
* É tipicamente usado para evitar a recriação de objetos **"caros"**, que são complexos para ser construidos ou consomem muitos recursos para serem construidos, como uma classe que se conecta com a base de dados.
* Ajuda a evitar a explosão de subclasses.
* Pode (ou não) manter um registro de objetos protótipo um um objeto separado
* Geralmente é criado apenas com um método **"clone"** dentro do objeto protótipo
* O método clone pode gerar uma **"shallow**" ou **"deep"** copy do objeto protótipo
* Evita que o cliente conheça as classes que criam os objetos

### Aplicabilidade

* Use o padrão prototype quando precisar que seu código não dependa de **classes concretas** **para a criação de novos objetos**
* Quando quiser evitar explosão de subclasses para objetos muito similares
* para evitar a recriação de objetos **"caros"**

O que é bom ou ruim no Prototype:

**Bom:**

* Oculta classes concretas do código cliente
* Ajuda na criação de objetos caros ou complexos
* Evita a explosão de subclasses

**Ruim:**

* Clonar objetos que que tem referências para outros objetos pode ser super complexo

Exemplo:

```typescript
interface Prototype {
    clone(): Prototype;
}

class Person implements Prototype {
    constructor(public name: string, public age: number) {}
    
    clone(): this {
        /*
        Isso não é um clone
        Estamos apenas criando um novo objeto
        que tem esse objeto como protótipo
        */
        const newPerson = Object.create(this);
        return newPerson;
    }
}

const person1 = new Person('Victor', 16);
const person2 = person1.clone();

console.log(person1.name) // Victor
console.log(person2.name) // Victor
```
