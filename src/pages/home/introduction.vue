<template>
  <div class="introduction">
    <h2>Hello, I'm Joel Brubaker.</h2>
    <p>I'm an experienced full stack engineer that loves to build modern web applications. My favorite tools include <a target="_blank" href="https://laravel.com/">Laravel</a>, <a target="_blank" href="https://vuejs.org/">Vue.js</a>, <a target="_blank" href="https://firebase.google.com/">Firebase</a> and <a target="_blank" href="https://cloud.google.com/">Google Cloud Platform</a>.</p>
  </div>
</template>

<script>
export default {
  data () {
    return {

    }
  },
  components: {

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
  .introduction {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 10px 30px;
    height: 100vh;
    max-width: 900px;
    align-content: center;
  }
  p {
    font-size: 1.2em;
    line-height: 2em;
  }
  a {
    color: #2c3e50;
    border-bottom: 1px solid #FFB88C;
    &:hover {
      text-decoration: none;
    }
  }
</style>
