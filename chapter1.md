# ¿Qué vamos a necesitar?

### Node

React native es una tecnología basada en node, así que vamos a necesitar descargarlo. Vamos a hacer esto a través de el paquete de **nodesource**, que es la forma más rapida de obtenerlo.

Los pasos de instalación para sistemas basados en ubuntu son

```bash
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```

### Yarn

El gestor de paquetes por defecto de node es **npm**, sin embargo Facebook recomienda utilizar **yarn**, su nuevo gestor de dependencias node.

Para instalarlo

```bash
# Configuramos el repositorio

curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

# Luego simplemente

sudo apt-get update && sudo apt-get install yarn
```

### Expo

Expo es un set de herramientas para React Native, nos provee de un gran número de APIs que este último no posee de forma nativa. Además nos va a habilitar a desarrollar la aplicación de la manera más rapida y cómoda.

Expo es la tecnología recomendada por Facebook para desarrollar en React Native, y por ello nos proveen de una herramienta que nos permite crear una aplicación con Expo incluido, esta es:

### Create-react-native-app

Esta es la forma más facil de empezar una nueva aplicación de React Native. Nos permite empezar un proyecto sin necesidad de instalar o configurar ninguna herramienta para buildear codigo nativo \(no necesitamos Xcode ni Android Studio\).

Para instalarla

```bash
yarn global add create-react-native-app
```



