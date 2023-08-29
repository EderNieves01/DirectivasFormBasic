<!-- Directiva de show: v-show que podemos ocultar y ver elementos -->

<template>
  <div>
    <h1>Directivas</h1>
    <hr>
<h3>Tu edad es: {{ edad }}</h3>

<!-- nos permite crear una condicional que si se cumple muestre
o desaparece el elemento-->
<h2 v-show="edad >= 18"> Eres mayor de edad</h2>
<h2 v-show="edad < 18"> Eres menor de edad</h2>

<button @click="add()">add</button>
  </div>

</template>

<script>

export default {
  data: () => ({
    edad: 17,
  }),
  methods: {
    add(){
    this.edad++;
  }
  }
}
</script>


<style scoped>
div{
  text-align: center;
  margin: 0px 2rem ;

}
</style>