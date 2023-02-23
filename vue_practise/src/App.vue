<template>
  <div class="hello">{{ greet }} {{ pname }}
    <a href="#" v-text="pname"></a>
    
    </div>   
  <!-- here {{   }} is the mustache syntax the method of binding text using mustache syntax is called text interpolation  -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data(){
    return{
      greet:"Hello",
      pname:"Kanni appan",
    }
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
