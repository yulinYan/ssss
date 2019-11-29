<template>
    <div class="tuijian-min-div">
        <h3 class="tuijian-min-h3">。。。</h3>
<!--        <a href="#/tuijianmjxmin">-->
        <a href="#/tuijianmjx">
            <p class="tuijian-min-p">今天就来欣赏一下吧。每次做这种征集都忍不住感叹，我到底拥有怎样一群神仙读者啊，长得美、还那么会拍，今天就来欣赏一下吧。每次做这种征集都忍不住感叹，我到底拥有怎样一群神仙读者啊，长得美、还那么会拍</p>
            <img class="tuijian-min-img" src="../../../assets/images/chengQ/tuijian/tuijian-min.jpg" alt="">
            <img class="tuijian-min-img" src="../../../assets/images/chengQ/tuijian/tuijian-min.jpg" alt="">
            <img class="tuijian-min-img" src="../../../assets/images/chengQ/tuijian/tuijian-min.jpg" alt="">
        </a>
        <div  class="tuijian-min-div1">
            <span class="tuijian-min-span-left">黎贝卡的异想世界</span>
            <span class="tuijian-min-span-right"><img src="../../../assets/images/chengQ/tuijian/guankan.png" alt="">1.8w</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: "chengQ-tuijian-min"
    }
</script>

<style scoped>
    .tuijian-min-div{
        background-color: white;
        border-bottom: 0.01rem solid #999;
    }
    .tuijian-min-h3{
        width: 96%;
        margin: 0 auto;
        text-align: right;
        padding-right: 4%;
        font-size: 0.12rem;
        font-weight: 400;
        height: 0.2rem;
    }
    .tuijian-min-img{
        width: 33%;
    }
    .tuijian-min-p{
        width: 96%;
        margin: 0 auto;
        text-align: left;
        padding-top: 0.05rem;
        /*padding-bottom: 0.05rem;*/
        padding-left: 4%;
        color: #666666;
        display: -webkit-box; /** 对象作为伸缩盒子模型显示 **/
        -webkit-box-orient: vertical; /** 设置或检索伸缩盒对象的子元素的排列方式 **/
        -webkit-line-clamp: 2; /** 显示的行数 **/
        overflow: hidden;  /** 隐藏超出的内容 **/
    }
    .tuijian-min-div1{
        width: 96%;
        margin: 0 auto;
        text-align: left;
        color: #666666;
        padding: 0.05rem 0 0.1rem 0.1rem;
    }
    .tuijian-min-span-left{

    }
    .tuijian-min-span-right{
        float: right;
        /*padding-right: 0.2rem;*/
    }
    .tuijian-min-span-right img{
       width: 25%;
    }
</style>