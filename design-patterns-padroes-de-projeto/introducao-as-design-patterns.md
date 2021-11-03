# Introdução as Design Patterns

As design patterns são soluções elegantes para problemas conhecidos recorrentes no desenvolvimento de softwares que foram utilizados e testados no passado e continuam relevantes nos dias atuais

Foram catalogados e popularizados pelo livro "Padrões de Projeto - Soluções reutilizáveis de software orientado a objetos" (os padrões da "GoF", de 1994-95 - por Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides)

São divididos em 3 categorias: **de criação(creational)**, que visam abstrair o processo como objetos são criados na aplicação; **estruturais(structural),** que lidam com a composição de classes e objetos; **comportamentais(behavioural),** que caracterizam como as classes e objetos interagem e distribuem responsabilidades na aplicação.

Benefícios e problemas

O que é bom:

* Você não precisa reinventar a roda
* Padrões universais facilitam o entendimento do seu projeto
* Evita refatoração desneceessária
* Ajuda na reutilização de código (conceito **DRY** - Don't repeat yourself)
* Abstrai e nomeia partes particulares do projeto
* Ajuda na aplicação dos princípios do design orientado a objetos (**S.O.L.I.D.**)
* Facilitam a criação de testes unitários

O que é ruim:

* Alguns padrões podem ser complexos até que você os compreenda
* Muito código para atingir um objetivo simples
* Podem trazer otimizações prematuras para o seu código (YAGNI - You Ain't Gonna Need It)
* Se usados incorretamente, podem atrapalhar ao invés de ajudar

Design Patterns de criação

* Abstract factory
* Factory method
* Builder
* Protoype
* Singleton

Design Patterns Estruturais

* Adapter
* Bridge
* Composite
* Decorator
* Façade
* Flyweight
* Proxy

Design Patterns Comportamentais

* Interpreter
* Template method
* Chain of responsibility
* Iterator
* Command
* Mediator
* Memento
* Observer
* State
* Strategy
* Visitor
