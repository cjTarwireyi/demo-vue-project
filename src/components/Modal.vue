<template>
    <div class="backdrop" @click.self="closeModal">
    <div class="modal">
        <h1>{{selectedProduct.title}}</h1>
      
       <img alt="Vue logo" :src="require('' +selectedProduct.imageUrl)">
         <button @click="closeModal">close Modal</button>
    </div>
    </div>
    
</template>
<script>
export default{
    props:['selectedProduct'],
    methods: {
        closeModal(){
            this.$emit('closeModal');
        }
    }

}
</script>
<style scoped>
.modal{
    width:400px;
    height: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
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