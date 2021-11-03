# Classes Abstratas

As classes abstratas são as que não permitem realizar qualquer tipo de instância. São classes feitas especialmente para serem modelos para suas classes derivadas. As classes derivadas, via de regra, deverão sobrescrever os métodos para realizar a implementação dos mesmos. As classes derivadas das classes abstratas são conhecidas como classes concretas.

Como medida de segurança, as classes abstratas somente podem ser estendidas, sendo que a criação de um objeto a partir da mesma é um procedimento evitado. Além disso, caso um ou mais métodos abstratos estejam presentes nessa classe abstrata, a classe filha será, então, forçada a definir tais métodos, pois, caso contrário, a classe filha também se tornará abstrata.

```typescript
export abstract class Personagem { 
    protected abstract emoji: string;
    constructor( 
        protected nome: string,
        protected ataque: number, 
        protected vida: number, ) {}
    atacar(personagem: Personagem): void { 
        this.bordao(); personagem.perderVida(this.ataque); 
        }
    perderVida(forcaAtaque: number): void { 
    this.vida -= forcaAtaque; 
    console.log( ${this.emoji} - ${this.nome} agora tem ${this.vida} de vida..., );
     }
    abstract bordao(): void; 
    }
    export class Guerreira extends Personagem { 
        protected emoji = '\u{1F9DD}';
        bordao(): void { console.log(this.emoji + ' GUERREIRAAAAAA AOOOOOO ATAAAQUEEE!!'); 
        } 
    } 


export class Monstro extends Personagem { 
    protected emoji = '\u{1F9DF}';
    bordao(): void { 
        console.log(this.emoji + ' MONNNNNNNNNNNSSSTERRRRRRRRRRRRRR!!!!'); 
    } 
}
```

