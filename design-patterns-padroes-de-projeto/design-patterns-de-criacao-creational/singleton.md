# Singleton

A intenção do Singleton é garantir que uma classe tenha somente uma instância no programa e fornecer um ponto de acesso global para a mesma.

### Somente uma instância?

* Geralmente usado para acesso a recursos compartilhados, como acesso à base de dados, interfaces gráficas, sistemas de arquivos, servidores de impressão, logger e mais.
* Também usado para substituir variáveis globais, como em casos de uso de objetos de configuração do sistema como um todo.

### Ponto de acesso global?

* Você pode permitir acesso global ao Singleton em toda sua aplicação, assim como fazemos com variáveis globais.
* Uma vantagem do Singleton é que podemos proteger a instância com encapsulamento, evitando que outro código sobrescreva seu valor.

### Aplicação

* Use o singleton quando uma classe precisa ter somente uma instância disponivel em todo o seu programa
* Use o singleton quando perceber que está usando variáveis globais para manter partes importantes do programa, como variáveis de configuração que são usadas por toda a aplicação.

### Vantagens

* Acesso controlado à instância única
* É fácil permitir um número maior de instâncias caso mude de ideia
* O singleton só é criado no momento do uso
* Substitui variáveis globais

### Desvantagens

* É mais difícil de testar
* Viola o princípio da responsabilidade única
* Requer tratamento especial em casos de concorrência

Exemplo:

```typescript
export class Singleton {
    private static _instance: Singleton | null = null; // Inicialmente é nulo
    
    private constructor() {
        //Não é permitir usar o new fora da classe, impedindo criar outra instância
    }
    
    static get instance(): Singleton {
     /*Se for a primeira vez que o método estático está sendo chamado, 
     retorna uma nova instância 
      */
        if (Singleton._instance === null) {
            Singleton._instance = new Singleton();
        }
        
        return Singleton._instance; // retorna a instância já criada
    }
}

```
