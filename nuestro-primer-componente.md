# Pokémons!

Para propósitos de este tutorial, la aplicación que desarrollaremos nos mostrará los primeros 20 pokémons de la lista de [PokeAPI](https://pokeapi.co/).

Para ello comenzaremos a desarrollar nuestro primer componente. El mismo será un componente del tipo `container`, esto significa que tendrá acceso a datos en forma de `state` \(hablaremos de esto en momentos\).

### PokeContainer

Este será el container principal de la app, en él obtendremos a los pokemons via API REST, y los mostraremos en un componente de lista que crearemos posteriormente.

La estructura que sugiero para la creación de cualquier tipo de componente es la siguiente: un directorio `NombreDelComponente`, que adentro tenga un archivo `NombreDelComponente.js`, y un archivo `styles.js`.

Para nuestro caso particular esto quedaría de la siguiente forma

![](/assets/tree-3.png)

Comenzaremos por `PokeContainer.js`

Vamos a escribir solo los metodos necesarios para que este componente funcione

```js
//PokeContainer.js

import React, { Component } from 'react'
import { View } from 'react-native'

export default class PokeContainer extends Component {

    render() {
        return (
            <View></View>
        )
    }

}
```

Los componentes del tipo `container` son creados con la sintaxis de clases, de JavaScript ES6.

Como verán solo implementamos un método `render`. Éste es el único método necesario para crear un componente.

Habrán notado que dentro de `render` utilizamos una sintaxis muy similar a html, sin embargo ésta es llamada JSX, la cual, si bien no es necesaria, es la forma más conveniente de escribir en React.

Dentro de éste colocamos una `View`, esto sería el equivalente a un `div` en html, un mero contenedor.

Por ahora vamos a poner algo de texto dentro de nuestro componente, y lo vamos a ubicar en el punto principal de nuestra aplicación \(`App.js`\) para poder visualizarlo en nuestro dispositivo. Para ello agregaremos lo siguiente:

```js
//PokeContainer.js

import React, { Component } from 'react'
import { View, Text } from 'react-native'

export default class PokeContainer extends Component {

    render() {
        return (
            <View>
                <Text>
                    {'Este es nuestro PokeContainer!'}
                </Text>
            </View>
        )
    }

}
```

E importaremos nuestro `PokeContainer` en `App.js`

```js
//App.js

import React from 'react'
import { StyleSheet, Text, View } from 'react-native'
import PokeContainer from './src/containers/PokeContainer/PokeContainer'

export default class App extends React.Component {
  render() {
    return (
        <View style={styles.container}>
            <PokeContainer />
        </View>
    )
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
})
```

Ahora nuestra aplicación nos mostrará el contenido de `PokeContainer`

![](/assets/mobile-2.jpg)

Muy bien! Ahora vamos a hacer algo un poco mas interesante.

### Manejando State

El `state` es un objeto que podemos definir en todos los componentes del tipo `container`. Podemos pensarlo como un objeto que define los atributos del componente. En el se guardan datos que luego se utilizaran en el container, o sus componentes interiores.

Vamos a agregarle `state` a nuestro `PokeContainer`



```js
//PokeContainer.js

import React, { Component } from 'react'
import { View, Text } from 'react-native'

export default class PokeContainer extends Component {

    constructor(props) {
        super(props)
        this.state = {
            pokemons: []
        }
    }
    
    render() {
        return (
            <View>
                <Text>
                    {'Este es nuestro PokeContainer!'}
                </Text>
            </View>
        )
    }

}
```

En el `constructor` de nuestro container definimos que su `state` va a poseer un atributo pokemons, que por default va a corresponder a un array vacío. Ahora nuestro container va a poder retener datos!

> Pero..pero..yo quiero ver pokemons!

Un reclamo tan válido como cualquier otro. Vamos a ver como podemos lograr esto introduciendo un nuevo termino.

### Lifecycle Methods





