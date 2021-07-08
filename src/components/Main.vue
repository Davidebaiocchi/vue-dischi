<template>
  <div class="container-main">
      <div class="dischi">
              <div class="disco text-center" v-for="(disco, index) in arrayDischi" :key="index">
                    <img :src="disco.poster" alt="album disco">
                    <div class="title descr"> {{ disco.title }} </div>
                    <div class="descr grey mt-10"> {{ disco.author }} </div>
                    <div class="descr grey"> {{ disco.year }} </div>     
              </div>
      </div>
  </div>
</template>


<script>
import axios from 'axios';
export default {
  name : 'Main',
  components: {
  },
  data(){
    return{
      urlApi : 'https://flynn.boolean.careers/exercises/api/array/music',
      arrayDischi : []
    }
  },
  methods: {
    loadApi(){
      axios
        .get(this.urlApi)
        .then(response => {
          this.arrayDischi = response.data.response;
          console.log(this.arrayDischi);
        });
    }
  },
  mounted(){
    this.loadApi();
  }
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import 'bootstrap';
    .container-main {
        background-color: hsl(209, 32.6%, 17.5%);
        height: calc(100vh - 50px);
        width: 100%;
        overflow-y: hidden;
    }

    ul {
        list-style: none;
    }

    img {
        width: 190px;
        height: 190px;
    }

    .dischi {
        display: flex;
        color: white;
        display: flex;
        flex-wrap: wrap;
        overflow: hidden;
        margin: 0 auto;
        width: 80%;
    }

    .disco {
        background-color: rgba(255, 255, 255, 0.103);
        margin: 30px;
        padding: 20px;
        padding-bottom: 10px;
    }

    .title {
        font-size: 25px;
        text-transform: uppercase;
        padding-top: 10px;
    }

    .descr {
        width: 190px;
    }

    .grey {
        color: grey;
        font-size: 20px;
    }

    .mt-10 {
        margin-top: 20px;

    }
</style>