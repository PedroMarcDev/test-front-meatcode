<script>
import Hero from './components/Hero.vue';
import Articles from './components/Articles.vue'
import ContactForm from "./components/ContactForm.vue";

export default {
  components: {
    Hero,
    Articles,
    ContactForm
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
  <main class="articles__container">
    <section>
      <div class="articles__content">
        <Articles />
      </div>
    </section>
    <section class="contactform__container">
      <ContactForm />
    </section>
  </main>

</template>