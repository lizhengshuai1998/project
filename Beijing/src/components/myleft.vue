<template>
    <div class="left">
        <ul>
            <li
            v-for="(item,index) in list"
            :key="index"
            @click="changeLeft(index)"
            >{{item.name}}</li>
        </ul>
    </div>
</template>
<script>
export default {
    props:{
        list:Array
    },
    components:{

    },
    data(){
        return {

        }
    },
    computed:{

    },
    methods:{
     changeLeft(index){
         this.$emit('change',index)
        // console.log(index)
        }
    },
    created(){

    },
    mounted(){
       
    }
}
</script>
<style scoped lang="">
.left{
    width: 120px;
    height: 100%;
    overflow-y: auto;
    border-right:1px solid #ccc; 
}
li{
    height: 44px;
    line-height: 44px;
    background: #007ACC;
    color:#285C2A;
    border-radius: 5px;
    margin:5px;
    text-align: center;
}
</style>