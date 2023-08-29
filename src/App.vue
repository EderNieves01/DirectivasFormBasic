<!-- Directiva de html: v-html que podemos agregar contenido html
desde nuestro script -->

<template>
  <div>
    <h1>Directivas</h1>
    <hr>

    <!-- me crea un h3 con su contenido creado en en script 
    pero nos deja vulnerables ataques xss, podemos crear script y pasarlos aqui-->
<div v-html="html"></div>
  </div>

</template>

<script>

export default {
  data: () => ({
    html: "<h3> Hola a todos</h3>"
  })
}
</script>


<style scoped>
div{
  text-align: center;
  margin: 0px 2rem ;

}
</style>