# Primeros pasos

### Inicializar la aplicación

Para comenzar nuestro proyecto vamos a inicializar la aplicación

```bash
create-react-native-app NuevasTecnologias
cd NuevasTecnologias/
```

> Happy hacking!

Podemos observar que el arbol del directorio es bastante sencillo

![](/assets/tree.png)

`node_modules` será el directorio donde se guardarán los paquetes de node que descarguemos.

`App.js` será el punto principal de nuestra aplicación.

### Organizando el proyecto

React Native nos permite organizar nuestro proyecto de la manera que nosotros deseemos. Sin embargo es una buena práctica organizarlo consistentemente y de forma que nos permita acceder a cada parte de la aplicación de manera óptima.

Al proyecto base le vamos a agregar una carpeta `src`, y dentro de ella dos carpetas llamada `components`  y `containers`. Allí pondremos los componentes que crearemos para nuestra aplicación.

![](/assets/tree-2.png)

### Corriendo la aplicación

Para trabajar con esta aplicacion vamos a descargar el cliente de **Expo **para [Android](https://play.google.com/store/apps/details?id=host.exp.exponent&hl=en) o [iOS](https://itunes.apple.com/us/app/expo-client/id982107779?mt=8)** **en un dispositivo móvil.

Luego abrimos una terminal en la carpeta del proyecto y corremos

```
yarn start
```

_Cabe destacar que **nuestra computadora y nuesto dispositivo móvil deben estar en la misma red.**_

Expo generará un servidor local con nuestra aplicación, y podremos acceder al mismo a través de nuestro cliente de Expo. También nos provee de un código QR, el cuál podemos leer para acceder rápidamente al servicio.

![](/assets/qr.png)



