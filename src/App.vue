<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" width="25%">
    <HelloWorld msg="Hello Vue in CodeSandbox!"/>
    <FirstComponent header="My first Vue component" v-bind:tip="tip"/>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import FirstComponent from "./components/VueLearningStart";

export default {
  name: "App",
  components: {
    HelloWorld,
    FirstComponent
  },
  data: function() {
    return {
      tip: "redirect to next page"
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
