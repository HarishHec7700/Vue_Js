<template>
  <div class="hello">
    <b>{{ name }}</b>
    {{ desp }}
    <p :class="className">Here is an example for the HTML Directive "v-html"</p>
    <span v-html="binHtml"></span>
    <br />
    <button v-bind:disabled="isDisabled" on-click="()=>{isActive:false}">NO</button>
    <!-- Binding the classess -->
    <h2 :class="{isActive}">Welcome</h2>
    <h2 :class="{active:isActive,disabled:isDisabled}">Come</h2>
    <p :class="status">Some random Text</p>
    <!-- Inline stye Method -->
    <!-- We use Inline style binding only when u have only one style to bind -->
    <h4 :style="{fontSize}">Style Binding</h4>

    <!-- Object Style Binding -->
    <!-- We use object style binding only when u have many styles to bind -->
    <h4
      :style="objStyle"
    >Object Style Binding</h4>
  <h4
      :style="[objStyle,backStyle]" 
    >Array of Object Style Binding</h4>
    <!-- If any style is common then the last style will apply  -->
  </div>
  <!-- here {{   }} is the mustache syntax the method of binding text using mustache syntax is called text interpolation  -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: "App",
  data() {
    return {
      name: "Hector",
      desp: "A great warrior",
      // Binding the HTML
      binHtml: "<b>This is the HTML dircetive using v-html </b>",
      // Binding the Attributes
      className: "bind",
      // Binding the Boolean Attributes
      isDisabled: true,
      isActive: true,
      status: "warning",
      fontSize: 2.5 + "rem",
      objStyle: {
        padding: "10px",
        color: "red",
        fontWeight: "700"
      },
      backStyle: {
        padding: "20px",
        backgroundColor: "green",
        border:"solid 5px #000"
      }
    };
  }
};
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
.bind {
  color: green;
}
.isActive,
.active {
  text-decoration: underline;
}
.warning {
  color: orange;
}
</style>
