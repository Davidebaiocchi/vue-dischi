<template>
  <div class="container-main">
      <div class="dischi">
          <ul>
              <li>

              </li>
          </ul>
      </div>
  </div>
</template>

<script>
import axios from 'axios'


export default {
    name: 'Main',
    data() {
        return {
            apiUrl : 'https://flynn.boolean.careers/exercises/api/array/music',
            arrayDischi : ''
        }
    },
    created() {
        this.getDischi();
    },
    methods: {
        getDischi() {
            axios
            .get(this.apiUrl)
            .then(response => {
                this.arrayDischi = response;
                console.log(this.arrayDischi);
            })
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .container-main {
    background-color: hsl(209, 32.6%, 17.5%);
    height: calc(100vh - 50px);
    text-align: center;
  }

</style>