<template>
  <div id="app">
    <myleft :list="list" @change="change"></myleft>
    <myright :list="list[index].cities" v-if="list[index]"></myright>
  </div>
</template>

<script>
import myleft from "./components/myleft";
import myright from "./components/myright";
import axios from "axios";
export default {
  components: {
    myleft,
    myright
  },
  data() {
    return {
      index: 0,
      list: []
    };
  },
  created() {
    axios.get("/api/city").then(res => {
      this.list = res.data.data;
     // this.list[this.index].cities.forEach(item => (item.flag = this.$set(item,'flag',false)));
    });
  },
  watch:{
    index(news,olds){
      //console.log(news)
      this.list[this.index].cities.forEach(item => (item.flag = this.$set(item,'flag',false)));
    }
  },
  methods: {
    change(index) {
      this.index = index;
     // console.log(index);
    }
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
body,
html,
#app {
  width: 100%;
  height: 100%;
}
#app {
  display: flex;
}
</style>