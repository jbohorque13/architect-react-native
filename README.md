# architect-react-native
Arquitectura de una App mobile con react-native

## Explicación de la Arquitectura
```
- src  ### El código js de la app
  - actions ### Aquí esta las funciones que interactuan con los servicios, funciones que consultan los (endpoints) para mas tarde usar la funcion reductora y actualizar el state de la App (Redux)
  - components ### Componentes generales de la App (Se usan en varias Screen)
  - containers ### Las Screen de la App
  - navigators ### Logica de de router
  - reducers ### Funcion reductora y sus metodos.
  - services ### Funciones que consultan los endpoints (Usan validaciones de utilities)
  - styles ### stylos comunes
  - utilities ### Funciones que se usan frecuentemente en la App
```

## Redux vs sin Redux (Ventajas)

En este proyecto en especifico que me plantee, considero que el uso de redux facilita en mucho de los aspecto de desarrollo de la App

1) Mantiene la informacion en el state del usuario por ejemplo :
  a) Nombre
  b) foto
Con lo cual te permite mostrarla en diferentes screen sin necesidad de estar pasando por params al momento de ir navegando permitiendo tener mayor flexibilidad, dependencia y mejor performance porque no deberas preocuparte de tener que por ejemplo consultar de nuevo algun endpoint.

2) Podria utilizar la funcion reductora post para guardar ciertos datos del post en caso de que:

  a) Falle conexion y el usuario no pudo publicar el post ese dato quede guardado en state.

3) Se tiene unas screen mas limpio de codigo.

## Redux vs sin Redux (Desventajas)

Debo mencionar algunas de las desventajas que he podido observar segun mi experencia de usar redux

Si conectas un componente descuidadamente a muchas variables del state, puede ocurrir que ese componente se renderize varias veces aunque no desees que se renderize o si no usas ShouldComponentUpdate esto puede llegar a afectar en el performance de la App significativamente.
 
