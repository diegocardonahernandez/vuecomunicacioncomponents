<template>
  <div>
    <h3>HIJO DEPORTE</h3>
    <h5 v-for="deporte in deportes" :key="deporte">{{ deporte }}
         <button @click="seleccionarFavorito()">Seleccionar Favorito</button>
    </h5>
   
  </div>
</template>

<script>
export default {
  name: "HijoDeportes",
  props: ["deportes"],
  deporte: "",

  methods: {
    seleccionarFavorito(){
        console.log("Soy el hijo " + this.deporte) 
    }
  },
};
</script>