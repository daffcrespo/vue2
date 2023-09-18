<template>
  <div>
    <h2>Lista de Películas</h2>
    <ul>
      <li v-for="movie in movies" :key="movie.id">{{ movie.title }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      movies: [
        { id: 1, title: "Avengers" },
        { id: 2, title: "Spiderman" },
        { id: 3, title: "Interstellar" },
      ],
    };
  },
};
</script>