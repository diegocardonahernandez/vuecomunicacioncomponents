<template>
  <div>
    <h1 style="color: darkblue">PADRE DEPORTES</h1>
    <h2 style="bakcgroubd-color: yellow;" v-if="favorito">
      Su deporte Favorito es {{favorito}}
    </h2>
   <HijoDeportes :deportes="deportes" v-on:seleccionarFavorito="seleccionarFavorito"/>
  </div>
</template>

<script>
import HijoDeportes from "./components/HijoDeportes.vue";

export default {
  name: "PadreDeportes",
  components: {
    HijoDeportes,
  },
  data() {
    return {
      deportes: ["Futbol", "Tenis", "Cricket", "Padel"],
      favorito: null
    };
  },
  methods: {
    seleccionarFavorito(deporteFav){
      console.log("Yo sou tu padre")
      this.favorito = deporteFav
    }
  }
};
</script>