<template>
  <div id="date-night">
    <DateIdeas :data=this.selectedData />
    <div v-for="(data, index) in dateNightData" v-bind:key="index" class="date-category">
      <DateCategory :data=data @clicked="clickEvent" />
    </div>
  </div>
</template>

<script>
import DateNightJson from '../data/date-night.json'
import DateCategory from './DateCategory.vue'
import DateIdeas from './DateIdeas.vue'

export default {
  name: 'DateNightComp',
  data() {
    return {
      dateNightData: DateNightJson,
      selectedData: null
    }
  },
  components: {
    DateCategory,
    DateIdeas
  },
  methods: {
    clickEvent: function(dateIdeas) {
      this.selectedData = dateIdeas;
    }
  }
}
</script>

<style scoped>
#date-night {
  width: 100%;
}
.date-category {
  display: inline-block;
  margin: 15px;
}
</style>
