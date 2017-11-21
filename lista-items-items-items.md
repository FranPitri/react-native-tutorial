# Vamos a crear nuestra lista!

Ahora que sabemos cómo escribir un componente, como importarlo dentro de otro, y como guardar datos en su `state`; vamos a crear la lista que mostrará éstos datos.

### PokeList

Llamaremos a nuestra lista, cómo no, `PokeList`. Para ello crearemos un nuevo componente del tipo `component`, y haremos uso del componente `FlatList` que nos provee React Native.

Nuestro arbol de archivos se expandirá a algo como ésto:

![](/assets/tree-4.png)

Dentro de `PokeList` generaremos un componente, pero utilizaremos una sintaxis nueva. Esto es debido a que `PokeList` es un componente presentacional; es decir que solo será utilizado para mostrar datos, y no necesitará acceder a un `state` propio.

```js
//PokeList.js

import React from 'react'
import { FlatList } from 'react-native'

const PokeList = () => (
    <FlatList />
)

export default PokeList
```

`FlatList` va a requerir unos cuantos datos para renderizar una lista, y nosotros vamos a encontrar la forma de pasaselos a nuestro `PokeList` a través de `PokeContainer` \(recuerden que estos datos ya estan disponibles en su state\).

Antes que nada, ¿Qué necesitamos en nuestra `FlatList`?

* La propiedad **data **recibe un array de objetos, los cuales seran renderizados posterirmente en nuestra lista.
* La propiedad **renderItem** recibe una función que definirá cómo serán nuestros items. En esencia, esto es un componente presentacional.
* La propiedad **keyExtractor **definirá un valor único que se asignará a cada item para identificarlo.

Vamos a escribir estas últimas dos funciones de manera básica, además vamos a recibir una propieda **data** en nuestra `PokeList` y se la vamos a asignar a nuestra `FlatList`

```js
//PokeList.js

import React from 'react'
import {View, Text, FlatList} from 'react-native'

const _renderItem = ({item}) => (
    <View >
        <Text>{item.name}</Text>
    </View>
)

const _keyExtractor = (item) => `pokemon-${item.name}`

const PokeList = ({data}) => (
    <FlatList 
        renderItem={_renderItem}
        keyExtractor={_keyExtractor}
        data={data}
    />
)

export default PokeList
```

Así mismo, vamos a ubicar nuestra PokeList en PokeContainer, y le vamos a proporcionar nuestros pokemons como propiedad **data**

```js
//PokeContainer.js

import React, { Component } from 'react'
import { View, Text } from 'react-native'
import PokeList from '../../components/PokeList/PokeList'

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
            <View>
                <PokeList data={this.state.pokemons} />
            </View>
        )
    }

}
```



