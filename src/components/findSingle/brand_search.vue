<template>
    <div>
        <header >
            <div class="search">
                <a :href="'#/brasearchshow'+value"><img  src="../../assets/images/header/search.png" alt=""></a>
                <input type="text" placeholder="搜索品牌" class="inp" id="inp" v-model="value">
            </div>
            <div class="back" @click="go_back"></div>
        </header>

    </div>
</template>

<script>
    export default {
        name: "brand_search",
        data(){
            return{
                value:null
            }
        },
        methods:{
            go_back(){
                this.$router.go(-1)
            },
        }
    }
</script>

<style scoped>
    header{
        width: 100%;
        height: 0.5rem;
        background-color: white;
        position: fixed;
        top: 0;
        /*line-height: 0.4rem;*/
    }
    .search{
        width: 80%;
        height: 0.3rem;
        margin: 0.1rem auto 0;
        border: 0.01rem solid #dcdcdc;
        display: flex;
        /*margin-top: 0.1rem;*/
    }
    .search img{
        width: 0.3rem;
        height: 0.3rem;
    }
    .inp{
        width: 100%;
        height: 0.3rem;
        border: none;
        border-left: 0.01rem solid #dcdcdc;
        display: block;
    }
    .search:before{
        content: "";
        width: 0.1rem;
        height: 0.1rem;
        border: 0.02rem solid #cccccc;
        transform: rotate(45deg);
        position: absolute;
        left: 0.13rem;
        top: 0.18rem;
        border-right: none;
        border-top: none;
    }
    .back{
        width: 0.3rem;
        height: 0.3rem;
        position: absolute;
        top: 0.1rem;
    }



    .founder{
        overflow: hidden;
        width: 100%;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
    /*头部中间的品牌名称*/
    .name{
        width: 50%;
        text-align: center;
        font-size: 0.2rem;
    }

    .name p{
        width: 65%;
        margin: 0 auto;
    }
    /*品牌头部  品牌信息*/
    .brand_inif{
        display: flex;
        width: 100%;
    }
    .shop_pic{
        width: 40%;
    }
    .shop_pic img{
        width: 100%;
        margin: 0 auto;
        margin-top: 0.05rem;
    }
    /*er*/
    .message{
        width: 40%;
        font-size: 0.12rem;

    }
    .inif{
        margin-left: 0.05rem;
    }
    .brand_name{
        font-size: 0.2rem;
    }
    .message p{
        height: 0.25rem;
        line-height: 0.25rem;
    }
    /*三*/
    .relevant{
        text-align: right;
        width: 20%;

    }
    .follow{
        border: 1px solid #F56D02;
        border-radius: 0.07rem;
        text-align: center;
        width: 0.6rem;
        font-size: 0.13rem;
        height: 0.2rem;
        line-height: 0.2rem;
        margin-top:0.05rem ;
    }
    .brand_story{
        color: #F56D02;
        margin: 0.4rem 0.14rem 0 0;
        position: relative;
    }
    .brand_story:after{
        content: "";
        position: absolute;
        right: -0.17rem;
        top:0.03rem;
        width: 0;
        height: 0;
        border: 0.07rem solid transparent;
        border-left: 0.07rem solid #F56D02!important;

    }

</style>