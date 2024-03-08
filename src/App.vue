<script>
import Hero from './components/Hero.vue';
import Articles from './components/Articles.vue'

export default {
  components: {
    Hero,
    Articles
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
  <Html lang="es">

  <Head>
    <Title>El secreto de tu cocina</Title>
    <Meta name="description" content="El secreto de tu cocina" />
  </Head>


  <Hero />
  <main class="articles__container">
    <section>
      <div class="articles__content">
        <Articles />
      </div>
    </section>
  </main>

  </Html>

</template>