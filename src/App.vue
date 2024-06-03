<template>
  <h1>App</h1>
  <h4>{{ nama }}</h4>
  <MyComponent/>
</template>


<script>
import MyComponent from './components/myComponent.vue';

export default {
  name: 'App',
  data(){
    return{
      nama : 'Fauzi Ramdani'
    }
  },
  components: {
   MyComponent
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
</style>
