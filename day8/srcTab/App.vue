<template>
  <div id="app">
        <header>
          <span v-for="(item,index) in typeList" :class="{active:ind==index}" @click="btnclick(index)" :key="index">{{item}}</span>
          
        </header>
        <section>
          <div v-if="list.length==0">当前分类没有</div>
               <my-list
          v-for="(item,index) in list"
          :key="index"
          :title="item.title"
          :content="item.content"
          :time="item.time"
          :type="item.type"
          :bool="item.bool"
        ></my-list>

        </section>
     
  </div>
</template>
<script>
 import  data from './mock'
 import MyList from './components/list'
export default {
  name: 'App',
  data(){
       
        return{ 
              ind:0,
              list:[],
              typeList:['已开始','已打卡','已放弃','全部']
             
        }
       
        
  },
  components: {
    MyList
  },
  created(){
   //this.list=data.list.filter(item=>item.type==0)
   this.list=this.getList(0)
    console.log(this.list)
  },
  methods:{
    btnclick(ind){
      this.ind=ind
      this.list=this.getList(ind)
    },
    getList(type)
    {
       return data.list.filter(item=>item.type==type)
    }

  }

}
</script>

<style>
  #app{
    display: flex;
    flex-direction: column;
  }
  header{
    width: 100%;
    height: 44px;
    display: flex;
    background: blue;

  }
  header span{
    flex: 1;
    text-align: center;
    height: 44px;
    line-height: 44px;
  }
  .active{
    color: #fff;
  }
  section{
    width: 100%;
    flex: 1;
    overflow:hidden;
  }
</style>
