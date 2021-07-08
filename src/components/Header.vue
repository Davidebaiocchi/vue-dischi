<template>
  <div class="container-main">
    <i class="fab fa-spotify"></i>
  </div>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .container-main {
    background-color: hsl(210, 20.7%, 22.7%);
    height: 50px;
  }
  i {
    color: rgb(10, 214, 10);
    font-size: 35px;
    padding: 6px;
    margin-left: 5px;
  }
</style>
