<template>
  <div class="right">
    <ul>
      <li v-for="(item,index) in list" :key="index" :class="{current:item.flag}" @click="changeRight(index)">{{item.name}}</li>
    </ul>
  </div>
</template>
<script>
export default {
  props: {
    list: Array
  },
  components: {},
  data() {
    return {};
  },
  computed: {},
  methods: {
      changeRight(index){
          this.list[index].flag=! this.list[index].flag;
          //console.log(this.list[index])
      }
  },
  created() {},
  mounted() {}
};
</script>
<style scoped lang="">
.right {
  flex: 1;
  height: 100%;
}
ul {
  display: flex;
  width: 100%;
  flex-wrap: wrap;
  list-style: none;
}
li {
  width: 29%;
  height: 44px;
  line-height: 44px;
  border: 1px solid seagreen;
  border-radius: 5px;
  margin: 5px;
  text-align: center;
}
.current {
  background: skyblue;
}
</style>