<!-- Directiva de texto: v-text -->

<template>
  <div>
    <h1>Directivas</h1>
    <hr>
<!-- se agrega directamente a la etiqueta -->
<!-- <span v-text="title"></span> -->

<!-- y podemos agregarlo afuera, es mas recomendable por si queremos 
combinar texto -->
<span >Eder {{ title }}</span>
  </div>

</template>

<script>

export default {
  data: () => ({
    title: "Hola desde vue"
  })
}
</script>


<style scoped>
div{
  text-align: center;
  margin: 0px 2rem ;

}
</style>