# Typescript Tipos básicos

## Tipos básicos (aqui ocorre inferência de tipos)&#x20;

```typescript
let nome: string = 'Luiz'; // Qualquer tipo de strings: '' "" `` 
let idade: number = 0b1010; // 10, 1.57, -5.55, 0xf00d, 0b1010, 0o7744 
let adulto: boolean = true; // true ou false 
let simbolo: symbol = Symbol('qualquer-symbol'); // symbol 
let big: bigint = 10n; // bigint
```

#### Arrays&#x20;

```typescript
let arrayDeNumeros: Array = [1, 2, 3]; 
let arrayDeNumeros2: number[] = [1, 2, 3];
let arrayDeStrings: Array = ['a', 'b']; 
let arrayDeStrings2: string[] = ['a', 'b'];
```

#### Objetos&#x20;

```typescript
// ?: chave opicional
let pessoa: {nome: string, idade: number, adulto?: boolean} = { 
   idade: 30, 
   nome: 'Victor' 
};
```

``
