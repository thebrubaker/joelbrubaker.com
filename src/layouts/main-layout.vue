<template>
  <div class="layout__container">
    <page-header></page-header>
    <main class="layout__content">
      <slot></slot>
    </main>
    <page-footer></page-footer>
  </div>
</template>

<script>
  import PageHeader from '~/components/page-header'
  import PageContent from '~/components/page-content'
  import PageFooter from '~/components/page-footer'

  export default {
    name: 'MainLayout',
    components: {
      PageHeader,
      PageContent,
      PageFooter
    }
  }
</script>

<style lang="scss" scoped>
  .layout {
    &__container {
      display: flex;
      flex-direction: column;
      min-height: 100vh;
    }

    &__content {
      display: flex;
      flex-direction: column;
      align-items: center;
      flex: 1;
    }
  }
</style>
