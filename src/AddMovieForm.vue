<template>
  <div>
    <h2>Agregar Película</h2>
    <form @submit.prevent="addMovie">
      <input v-model="newMovie" placeholder="Título de la película" />
      <button type="submit">Agregar</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newMovie: "",
    };
  },
  methods: {
    addMovie(title) {
      if (this.newMovie.trim() !== "") {
        this.$emit("movieAdded", this.newMovie);
        this.newMovie = "";
        console.log("Evento 'movieAdded' emitido con éxito");
      }
    },
  },
};
</script>