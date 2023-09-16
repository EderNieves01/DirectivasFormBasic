<template>
  <div>
    <!-- pasamos los parametros aqui -->
    <!-- <form @submit.prevent="obtener(cripto, moneda)"> -->
      <!--emit emite un evento y sus parametos para ser llamado en el padre y asi eliminar el props-->
      <form @submit.prevent="$emit('inforMonedad', cripto, moneda)">
      <div>
      <label>
        Moneda Nacional:
      </label>
      <select v-model="moneda" required>
        <option value="" disabled selected>
          Seleccione una Moneda...
        </option>
        <option>MXN</option>
        <option>USD,EUR</option>
        <option>EUR</option>
      </select>
    </div>
    <div>
      <label>
        Criptomoneda:
      </label>
      <select v-model="cripto" required>
        <option value="" disabled selected>
          Seleccione una Criptomoneda...
        </option>
        <option>BTC</option>
        <option>ETH</option>
        <option>LTC</option>
      </select>
    </div>

    <div>
      <button type="submit">cotizar</button>
    </div>
    </form>
  
  </div>
</template>

<script>
export default {
 data: () => ({
  moneda: "",
  cripto: "",
}),
// props: ["obtener"]
// methods: {
  //peticiones http con async y await
  //await espera que la respuesta se resuelva antes de cualquier otra cosa
//  async obtener(){
//   //cambiamos la ruta para obtener el resultado deseado, colocando `` para agregar string y colocar las variables con ${}
//     //Asi modificamos la ruta
//   //const res = await fetch("https://min-api.cryptocompare.com/data/pricemultifull?fsyms=ETH&tsyms=USD,EUR");
//     //encoreURI agrega metedos de ruta como % y hacerlas mas seguras
//   const res = await fetch (`https://min-api.cryptocompare.com/data/pricemultifull?fsyms=${ encodeURI(this.cripto) }tsyms=${ encodeURI(this.moneda)}`
//     );
//     console.log(res);

//     const data = await res.json();
   
//     console.log(data)
//   },
//mandamos todo esto por props hacia app.vue y export
// },
};
</script>

<style>

</style>