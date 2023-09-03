<!-- Directiva de for: v-for recorriendo array y objetos -->

<template>
  <div>
    <h1>Directivas</h1>
    <hr>
<ul>
  <!-- lo implementemos en el li para crear una lista con cada elemento de mi array
  pasandole dos parametos acciendo referencia de como se llamara nuestra
  variable cada elemento del array in en nombre del array, tambien podemos pasar el indice 
  con el index por coma -->
  <!-- en el caso de que fuera un objeto se coloca la valor y la clave -->
  <li v-for=" (usuarios, index) in usuarios " :key="index" >
               {{index}} - {{ usuarios }} 
  </li>
</ul>

  </div>

</template>

<script>

export default {
  //aqui van las variables de objeto que podemos inyectar a nuestro html
  data: () => ({
    edad: 17,
    usuarios: [
      "Eder", "Brayan", "Ray", "Kleirin"
    ]
  }),
  //aqui los methods
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