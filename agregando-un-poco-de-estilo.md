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

```js
//PokeContainer.js

import React, { Component } from 'react'
import { View, Text } from 'react-native'
import PokeList from '../../components/PokeList/PokeList'
import styles from './styles'

export default class PokeContainer extends Component {

    constructor(props) {
        super(props)
        this.state = {
            pokemons: []
        }
    }

    componentWillMount() {
        fetch('http://pokeapi.co/api/v2/pokemon/?limit=20').then((response) => (
            response.json()
        ).then((data) => {
            this.setState({pokemons: data.results}, () => console.log(this.state))
        }))
    }
  
    render() {
        return (
            <View style={styles.container}>
                <PokeList data={this.state.pokemons} />
            </View>
        )
    }

}
```





