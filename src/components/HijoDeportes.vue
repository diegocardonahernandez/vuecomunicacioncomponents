<template>
    <div>
        <h3>HIJO DEPORTE</h3>
        <h5 v-for="deporte in deportes" :key="deporte">{{deporte}}</h5>
    </div>
</template>

<script>
    export default {
        name: "HijoDeportes",
        props: ["deportes"]
    }
</script>