# Pokémons!

Para propósitos de este tutorial, la aplicación que desarrollaremos nos mostrará los primeros 20 pokémons de la lista de [PokeAPI](https://pokeapi.co/).

Para ello comenzaremos a desarrollar nuestro primer componente. El mismo será un componente del tipo `container`, esto significa que tendrá acceso a datos en forma de `state` \(hablaremos de esto en momentos\).

### PokeContainer 

Este será el container principal de la app, en él obtendremos a los pokemons via API REST, y los mostraremos en un componente de lista que crearemos posteriormente.

La estructura que sugiero para la creación de cualquier tipo de componente es la siguiente: un directorio `NombreDelComponente`, que adentro tenga un archivo `NombreDelComponente.js`, y un archivo `styles.js`.

Para nuestro caso particular esto quedaría de la siguiente forma

![](/assets/tree-3.png)



