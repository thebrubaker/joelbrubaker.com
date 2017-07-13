<template>
  <div class="skills-section">
    <transition name="drop-down">
      <div class="card" v-if="showCards">
        <div class="left">
          <laravel-icon width="35" height="35" />
        </div>
        <div class="right">
          <h1>Laravel</h1>
          <p>A modern toolkit for building high-quality, well-tested backends and RESTful APIs.</p>
        </div>
      </div>
    </transition>
    <transition name="drop-down">
      <div class="card" v-if="showCards">
        <div class="left">
          <vue-icon width="35" height="35" />
        </div>
        <div class="right">
          <h1>Vue.js</h1>
          <p>A javascript framework for rapid interface development and lightning-fast single page apps.</p>
        </div>
      </div>
    </transition>
    <transition name="drop-down">
      <div class="card" v-if="showCards">
        <div class="left">
          <firebase-icon width="35" height="35" />
        </div>
        <div class="right">
          <h1>Firebase</h1>
          <p>Suite of tools for rapidly prototyping mobileapplications, without managing infrastructure.</p>
        </div>
      </div>
    </transition>
    <transition name="drop-down">
      <div class="card" v-if="showCards">
        <div class="left">
          <gcs-icon width="35" height="35" />
        </div>
        <div class="right">
          <h1>Google Cloud Platform</h1>
          <p>Secure, global, high-performance, cost-effective infrastructure with the smartest tools available.</p>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
import LaravelIcon from '~/components/laravel-icon'
import VueIcon from '~/components/vue-icon'
import GcsIcon from '~/components/gcs-icon'
import FirebaseIcon from '~/components/firebase-icon'

export default {
  data () {
    return {
      scroll: 0,
      offset: 0,
      showCards: true
    }
  },
  components: {
    LaravelIcon,
    VueIcon,
    GcsIcon,
    FirebaseIcon
  },
  props: {

  },
  computed: {

  },
  methods: {

  },
  watch: {
    scroll () {
      if (!this.showCards && this.scroll > this.offset + 350) {
        this.showCards = true
      }
    }
  },
  mounted () {
    this.$nextTick(() => {
      this.offset = this.$el.offsetTop
      window.addEventListener('scroll', () => {
        this.scroll = window.scrollY
      })
    })
  }
}
</script>

<style lang="scss" scoped>
  .log {
    position: fixed;
    top: 0;
    right: 0;
    z-index: 100;
  }
  .skills-section {
    background-color: rgb(245,245,245);
    width: 100%;
    min-height: 100vh;
    padding: 15px 15px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    @media (min-width: 400px) {
      flex-direction: row;
      flex-wrap: wrap;
      padding: 30px 15px;
    }
  }
  .card {
    background-color: white;
    border: 1px solid hsl(0, 5%, 90%);
    border-radius: 3px;
    display: flex;
    padding: 15px;
    margin: 10px 0;
    @media (min-width: 500px) {
      margin: 10px;
      flex: 0 0 25%;
      flex: 1;
    }
    h1 {
      font-family: 'Avenir';
      margin: 0 0 5px 0;
      font-size: 20px;
      color: hsl(0, 5%, 40%);
    }
    p {
      font-family: 'Avenir';
      margin: 0;
      font-size: 15px;
      line-height: 1.5em;
    }
    .left, .right {
      padding: 10px;
    }
  }
</style>
