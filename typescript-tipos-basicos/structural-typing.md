# Structural Typing

_O typescript não se importa com a identidade do tipo, apenas o seu conteúdo, logo o que você está enviando não precisa necessariamente ser do tipo que é requerido, apenas cumprir as regras que o tipo tem. No exemplo abaixo **bdUser **e **sentUser **não são do tipo **User**, porém cumprem as regras que o tipo User tem logo são válidos._

Exemplo:

```typescript
type VerifyUserFn = (user: User, sentValue: User) => boolean; 
type User = { username: string; password: string };
const verifyUser: VerifyUserFn = (user, sentValue) => { 
  return ( user.username === sentValue.username && user.password === sentValue.password ); 
  };
const bdUser = { username: 'joao', password: '123456' }; 
const sentUser = { username: 'joao', password: '123456', permissions: '' }; 
const loggedIn = verifyUser(bdUser, sentUser); console.log(loggedIn);
```

``
