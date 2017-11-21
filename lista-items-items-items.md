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

`FlatList` va a requerir unos cuantos datos para renderizar una lista, y nosotros vamos a encontrar la forma de pasaselos a nuestro `PokeList` a través de `PokeContainer` \(recuerden que estos datos ya estan ubicados en su state\)

