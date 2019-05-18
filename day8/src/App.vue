<template>
  <div id="app">
        <my-section
         :cart="cartList"
          :sum="sum"
          :sumPrice="sumPrice"
          @priceAdd="addSum()"
          >
        
        </my-section>
        <my-botton
        :sum="sum"
        :sumPrice="sumPrice"></my-botton>
  </div>
</template>

<script>
import mySection from './components/cart'
import myBotton from './components/list'
export default {
  name: 'App',
  components: {
   mySection,
  myBotton
  },
  data()
  {
    return{
        sum:0,
       sumPrice:0,
       cartList:[
               {
                img:"https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=1648378125,1150707632&fm=26&gp=0.jpg",
                title:"科迪纯牛奶1袋",
                pirce:2.5,
                flag:false
              
               },
                 {
                img:"https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1225082726,3404146229&fm=26&gp=0.jpg",
                title:"活润芒果酸牛奶",
                pirce:9.9,
                flag:false,
               },
                 {
                img:"https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=4109564529,1639036679&fm=11&gp=0.jpg",
                title:"畅轻燕麦+黄桃",
                pirce:6.9,
                flag:false,
               
               },
                 {
                img:"https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=2541475856,2392476867&fm=26&gp=0.jpg",
                title:"活润草莓酸牛奶",
                pirce:9.9,
                flag:false
              
               }
       ]
    }
  },
  created()
  {
     
  },
 
  methods:{
      addSum(sum,sumPrice){
        // this.sum=sum++
        //  this.sumPrice=sumPrice++
        console.log(this.sumPrice++)
        //  console.log(this.sum++,this.sumPrice++)
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
   flex-direction: column;
}

</style>
