<template>
  <main-layout id="home-page">
    <hero-section></hero-section>
    <introduction></introduction>
  </main-layout>
</template>

<script>
  import MainLayout from '~/layouts/main-layout'
  import HeroSection from './hero-section'
  import Introduction from './introduction'

  export default {
    data () {
      return {
        message: 'Welcome!',
        height: null
      }
    },
    components: {
      MainLayout,
      HeroSection,
      Introduction
    },
    props: {

    },
    computed: {

    },
    methods: {

    }
  }
</script>

<style lang="scss" scoped>
  #home-page {
    display: flex;
    flex-direction: column;
  }
</style>
