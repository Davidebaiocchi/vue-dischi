<template>
  <div id="app">
    <Header/>
    <Main/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
  }
}

</script>

<style lang="scss">
  * {
    box-sizing: border-box;
    margin: 0;
    border: 0;
  }
</style>
