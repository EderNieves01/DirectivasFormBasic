<!-- Directiva de eventos click: v-on:click o forma abreviada @click -->

<template>
  <div>
    <h1>Directivas</h1>
    <hr>

    <div @click="clicks" class="contador"> {{ Clicks }} </div>

  </div>

</template>

<script>

export default {
  //aqui van las variables de objeto que podemos inyectar a nuestro html
  data: () => ({
    Clicks: 0
  }),
  //aqui los methods
  methods: {
    clicks(){
    this.Clicks++;
  }
  }
}
</script>


<style scoped>
div{
  text-align: center;
  margin: 0px 2rem ;

}
.contador{
  background: tomato;
  color: snow;
  font-weight: bold;
  height: 200px;

}
</style>