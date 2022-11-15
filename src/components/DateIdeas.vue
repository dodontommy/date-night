<template>
  <div id="ideas-container">
    <div class="idea fade" 
        :class="{['hidden']: this.singleDisplay != index}" 
        v-for="(idea, index) in this.currentDisplay" v-bind:key="index" 
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
      singleDisplay: null,
      ideas: []
    }
  },
  computed: {
    currentDisplay() {
      return this.data
    }
  },
  watch: {
    data() {
      this.animate()
    }
  },
  methods: {
    // Animate cycling through date ideas
    // Using animation_ident as a random identifier just to update the v-bind:key
    // which will force a DOM redraw. Randomly cycle through the date ideas 
    // displaying a new one until we finally land on one.
    animate: async function() {
      let interval = 0
      let max = 15

      while(interval < max) {
        setTimeout(() => {
          let i = Math.floor(Math.random() * Object.keys(this.data).length)
          let idea = this.data[i]
          idea.animation_ident = 'id-' + i + '-' + Math.floor(Math.random() * 10000)
          this.singleDisplay = i
        }, (250 * interval))  
      , interval++}
    }
  }
}
</script>

<style scoped>
.fade {
  animation: fade 0.25s ease-in;
}

@keyframes fade {
  0%   { opacity:0; }
  50%  { opacity:1; }
  100% { opacity:0; }
}

.idea{
  animation-name: fade;
  animation-duration: 250ms;
  font-size: 36px;
}

.hidden {
  display: none;
}
</style>
