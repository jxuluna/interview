<template>
<div class="vip">
    <div class="header">
        <img src="../../assets/back.png" alt="">
        <div class="item-top">VIP中心</div>
        <img src="../../assets/staff.png" alt="">
    </div>
    <div class="contentChoose">
        <div class="chooseType" :class="{'chooseActive' : isChoose==0}" @click = changeavtive(0)>
          <div><h2>高级版</h2>
          <p>适合独立摄影师</p></div>  
        </div>
        <div class="chooseType" :class="{'chooseActive' : isChoose==1}"  @click = changeavtive(1)>
          <div>
              <h2>定制版</h2>
          <p>适合小型工作室</p>
              </div>  
        </div>
    </div>
    <div class="blank"></div>
    <div class="iconContent">
        <div class="title" v-if="isChoose == 0 ">
            <h2>高级版<span>（适合<span class="spanRed">独立摄影师</span>）</span></h2>
        </div>
         <div class="title" v-else>
            <h2>定制版<span>（适合<span class="spanRed">小型工作室</span>）</span></h2>
        </div>
    </div>
    <div class="list">
        <div class="listContent" v-for='(item,index) in list' :key = 'index' @click="showPopUp(item)">
            <div class="listIcon">
               <div class="iconIcon" :class="{'iconA': isChoose==0 && item.highlight == 0}">{{item.listIcon}}</div>
            </div>
            <div class="iconTitle">{{item.title}}</div>
        </div>
    </div>
    <popUp :isShow='ishow' :desc='content' @close='close'></popUp>
</div>
    
</template>

<script>
import popUp from '../../components/popUp'
export default {
    data () {
        return {
            list: [
                {
                    highlight: 1,
                    listIcon : 'A',
                    title: '标题1',
                    content: 'dgasdghjshdasdhjkdsajhdk'
                },
                {
                    highlight: 0,
                    listIcon : 'A',
                    title: '标题2',
                    content: 'dgasdghjshdasdhjkdsajhdk'
                },
                {
                    highlight: 1,
                    listIcon : 'A',
                    title: '标题3',
                    content: 'dgasdghjshdasdhjkdsajhdk'
                },
                {
                    highlight: 1,
                    listIcon : 'A',
                    title: '标题4',
                    content: 'dgasdghjshdasdhjkdsajhdk'
                },
                {
                    highlight: 0,
                    listIcon : 'A',
                    title: '标题5',
                    content: 'dgasdghjshdasdhjkdsajhdk'
                },
                {
                    highlight: 0,
                    listIcon : 'A',
                    title: '标题6',
                    content: 'dgasdghjshdasdhjkdsajhdk'
                },
                {
                    highlight: 0,
                    listIcon : 'A',
                    title: '标题7',
                    content: 'dgasdghjshdasdhjkdsajhdk'
                },
                {
                    highlight: 1,
                    listIcon : 'A',
                    title: '标题8',
                    content: 'dgasdghjshdasdhjkdsajhdk'
                },
                {
                    highlight: 0,
                    listIcon : 'A',
                    title: '标题9',
                    content: 'dgasdghjshdasdhjkdsajhdk'
                },
                {
                    highlight: 1,
                    listIcon : 'A',
                    title: '标题10',
                    content: 'dgasdghjshdasdhjkdsajhdk'
                },
            ],
            isChoose: 0,
            content: {},
            ishow: false
            
             
        }
    },
    methods :{
        changeavtive (index) {
            this.isChoose = index;

        },
        showPopUp (item) {
            if (this.isChoose == 0 && item.highlight == 0) {
                return false
            }
            this.ishow = true
            this.content = item
        },
        close () {
            this.ishow = false
        }
    },
    components : {
        popUp
    }


}
</script>

<style scoped>
.vip{
    width: 100%;
}
.header{
    display: flex;
    justify-content:space-between;
    align-items: center;
    padding: 0 .2rem;
    height: .88rem;
    border-bottom : 2px solid rgb(247,247,247); 
}
.header img{
    width: .48rem;
    height: .48rem;
}
.header div {
    font-size: .32rem;
}
.contentChoose{
    display: flex;
}
.chooseType{
    margin: .2rem .1rem .1rem .1rem;
    width: 50%;
    height: 2.5rem;
    background-color: rgb(246,246,246); 
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid #dbdbdb; 
}
.chooseType p{
    color: #cdcdcd;
}
.blank{
    width: 100%;
    height: .2rem;
    background-color: rgb(246,246,246); 
}
.title span{
    font-size: .24rem;
    color:  #cdcdcd;
}
.spanRed{
    color: rgb(255,114,119) !important;
}
.title{
    text-align: left;
    margin: .3rem;
}
.list{
    display: flex;
    flex-wrap: wrap;  
    justify-content: center;
}
.list img{
    width:.48rem;
    height:.48rem;
    
}
.listIcon{
    background-color: rgb(255,234,232);
    width: 1rem;
    border-radius: 50%; 
    height: 1rem;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: .2rem;
}
.chooseActive{
    color: rgb(255,114,119);
    background-color: rgb(255,248,246);
    border: 1px solid rgb(255,114,119);
}
.chooseActive  p{
    color: rgb(255,114,119) ;
}
.iconA{
    opacity: 0.2;
}
</style>
