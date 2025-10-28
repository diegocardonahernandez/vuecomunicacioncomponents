<template>
  <div>
    <h2>Soy Padre Matemáticas</h2>
    <h3 v-if="suma > 0" style="color: darkblue">LA SUMA ES: {{ suma }}</h3>
    <button @click="anadirNumero()">Nuevo Número</button>
    <h4 v-if="numeros.length == 0" style="color:darkred">No ha añadido ningún número aún</h4>
    <HijoMatematicas
      v-for="num in numeros"
      :key="num"
      :numeroHijo="num"
      v-on:sumarNumeroHijo="sumarNumero"
    />
  </div>
</template>

<script>
import HijoMatematicas from "./HijoMatematicas.vue";

export default {
  name: "PadreNumeros",
  components: {
    HijoMatematicas,
  },
  data() {
    return {
      numeros: [],
      suma: 0,
    };
  },
  methods: {
    anadirNumero() {
      let newNum = parseInt(Math.random() * 100) + 1;
      this.numeros.push(newNum);
    },
    sumarNumero(numero) {
        console.log("Sumando número...")
      this.suma += numero;
    },
  },
};
</script>