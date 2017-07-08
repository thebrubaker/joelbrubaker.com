<template>
  <transition name="fade">
    <main-layout id="home-page" v-show="ready">
      <hero-section ref="hero"></hero-section>
      <introduction></introduction>
    </main-layout>
  </transition>
</template>

<script>
  import MainLayout from '~/layouts/main-layout'
  import HeroSection from './hero-section'
  import Introduction from './introduction'
  import { mapComputed } from '~/utils/vuex'

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
      ...mapComputed([
        'ready'
      ])
    },
    methods: {

    },
    mounted () {
      this.ready = true
      this.$nextTick(() => {
        this.$refs.hero.height = document.querySelector('.section__hero').clientHeight
      })
    }
  }
</script>

<style lang="scss" scoped>
  #home-page {
    display: flex;
    flex-direction: column;
  }
</style>
