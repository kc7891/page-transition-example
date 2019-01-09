<template>
  <footer>
    <section class="contents">
      <div><a @click.stop="pageClickHandler( 1 )">page1</a></div>
      <div class="center-button"><a @click.stop="pageClickHandler( 2 )">page2</a></div>
      <div><a @click.stop="pageClickHandler( 3 )">page3</a></div>
    </section>
  </footer>
</template>

<script>
export default {
  methods: {
    pageClickHandler( pageNumber ) {
      this.$emit("pageSelect",pageNumber)
    }
  }
}
</script>

<style scoped>
  footer {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 50px;
    background-color: #35495e;
  }
  .center-button {
    border-left: 1px solid #6c7177;
    border-right: 1px solid #6c7177;
  }
  .contents {
    display: flex;
    flex-direction: row;
    height: 100%;
  }
  .contents > div {
    width: 33.3%;
    height: 100%;
  }
  .contents > div:hover {
    background-color: #455a70;
  }
  .contents > div > a {
    color: white;
    display: block;
    height: 100%;
    line-height: 50px;
    cursor: pointer;
  }
</style>
