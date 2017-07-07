<template>
  <header class="page__header">
    <div class="stripe" :class="{ slide: slideHeader}"></div>
    <button class="menu" type="button">menu</button>
  </header>
</template>

<script>
export default {
  data () {
    return {
      slideHeader: false,
      innerHeight: 0,
      scroll: 0
    }
  },
  components: {

  },
  props: {

  },
  computed: {

  },
  methods: {

  },
  watch: {
    scroll () {
      if (this.scroll - this.innerHeight + 60 >= 0) {
        this.slideHeader = true
      } else {
        this.slideHeader = false
      }
    }
  },
  mounted () {
    this.innerHeight = window.innerHeight
    window.addEventListener('scroll', event => {
      this.scroll = window.scrollY
    }, false)
  }
}
</script>

<style lang="scss" scoped>
.page__header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  .stripe {
    height: 55px;
    transform: translateY(-48px);
    transition: 0.2s;
    background: #DE6262;
    background: -webkit-linear-gradient(to right, #FFB88C, #DE6262);
    background: linear-gradient(to right, #FFB88C, #DE6262);
  }
  .stripe.slide {
    transition: 0.2s;
    transform: translateY(0);
  }
  .menu {
    background-color: transparent;
    position: absolute;
    top: 18px;
    right: 6px;
    border: none;
    color:transparent;
    display: flex;
    flex-direction: column;
    align-items: center;
    font-size: 5px;
    &::after {
      content: '';
      background-color: white;
      width: 23px;
      height: 4px;
      display: block;
      border-radius: 2px;
    }
    &::before {
      content: '';
      background-color: white;
      width: 23px;
      height: 4px;
      display: block;
      border-radius: 2px;
    }
  }
}
</style>
