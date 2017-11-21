# ｅ　ｓ　ｔ　ａ　ｉ　ｌ　（　͡°　͜ʖ　͡°）

Por último, vamos a ver como hacer que nuestra rudimentaria `PokeList` sea presentable.

Vamos a darle uso a los múltiples archivos `styles.js` que estuvimos creando. La forma en la que funcionan es sencilla, generamos un objeto `StyleSheet` de React Native y se los aplicamos a nuestros componentes como si fueran clases de CSS. De hecho, escribir `StyleSheets` es casi igual a escribir CSS!

Primero que nada vamos a escribir el estilo de `PokeContainer` y a aplicarselo:

```js
//PokeContainer/styles.js

import { StyleSheet } from 'react-native'

const styles = StyleSheet.create({
    container: {
        flex: 1,
        alignItems: 'center',
        justifyContent: 'center',
        flexDirection: 'column',
        width: '100%',
    },
})
  
export { styles as default }
```





