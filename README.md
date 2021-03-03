# tiptiTest

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

  En la carpeta principal -> 
      run ->
          flutter run

  Problemas con Android inicia
    Caperta principal -> 
          cd Android && ./gradlew clean

## Estructura de proyecto

El projecto esta organizado por 5 carpetas dentro del recurso lib
en la ruta /Tiptitest/lib/

- lib ┐

    models ┐

        actors_model.dart
        character_movie.dart
        movie_modal.dart
        rickAndMorty.dart
        todo_model.dart

    providers ┐

        addController.dart
        movie_provider.dart

    screens ┐

        episodes.dart
        home_pages.dart
        homescreen.dart
        movie_details.dart
        todo.dart

    search ┐

        search_delegate.dart

    widgets ┐

        card_episodes.dart
        card_swiper_widget.dart
        movie_horizontal.dart
        navigation.dart

    main.dart

## Rutas

En las rutas tenemos 5 las cuales son:
  - `/`
  - `/episodes`
  - `/movies`
  - `details`
  - `/todo`

Las rutas del proyecto son:
    La inicial `/` que contiene los characters y la `/episodes` que contiene los episodios.
    Adicional ahy 3 rutas. Estas representan a proyectos pequeños que realice el dia sabado y domingo
    cuenta con una Api de peliculas donde se utiliza el paquete el card_swiper de Dev.pub y parametros en la 
    ruta details y un buscador de peliculas con sugerencias.
    tambien tenemos una muy basica todoApp en la ultima ruta.
    Las ultimas 3 rutas no cuentan en el proyecto pero me senti con las ganas de tambien enviarlo
    para que sea un proyecto un poco mas completo justificando mi demora en enviar el proyecto.


## Proyecto

El proyecto consiste en consumir 2 Api Restfull. En la carpeta 
  - /Tiptitest/lib/screens/homescreen.dart
vamos a encontrar el primer diseño, en donde consumimos los personajes de Rick and Morty que consiste
en:
  - Nombre
  - Estado
  - Imagen
cuando consumo la Api lo hago por el metodo http de dart. Los pasos que realizo son los siguientes:
  - Creo un modelo -> ruta -> /Tiptitest/lib/models/rickAndMorty.dart.
    La razon por la cual creo un modelo es para almacenar en un metodo organizado mis datos
    y esperar un respuesta json, de tal manera que pueda re utilizarlo en otro Widget. 
    Las 2 clases creadas en el modelo corresponden a crear un metodo Map<> para armar
    mi objecto tipo json, despues procedo a llamar un metodo List para guardar mis datos
    obtenidos en la Api anteriormente consumida dentro de un arreglo/array.

  - Creo un package tipo Provider -> ruta -> /Tiptitest/lib/providers/movie_provider.dart para solicitar las respuestas de las API RestFul.
    Para lograr optimizar mi codigo creo un provider de tal manera que pueda organizar mis
    solicitudes y respuestas http, y luego guardar mis información. De esta manera en la función ```getCharactersPerson```
    agrego un condicionador de carga para evitar las peticiones repetidas, de la misma forma agrego un contador 
    tipo `int` para la paginación que se cambie al momento de hacer un scroll end. Despues realizo la petición y descodifico 
    la respuesta. Posterior a eso añado mi respuesta en mi arreglo. Al tratarse de un Infinite Scroll utilizo Streamings
    para el flujo de información en una sola vía y no obtener errores en las solicitudes o guardado de datos. Finalmente
    retorno mi arreglo.

  - Visualizo mi información
    Finalmente vizualizo mi información dentro de un `StreamBuilder()` donde hago una iteración de mi arreglo y creación de Widgets.

  - /Tiptitest/lib/screens/episodes.dart
    Hacemos lo mismo que en la API 1 pero esta vez en la visualización no mostramos un GridView al contrario mostramos un ListView.


## Paquetes utilizados

  - En pubspec he modificado 1 dependencies `flutter_swiper` y una dev dependencies `http`

## Observaciones

  - API Rick and Morty no corre a un buen performance esto se puedo validar con la ruta `/movies`
    donde la API movies siendo mas grande carga mas rapido.

## Conclusión

  - Aunque flutter tiene una limitación en el diseño, contiene una gran variedad de Widget 
    que te ayudan a mejorar el performance y el UI de la app. Flutter es un lenguaje optimo
    que va a ser de los mejores a futuro. De las cosas mas agradables es crear sus diseños
    con los Widgets ya que te ayudan muchisimo.


## GRACIAS ## Atento a cualquier duda.