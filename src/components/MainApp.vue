<template>
  <div id="main-app">
    <DateNightComp/>
  </div>
</template>

<script>
import DateNightComp from './DateNightComp.vue';
export default {
  name: 'MainApp',
  components: {
    DateNightComp
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#main-app {
  display: flex;
  align-items:center;
  justify-content: center;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
}
</style>
