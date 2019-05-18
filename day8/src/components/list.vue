<template>
    <div class="footer">
       <div class="footerLeft">
           <div><span>{{sum}}</span></div>
           <div>
               <p>总计￥{{sumPrice}}元</p>
               <p>已优惠4.5元</p>
           </div>
       </div>
       <div class="right">去结算</div>
    </div>
</template>
<script>
export default {
    props:{
        sumPrice:Number,
        sum:Number
    }
}
</script>

<style scoped>

.footer{
    width: 100%;
    height: 50px;
    display: flex;
}
.footerLeft{
    width: 70%;
    height: 50px;
    background: rgba(0, 0, 0, .7);
    display: flex;
    justify-content: space-around;
}
.right{
    flex: 1;
    height: 50px;
    background: fuchsia;
    font-size: 18px;
    text-align: center;
    line-height: 50px;
    color: #fff;
}
</style>

