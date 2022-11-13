<template>
  <div>
    <Button :class="
      {['p-button-raised']: true,
      ['p-button-rounded']: true,
      [this.data.class]: true}" @click="select" :label=this.data.category />
  </div>
</template>

<script>
import Button from 'primevue/button';
export default {
  name: 'DateCategory',
  emits: ['clicked'],
  props: {
    data: Object
  },
  components: {
    Button
  },
  methods: {
    select: function(e) {
      e.preventDefault();
      this.$emit('clicked', this.data.date_ideas);
    }
  },
  mounted() {
  }
}
</script>
<style>
</style>