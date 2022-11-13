<template>
  <div id="ideas-container">
    <div class="idea fade" 
        :class="{['hidden']: this.singleDisplay != index}" 
        v-for="(idea, index) in this.data" v-bind:key="index" 
        v-bind:id='"idea-" + index'>
      {{ idea.name }}
    </div> 
  </div>
</template>

<script>
export default {
  name: 'DateIdeas',
  props: {
    data: Object
  },
  data() {
    return {
      currentDisplay: null,
      singleDisplay: null
    }
  },
  watch: {
    data() {
      this.currentDisplay = this.data
      this.singleDisplay = Math.floor(Math.random() * Object.keys(this.data).length)
    }
  }
}
</script>

<style scoped lang="scss">
.fade {
  animation: fade 1.5s ease-in;
}

@keyframes fade {
  from {opacity: 0}
  to {opacity: 1}
}

.idea{
  animation-name: fade;
  animation-duration: 750ms;
  animation-fill-mode: forwards;
  font-size: 36px;
}

.hidden {
  display: none;
}
</style>
