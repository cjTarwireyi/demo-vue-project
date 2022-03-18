<template>
    <div class="backdrop" @click.self="closeModal">
    <div class="modal">
        <h1>{{selectedProduct.title}}</h1><br>     
      
        <img :src="require('@/assets/' + selectedProduct.imageUrl)" width="100" height="100">  
       
            <p>Size: {{selectedProduct.size}}</p>
            <p> Price: {{selectedProduct.price}}</p>
            <p> Stock Quantity: {{selectedProduct.stockQty}}</p>
        
    </div>
    </div>
    
</template>
<script>
export default{
    props:['selectedProduct'],
 data(){
    return {
        imgUrl:"red.png"
    }
    },
    methods: {
        closeModal(){
            this.$emit('closeModal');
        },
    },


}
</script>
<style scoped>
.modal{
     z-index: 9998;    
    background-color: rgba(0, 0, 0, 0.5);
    display: table; 
    transition: opacity 0.3s ease;
    width:400px;
    height: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
    z-index: 1000;
}
.backdrop{
    top:0;
    background: rgb(0,0,0,0.5);
    width: 100%;
    height:100%;
    position: fixed;
}
.modal h1 {
    font-style: normal;
    color: rgb(56, 21, 4);
}
</style>