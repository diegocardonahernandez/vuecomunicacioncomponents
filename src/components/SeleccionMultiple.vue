<template>
  <div>
    <h1>SELECCIÓN MULTIPLE</h1>
    <select multiple v-model="selectedOptions">
      <option v-for="option in options" :key="option" :value="option">
        {{ option }}
      </option>
    </select><br>
    <button>Mostrar Selecciones</button>
    <ul>
        <li v-for="seleccion in selectedOptions" :key="seleccion">{{seleccion}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "SeleccionMultiple",
  data() {
    return {
      value: "",
      selectedOptions: [],
      options: [
        "Creatina",
        "Pre-Entreno",
        "Mass Gainer",
        "Proteina",
        "Ashwaghanda",
      ],
    };
  },
};
</script>

<style>
    ul{
        list-style: none;
    }
</style>