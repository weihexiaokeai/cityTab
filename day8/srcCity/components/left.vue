<template>
    <div class="box">
        <ul class="ulist">
            <li v-for="(item,index) in list" 
            :key="index" @click="btnClick(index)">{{item.name}}</li>
             
        </ul>
    </div>
</template>
<script>
export default {
      props:{
          list:Array
      },
      methods:{
           btnClick(index)
           {    
               this.$emit("chang",index)
           }
      }
}
</script>

<style scoped>
.box{
    width: 120px;
    height: 100%;
    overflow: auto;
    border-right: 1px solid #ccc;
}
.ulist{
     width: 100%;
     height: 100%;
}
.ulist li{
        width: 80px;
        height: 30px;
        background: orangered;
        margin: 10px;
        text-align: center;
        line-height: 30px;
        color: #fff;
}
</style>

