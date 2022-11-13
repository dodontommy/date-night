<template>
  <MainApp/>
</template>

<script>
import MainApp from './components/MainApp.vue'
import 'primevue/resources/themes/nova/theme.css'
import 'primevue/resources/primevue.min.css'
import 'primeicons/primeicons.css'
export default {
  name: 'App',
  components: {
    MainApp
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
