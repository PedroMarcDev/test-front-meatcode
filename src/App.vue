<script>
import Hero from './components/Hero.vue';

export default {
  components: {
    Hero
  },
  props: {
    campaign: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
    }
  },
  watch: {

  },
  mounted() {

  },
  methods: {

  }
}

</script>


<template>
  <Hero />
</template>