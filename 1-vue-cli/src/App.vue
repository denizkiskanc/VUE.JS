<!-- <template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style> -->

<template>
<div class="container">
  <h3>Sepete Ekle</h3>
  <ul>
    <li v-for="item in cardItems" :key="item.id">{{item.title}}</li> <!-- veriyi yazırıyoruz-->
  </ul>
  <p v-if="cardItems.length==0">Sepet boş</p>
  <hr>
<!-- <myComp></myComp> -->
<product @addToCard="cardItems.push($event)" :product ="product" v-for="product in productList" :key="product.id"/><!-- veriyi burda karşılyıoruz-->

</div>
</template>

<script>

// import MainContainer from '@/components/MainContainer'
import ProductContainer from '@/components/ProductContainer'
export default {

  components:{

    // myComp:MainContainer,
    product:ProductContainer
  },

  data() {

    return{
        productList:[
               {
                 id:1,
                 title:"Macbook Pro",
                 price:1200,
                 count:10,
                 description:"Açıklama 1"
               },

               {
                 id:2,
                 title:"Macbook Air",
                 price:1000,
                 count:10,
                 description:"Açıklama 2"
               },

               {
                 id:3,
                 title:"İphone 13 Pro",
                 price:800,
                 count:10,
                 description:"Açıklama 3"
               }
            ],
            cardItems:[]
           
    }
  }

  
}
</script>

<style>
.container {

  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}


</style>
