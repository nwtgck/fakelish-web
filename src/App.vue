<template>
  <div id="app">
    <h1>Fakelish</h1>
    <a href="https://github.com/nwtgck/fakelish-npm">GitHub</a>
    <Fakelish />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Fakelish from './components/Fakelish.vue';

@Component({
  components: {
    Fakelish,
  },
})
export default class App extends Vue {}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
