<!-- Directiva de show: v-if and v-else condicionales -->

<template>
  <div>
    <h1>Directivas</h1>
    <hr>
<h3>Tu edad es: {{ edad }}</h3>

<!-- nos permite crear una condicional que si se cumple muestre
o desaparece el elemento casi igual que el v-show pero tendremos mas control
 sobre los elementos, aqui le tenemos un limited a la edad y no puede
ser menor a cero ya que nadie tiene esa edad ni mayor que 100-->
<h2 v-if="edad >= 18 && edad > 0 && edad <100"> Eres mayor de edad</h2>
<h2 v-else-if="edad < 18 && edad > 0 && edad <100"> Eres menor de edad</h2>
<h2 v-else>Edad invalida</h2>

<button @click="add()">Add</button>
<button @click="dis()">Dis</button>
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
  },
  dis() {
    this.edad--;
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