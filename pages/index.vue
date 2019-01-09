<template>
  <section class="container" :class="{reverse: isReverseTransition}">
    <transition-group name="pageTransition">
      <page1 key="page1" v-if="currentPage===1"/>
      <page2 key="page2" v-else-if="currentPage===2"/>
      <page3 key="page3" v-else/>
    </transition-group>
    <Footer @pageSelect="goSelectedPage"/>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'
import page1 from '~/components/page-1.vue'
import page2 from '~/components/page-2.vue'
import page3 from '~/components/page-3.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    Logo,
    page1,
    page2,
    page3,
    Footer,
  },
  data() {
    return {
      currentPage: 1,
      isReverseTransition: true,
    }
  },
  methods: {
    goSelectedPage( pageNumber ) {
      this.isReverseTransition = this.currentPage > pageNumber
      this.currentPage = pageNumber;
    }
  }
}
</script>

<style>

.container {
  min-height: 100vh;
  text-align: center;
  padding: 1px;
  border: 20px solid #38806f;
  overflow-x: hidden;
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
/* leaving page */
.pageTransition-leave-active {
  transition: opacity 0.7s, transform 1s;
  transform: translateX(-70%);
  opacity: 0;
}
.pageTransition-leave {
  opacity: 0;
  transform: translateX(0);
}
/* entering page */
.pageTransition-enter-active {
  transition: transform 1s;
  transform: translateX(0);
}
.pageTransition-enter {
  transform: translateX(100%);
}
/* reverse transition */
/* leaving page */
.reverse .pageTransition-leave-active {
  transition: opacity 0.7s, transform 1s;
  transform: translateX(70%);
  opacity: 0;
}
.reverse .pageTransition-leave {
  opacity: 0;
  transform: translateX(0);
}
/* entering page */
.reverse .pageTransition-enter-active {
  transition: transform 1s;
  transform: translateX(0);
}
.reverse .pageTransition-enter {
  transform: translateX(-100%);
}
</style>
