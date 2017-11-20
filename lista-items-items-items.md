# Vamos a crear nuestra lista!

Ahora que sabemos cómo escribir un componente, y como importarlo dentro de otro, vamos a crear la lista que mostrará nuestros Pokémons en `PokeContainer`

### PokeList

Llamaremos a nuestra lista, cómo no, `PokeList`. Para ello crearemos un nuevo componente del tipo `component`, y haremos uso del componente `FlatList` que nos provee React Native.

Nuestro arbol de archivos se expandirá a algo como ésto:

![](/assets/tree-4.png)

Dentro de `PokeList` generaremos un componente, pero utilizaremos una sintaxis nueva. Esto es debido a que `PokeList` es un componente presentacional; es decir que solo será utilizado para mostrar datos, y no necesitará acceder al `state`.

