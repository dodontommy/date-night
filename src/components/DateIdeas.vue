<template>
  <div id="ideas-container">
    <div class="idea fade" 
        :class="{['hidden']: this.singleDisplay != index}" 
        v-for="(idea, index) in this.ideas" v-bind:key="idea.animation_ident" 
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
      singleDisplay: null,
      ideas: []
    }
  },
  watch: {
    data() {
      this.data.forEach((idea) => {
        this.ideas.push({
           "id": this.data.indexOf(idea),
           "name": idea.name,
           "animation_ident": 'id-' + this.data.indexOf(idea) + '-' + Math.floor(Math.random() * 10000)
          })
      })

     this.animate()
    }
  },
  methods: {
    animate: async function() {
      let interval = 0
      let max = 15

      while(interval < max) {
        setTimeout(() => {
          let i = Math.floor(Math.random() * Object.keys(this.data).length)
          let idea = this.ideas[i]
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
