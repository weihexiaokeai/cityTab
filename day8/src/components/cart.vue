<template>
    <div class="box">
         <header><h3>每日优鲜便利购</h3></header>
         <ul  class="ulist">
                    <li v-for="(item,index) in cart" :key="index" @click="btnclick(index)">
                     <img :src="item.img" alt="">
                        <p>{{item.title}}</p>
                        <p><span>{{item.pirce}}元/袋</span><span class="add" @click="sumAdd(item.pirce)">+</span></p>
                        
                    </li>
                     
                        
                
                  
                     
         </ul>
    </div>
</template>
<script>
export default {
     props:{
          cart:Array,
          sum:Number,
          sumPrice:0,
     },
     methods:{
         btnclick(index)
         {
              var flag= this.cart[index].flag=!this.cart[index].flag
          
         },
         sumAdd(price)
         {
              this.sumsumPrice=price;
            
             this.$emit("priceAdd",this.sum,this.sumPrice)
         }

     }
}
</script>

<style scoped>
        .box{
            width: 100%;
            flex: 1;
           
        }
        header{
            width: 100%;
            height: 44px;
            background: orange;
            text-align: center;
        }
        header h3{
            line-height: 44px;
        }
        .ulist{
            width: 100%;
            flex: 1;
            display: flex;
            flex-wrap: wrap;
        }

          .ulist li{
              width: 30%;
              height: 150px;
              background: #ccc;
              margin: 10px 5px;
          }
          img{
              width: 100%;
          }
          .add{
              font-size: 25px;
              margin: 0 10px;
              background: orange;
          }
          </style>
