<template>
    <div>
        <div class="top">
                <h3>{{title}}</h3>
                <span class="sty">{{list[type-0]}}</span>
        </div>
        <p>{{content}}</p>
        <div class="time">
                <span>面试时间:{{time}}</span>
                <span>{{bool ? '已提醒':'未提醒'}}</span>
        </div>
    </div>
</template>

<script>
export default {
    props:['title','content','time','type','bool'],
    data(){
        return{
                 list:['已开始','已打卡','已放弃','全部']
        }
    }
}
</script>
<style scoped>
.wrapper{
    width: 100%;
    height: 100%;
}
p{
         padding: 10px;
        box-sizing: border-box;
}
.sty{
    background: orange;
    color: #fff;
}
  .top,.time{
          margin-top: 30px;
        display: flex;
        justify-content: space-between;
        padding: 10px;
        box-sizing: border-box;
  }
</style>

