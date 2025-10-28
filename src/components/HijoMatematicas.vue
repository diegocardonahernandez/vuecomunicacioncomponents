<template>
    <div>
        <h2>Número Hijo: {{numeroHijo}} </h2> 
        <button @click="sendNumeroSuma()">Sumar {{numeroHijo}} </button>

    </div>
</template>

<script>
    export default{
        name:"HijoMatematicas",
        props: ["numeroHijo"],

            methods: {
                sendNumeroSuma(){
                    this.$emit("sumarNumeroHijo",this.numeroHijo)
                }
            }
    }
</script>