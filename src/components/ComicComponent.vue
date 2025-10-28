<template>
  <div id="comic">
    <h2>{{ comic.titulo }}</h2>
    <p>{{ comic.descripcion }}</p>
    <img :src="comic.imagen" alt="" />
    <h5 :class="{ rojo: comic.year <= 2000, verde: comic.year > 2000 }">
      Year: {{ comic.year }}
    </h5>
    <button @click="seleccionarFav()">Seleccionar Como Favorito</button>
    <button @click="deleteComic()" style="color: white; background-color:red">Eliminar</button>
  </div>
</template>

<script>
export default {
  name: "ComicComponent",
  props: ["comic" , "index"],
  methods: {
    seleccionarFav(){
        this.$emit("elegirFavorito",this.comic)
    },deleteComic(){
        this.$emit("deleteComic",this.index)
    }
  },
};
</script>

<style>
@import "./../assets/css/comics.css";
</style>