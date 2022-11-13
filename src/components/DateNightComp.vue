<template>
  <div id="date-night">
    <div v-for="(data, index) in dateNightData" v-bind:key="index" class="date-category">
      <DateCategory :data=data />
    </div>
  </div>
</template>

<script>
import DateNightJson from '../data/date-night.json';
import DateCategory from './DateCategory.vue';
export default {
  name: 'DateNightComp',
  data() {
    return {
      dateNightData: DateNightJson
    }
  },
  components: {
    DateCategory
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#date-night {
  width: 100%;
}
.date-category {
  display: inline-block;
  margin: 15px;
}
</style>
