<template>
  <div>
    <h1>
      <h2>Ejemplo Checkbox</h2>
      <button @click="generarCheckbox">Generar CheckBbox</button>
      <div id="checkboxes">
        <input v-for="num in checkBoxes" :key="num" type="checkbox"/>
      </div>
    </h1>
  </div>
</template>

<script>
export default {
  name: "CheckboxSuma",
  data() {
    return {
      numCheckbox: "",
      checkBoxes: [],
    };
  },
  methods: {
    generarCheckbox() {
      let numChecks = parseInt(Math.random() * 15) + 1;
      for(var i = 1; i <= numChecks; i++){
         let num = parseInt(Math.random() * 100) + 1;
        this.checkBoxes.push(num)
      }      
    },
  },
};
</script>