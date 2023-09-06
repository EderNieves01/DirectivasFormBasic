<!-- Directiva de eventos propiedades: v-bind:propiedad o forma abreviada :propiedad -->

<template>
  <div>
    <h1>Directivas</h1>
    <hr>
    <!-- mandamos de forma dinamica la url desde el script con
    v-bind:src o abreviado :src -->
    <img :src="url" alt="">

  </div>

</template>

<script>

export default {
  //aqui van las variables de objeto que podemos inyectar a nuestro html
  data: () => ({
    url: "https://cdn.svgporn.com/logos/vue.svg?response-content-disposition=attachment%3Bfilename%3Dvue.svg"
  })
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