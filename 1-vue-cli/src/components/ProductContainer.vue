<template>
<div class="product">
    <strong>{{product.title}}</strong>
    <p>{{product.description}}</p>
    <strong>Fiyatı: {{product.price}} | Adet : {{product.count}}</strong>
    <br><br>
    <button  @click="addToCard(product)">Sepete Ekle</button>
</div>
</template>
<script>

export default {

    props : ["product"], //almak istediğimiz veri
    methods:{
        addToCard(product){

            this.$emit("addToCard",product)// key(eventin adı),value
            //$emit vue instance’nın kullandığı bir metod. Veri yaymamızı sağlar.
        }
    }  

}
</script>
<style>
.product {

    border:2px solid #ccc;
    padding: 5px 10px;
    width:300px;
    margin-bottom:10px;

}




</style>