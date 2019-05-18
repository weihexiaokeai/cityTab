<template>
  <div id="app">
          <my-left
            :list="listCity"
            @chang="changData"
          ></my-left>
         <my-right
         :list="listCity[ind].cities" v-if="listCity[ind]"></my-right>
      
  </div>
</template>

<script>
import myLeft from './components/left'
import myRight from './components/right'
import axios from 'axios'
export default {
  name: 'App',
  components: {
   myLeft,
   myRight
  },
  data()
  {
    return{
        ind:0,
        listCity:[]
    }
  },
  created()
  {
      axios.get("/api/city").then((res)=>{
        console.log(res.data)
        this.listCity=res.data.data
        this.listCity[this.ind].cities.forEach(item=>this.$set(item,'flag',false))
          console.log(this.listCity)
      })
  },
  watch:{
          ind(news,olds)
          {
           
               this.listCity[news].cities.forEach(item=>this.$set(item,'flag',false))  
          }
  },
  methods:{
        changData(value){
          this.ind=value
            console.log(value)
        }
  }
  
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  border: 0;
  list-style: none;
}
html,body,#app{
  width: 100%;
  height: 100%;
}
#app{
   display: flex;
}

</style>
