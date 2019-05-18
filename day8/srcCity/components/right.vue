<template>
    <div class="wrapper">
        <ul class="ulist">
                <li  v-for="(item,index) in list" :key="index"
                :class="{'active':item.flag}"
                @click="changRight(index)"
                >

                    {{item.name}}
                </li>
                
        </ul>
    </div>
</template>
 <script>
 export default {
     props:{
         list:Array
     },
     methods:{
         changRight(ind){
            this.list[ind].flag=!this.list[ind].flag
             console.log(ind)
         }
     }
     
 }
 </script>
 
<style scoped>

.wrapper{
    flex: 1;
    height: 100%;
}
.ulist{
    width: 100%;
    height: auto;
    display: flex;
   flex-wrap: wrap;
}
.ulist li{
    width: 30%;
    height: 40px;
    text-align: center;
    line-height: 40px;
    border: 1px solid firebrick;
    margin: 2px;
}
.active{
    background:yellow;
}

</style>
