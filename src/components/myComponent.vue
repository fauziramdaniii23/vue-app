<template>
    <div class="my-component">
      <h1>{{ alamat }}</h1>
      <button @click="fullAddress">full address</button>
    </div>
    <input type="text" v-model="nama">
    <p>{{ nama }}</p>
    
  <div v-if="cariData.length">
    <ul>
      <li v-for=" item in cariData" :key='item.id' >
        {{ item.title }} - {{ item.harga }}
      </li>
    </ul>
  </div>
  <div v-else >
   
      <p>No Data</p>
    
  </div>

  <input type="text" placeholder="cari" v-model="cari">
  </template>
  
  <script>
  export default {
    name: 'MyComponent',
    data(){
      return{
        nama : '',
        cari : '',
        alamat :'Tanjungsari',
        produk : [ ]
      }
    },
    beforeCreate(){
      console.log('beforeCreate')
    },
    created(){
      this.produk = [
      {id:1, title:'produk 1', harga:200},
          {id:2, title:'produk 2', harga:300},
          {id:3, title:'produk 3', harga:400},
          {id:4, title:'produk 4', harga:500},
      ];
    },

    methods : {
      fullAddress(){
        this.alamat = ' Kabupaten Sumedang'
      }
    },
    computed : {
      cariData(){
        return this.produk.filter((item)=>{
          return item.title.match(this.cari);
        })
      }
    }
  }
  </script>
  
  <style scoped>
  .my-component {
    color: blue;
  }
  </style>
  