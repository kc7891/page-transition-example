<template>
  <div class="pageComponent">
    <section class="pageSection">
      <logo colorType="default"/>
      <h1 class="title">
        page-transition-example
      </h1>
      <h2 class="subtitle">
        Page 1
      </h2>
    </section>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style scoped>
.pageComponent {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
}

.pageSection {
    position: relative;
    top: 50%;
    transform: translateY(-50%);
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
