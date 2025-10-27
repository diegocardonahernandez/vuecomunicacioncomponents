<template>
  <div>
    <h1 style="color: darkblue">PADRE DEPORTES</h1>
   <HijoDeportes :deportes="deportes"/>
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
    };
  },
};
</script>