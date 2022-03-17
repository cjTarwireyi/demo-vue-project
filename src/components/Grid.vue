<template>
<div class="card">
    Products 
    <table class="table" id="products">
          <thead class="thead-dark">
        <tr>
            <th>Title</th><th>Size</th> <th>Price</th><th></th>
        </tr>
          </thead>
        <tr v-for="product in products" :key="product.id"> 
            <td>{{product.title}}</td> <td>{{product.size}}</td> <td>{{product.price}}</td> <td><button @click="viewProductDetails(product)">view details</button></td>
        </tr>
    </table>
   
</div>
<div v-if="showModal">
    <Modal :selectedProduct ="selectedProduct" @closeModal="viewProductDetails"/>
</div>
</template>

<script>
import Modal from'./Modal.vue';
export default {
    components:{Modal},
      methods:{
    viewProductDetails(product){
    this.selectedProduct=product;       
      this.showModal = !this.showModal;
    }
  },
    data(){
    return {
        selectedProduct:{},
        showModal: false,
        products:[ {
            "id": "123",
            "title": "Red Shirt",
            "size": "XL",
            "price": "R350",
            "stockQty": "5",
             "imageUrl": "red.png"
        },
        {
            "id":"456",
            "title": "White Shirt",
            "size": "S",
            "price": "R100",
            "stockQty": "5",
            "imageUrl": "@/assets/red tea shirt.png"
        },
         {
            "id":"456",
            "title": "Blue Shirt",
            "size": "M",
            "price": "R250",
            "stockQty": "5",
            "imageUrl": "@/assets/red tea shirt.png"            
             
        },
        {
            "id":"456",
            "title": "Black Shirt",
            "size": "L",
            "price": "R300",
            "stockQty": "5",
            "imageUrl": "../assets/red.png"
        }]
    }

    },
}
</script>
<style scoped>
#products {
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

#products td, #products th {
  border: 1px solid #ddd;
  padding: 8px;
}

#products tr:nth-child(even){background-color: #f2f2f2;}

#products tr:hover {background-color: #ddd;}

#products th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #6280d3;
  color: white;
}
.card{
    width:700px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}
</style>