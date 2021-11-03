# Keyof e Typeof

O typeof retorna o tipo do seu objeto pra você passar em algum parametro de função, é bem util pois é dinamico, logo se você mudar o objeto não vai precisar mudar o tipo. O keyof é a mesma coisa só que para as chaves do seu objeto.

```typescript
type CoresObj = typeof coresObj;
type CoresChaves = keyof CoresObj;

const coresObj = {
  vermelho: 'red',
  verde: 'green',
  azul: 'blue',
  roxo: 'purple',
};

function traduzirCor(cor: CoresChaves, cores: CoresObj) {
  return cores[cor];
}

console.log(traduzirCor('vermelho', coresObj));
console.log(traduzirCor('verde', coresObj));
console.log(traduzirCor('roxo', coresObj));

```
