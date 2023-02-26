<template>
  <div id="app">
    <HelloWorld/>
  </div>
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
.selects {
    background: rgb(151, 251, 151) !important;
}

td {
    width: min-content;
}

td,
th {
    text-align: center !important;
    border: 1px solid black !important;
    ;
}

th {
    color: black !important;
    ;
    background: #ace2c8 !important;
    ;
}

.active {
    border: 5px solid green
}
</style>
