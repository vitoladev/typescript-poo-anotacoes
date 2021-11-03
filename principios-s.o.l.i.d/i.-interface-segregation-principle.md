# I. Interface Segregation Principle

O príncipio diz que os clientes não devem ser forçados a depender de interfaces, tipos ou membros abstratos que não utilizam, por exemplo se você tem clientes que são pessoa fisíca e pessoa juridica, a interface de Cliente não deveria ter cnpj em pessoas físicas, já que elas não utilizam isso. Sendo assim uma solução pra cumprir esse príncipio fazer uma interface pra cada cliente.

Jeito que não cumpre o príncipio:

```typescript
export interface CostumerProtocol {
  firstName: string;
  lastName: string;
  cpf: string;
  cnpj: string;
}

export class IndividualCostumer implements CostumerProtocol {
  firstName: string;
  lastName: string;
  cpf: string;
  cnpj: string;

  constructor(firstName: string, lastName: string, cpf: string) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.cpf = cpf;
    this.cnpj = '';
  }
}

export class EnterpriseCustomer implements CostumerProtocol {
  firstName: string;
  lastName: string;
  cpf: string;
  cnpj: string;

  constructor(firstName: string, lastName: string, cnpj: string) {
    this.firstName = '';
    this.lastName = '';
    this.cpf = '';
    this.cnpj = cnpj;
  }
}

```

Jeito que cumpre o príncipio:

```typescript
export interface IndividualCostumerProtocol {
  firstName: string;
  lastName: string;
  cpf: string;
}

export interface EnterpriseCostumerProtocol {
  name: string;
  cnpj: string;
}

export class IndividualCostumer implements IndividualCostumerProtocol {
  firstName: string;
  lastName: string;
  cpf: string;

  constructor(firstName: string, lastName: string, cpf: string) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.cpf = cpf;
  }
}

export class EnterpriseCustomer implements EnterpriseCostumerProtocol {
  name: string;
  cnpj: string;

  constructor(name: string, cnpj: string) {
    this.name = name;
    this.cnpj = cnpj;
  }
}

```
