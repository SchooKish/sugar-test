<template>
  <div
    class="main-layout container-fluid min-vh-100 d-flex flex-column p-0"
    :class="{'main': isMain}"
  >
    <div class="content min-vh-100">
      <Header/>
      <Nuxt/>
    </div>
  </div>
</template>

<script>
export default {
  computed: {
    isMain() {
      return this.$route.name === 'main'
    }
  }
}
</script>

<style scoped>
  .main-layout {
    background: url("~/assets/image/bg.jpg") no-repeat;
    background-size: cover;
  }

  .main {
    background: url("~/assets/image/unlock.jpg") center repeat;
    background-size: auto;
  }

  .content {
    backdrop-filter: grayscale(70%);
    display: grid;
    grid-template-rows: min-content auto;
  }
</style>
