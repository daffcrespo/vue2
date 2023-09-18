<template>
  <div>
    <add-movie-form @movieAdded="addMovie" />
  </div>
  <div>
    <h1>Mis Películas</h1>
    <ul>
      <li v-for="movie in movies" :key="movie.id">{{ movie.title }}</li>
    </ul>
    <!-- ... Otros componentes o contenido ... -->
  </div>
</template>

<script>
  
import MovieList from "./MovieList.vue";
import AddMovieForm from "./AddMovieForm.vue";

export default {
  components: {
    MovieList,
    AddMovieForm,
  },
  data() {
    return {
      movies: [
        { id: 1, title: "Avengers" },
        { id: 2, title: "Spiderman" },
        { id: 3, title: "Interstellar" },
      ],
    };
  },
  methods: {
    addMovie(title) {
      const newMovie = { id: this.movies.length + 1, title };
      this.movies.push(newMovie);
      console.log("Película agregada:", newMovie);

    },
  },
};
  
</script>

<style>
  /* Estilos para el cuerpo de la aplicación */
  body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 0;
  }

  /* Contenedor principal */
  .app-container {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
    background-color: #fff;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }

  /* Estilos para los títulos */
  h2 {
    font-size: 1.5rem;
    margin-top: 0;
  }

  /* Estilos para la lista de películas */
  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    padding: 10px 0;
    border-bottom: 1px solid #ccc;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  /* Estilos para el formulario */
  form {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  input[type="text"] {
    padding: 5px;
    width: 70%;
  }

  button {
    padding: 5px 10px;
    background-color: #007bff;
    color: #fff;
    border: none;
    cursor: pointer;
  }

  /* Estilos para el botón Agregar */
  button[type="submit"] {
    background-color: #28a745;
  }
</style>