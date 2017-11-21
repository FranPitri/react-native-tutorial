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

Esto centrará nuestra lista. Ahora vamos con los estilos de la lista y sus items!

```js
//PokeList/styles.js

import { StyleSheet } from 'react-native'

const styles = StyleSheet.create({
    list: {
        width: '100%',
    },
    item: {
        paddingTop: 20,
        paddingBottom: 20,
        marginTop: 25,
        marginBottom: 20,
        marginLeft: 10,
        marginRight: 10,
        borderRadius: 2,
        flex: 1,
        alignItems: 'center',
        backgroundColor: '#212121',
        elevation: 3
    },
    itemText: {
        fontWeight: '900',
        fontSize: 15,
        color: '#fff'
    }
})
  
export { styles as default }
```

```js
//PokeList.js

import React from 'react'
import {View, Text, FlatList} from 'react-native'
import styles from './styles'

const _renderItem = ({item}) => (
    <View style={styles.item}>
        <Text style={styles.itemText}>{item.name.toUpperCase()}</Text>
    </View>
)

const _keyExtractor = (item) => `pokemon-${item.name}`

const PokeList = ({data}) => (
    <FlatList 
        renderItem={_renderItem}
        keyExtractor={_keyExtractor}
        data={data}
        style={styles.list}
    />
)


export default PokeList
```

Podemos jugar con el estilo a gusto hasta tener los items que deseemos! Esto es una de las grandes ventajas de React Native, escribir estilos es muy facil e intiutivo!

Éste es el resultado final de nuestros PokeItems





