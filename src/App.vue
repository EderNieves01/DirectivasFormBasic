import Formulario from '.';
<!-- Directiva de eventos propiedades: v-bind:propiedad o forma abreviada :propiedad -->

<template>
  <div class="container">
    <div class="container2">
      <img :src="url" alt="" />
      <h1>{{ nombre }}</h1>
      <hr />
    </div>

    <Grid>
<!-- mandamos el metodo por atributo -->
      <!-- <formulario-1 :obtener="obtener" /> -->
      <!-- aqui otra forma de implementar un evento del hijo al padre-->
      <formulario-1 @info_monedas="obtener" />
      <Data 
      :cripto="info.cripto"
      :moneda="info.moneda"
      :precio="info.precio"
      :img="info.img"/>

    </Grid>

  </div>
</template>

<script>
import Formulario1 from "./components/Formulario1.vue";
import Data from "./components/Data.vue";
import Grid from "./components/Grid.vue";

export default {
  components: { Formulario1, Data, Grid },
  //aqui van las variables de objeto que podemos inyectar a nuestro html
  data: () => ({
    url: "https://cdn.svgporn.com/logos/vue.svg?response-content-disposition=attachment%3Bfilename%3Dvue.svg",
    nombre: "Cotizador de monedas",
    info: {
      cripto: "*",
    moneda: "*",
    img: "https://cdn.svgporn.com/logos/vue.svg?response-content-disposition=attachment%3Bfilename%3Dvue.svg",
    precio: 0,
    }
    
  }),
  methods: {
 async obtener(cripto, moneda){
  //cambiamos la ruta para obtener el resultado deseado, colocando `` para agregar string y colocar las variables con ${}
    //Asi modificamos la ruta
  //const res = await fetch("https://min-api.cryptocompare.com/data/pricemultifull?fsyms=ETH&tsyms=USD,EUR");
    //encoreURI agrega metedos de ruta como % y hacerlas mas seguras
  const res = await fetch (`https://min-api.cryptocompare.com/data/pricemultifull?fsyms=${ encodeURI(cripto) }tsyms=${ encodeURI(moneda)}`
    );
    console.log(res);
//destructuracion del objeto
    const {RAW} = await res.json();
   
    const dataCripto = RAW[cripto];
    const data = dataCripto[moneda];

    this.info.cripto = cripto;
    this.info.moneda = moneda;
    this.info.img = data.IMGEURL;
    this.info.precio = data.PRICE;
  },
},
};
</script>

<style scoped>
h1{
  font-size: 72px;
  background: -webkit-linear-gradient(right,#ad8686 0% 50%, #a72929 52% 100%);
  -webkit-background-clip: text ;
  -webkit-text-fill-color : transparent;
}
div {
  margin: 0px 2rem;
}
.container2 {
  margin-top: 10px;
  text-align: center;
}
.container {
  border: 2px solid grey;
  border-radius: 5px;
}
img {
  width: 75px;
}
</style>
