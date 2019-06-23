<template>
    <div class="popUp" v-if="isShow">
        <div class="popUpContent">
            <h2>{{desc.title}}</h2>
            <p>{{desc.content}}</p>
        </div>
        <div class="close" @click="closePop"><img src="../assets/close.png" alt=""></div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            
        }
    },
    props: {
        desc: {
            default: {},
            type: Object
        },
        isShow:   false
    },
    methods: {
        closePop(data) {
            this.$emit('  close',data)
        }
    }

}
</script>

<style scoped>
.popUp{
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction:column;
    background-color : rgba(0,0,0,.3);
    position: fixed;
    left: 0;
    top: 0;
}
.popUpContent{
    background-color: #fff;
    width: 70%;
    height: 35vh;
    margin-top: -50%;
    border-radius: .1rem;
    padding: .2rem;
}
.close {
    padding: .5rem;
}
.close img{
    width: .5rem;
    height: .5rem;


}

</style>
