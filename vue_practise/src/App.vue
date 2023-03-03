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
    <h4 :style="objStyle">Object Style Binding</h4>
    <h4 :style="[objStyle,backStyle]">Array of Object Style Binding</h4>
    <!-- If any style is common then the last style will apply  -->

    <!-- Conditional Rendering  -->

    <h4 v-if="condi==2">This is Conditional Rendering Statement</h4>
    <h4 v-if="condi==0">Input is zero</h4>
    <h4 v-else-if="condi<0">Input is negative</h4>
    <h4 v-else>Input is positive</h4>
    <h4 v-show="backStyle.value">There is a value</h4>

    <!-- List Rendering in VueJs (Array) -->
    <h5>List Rendering in the Vue Js Using v-for for Array</h5>
    <ul>
      <li v-for="(name,index) in names" :key="index">{{name}}</li>
    </ul>

    <!-- List Rendering in VueJs (Array of Objects) -->
    <h5>List Rendering in the Vue Js Using v-for for Array of Objects</h5>
    <li v-for="(detail,index) in details" :key="index">
      This is {{ detail.name }}.
      <span v-if="detail.gender=='Male'">He</span>
      <span v-if="detail.gender=='Female'">She</span>
      is a {{ detail.occ }} and lives in {{detail.city}}
    </li>
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
        value: false,
        backgroundColor: "green",
        border: "solid 5px #000"
      },
      // Conditoinal Rendering in VueJs
      condi: -2,

      // List Rendering (Array) in VueJS
      names: ["Victor", "Julie", "Havana", "Beyonce"],

      // List Rendering (Array of Objects ) in VueJS
      details: [
        {
          name: "Victor",
          occ: "Gangster",
          city: "Chennai",
          gender: "Male"
        },
        {
          name: "Julie",
          occ: "Actress",
          city: "NewYork",
          gender: "Female"
        },
        {
          name: "Beyonce",
          occ: "Singer",
          city: "Kamamedu",
          gender: "Female"
        }
      ]
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
