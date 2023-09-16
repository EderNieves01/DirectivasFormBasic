<template>
 
        <div class="data">
            <h2>Informacion...</h2>
            <h4>
                <span class="cripto">{{ cripto }}</span>
                  - 
                <span class="moneda">{{ moneda }}</span> </h4>

            <img :src="img" alt="">
            <p>
                precio: 
                <strong>
                {{ precio }}
                </strong>

            </p>
        </div>
  
</template>

<script>
export default {
   
    //aqui todos los props que necesita mi componente
    props: {
        cripto:{
            type: String,
            required: true,
        },
        moneda:{
            type: String,
            required: true,
        },
        img:{
            type: String,
            required: true,
        },
        precio:{
            type: Number,
            required: true,
        },
    }
    
};
</script>
