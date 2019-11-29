<template>
    <div class="f-allorder-con">
        <div class="f-noorder" v-if="AllorderInfo.order == 0">
            <img src="assets/images/mine/search_result_none.png"/>
            <p>您还没有订单</p>
            <p>可以去逛逛有没有想买的</p>
        </div>
        <div v-else class="f-allorder-info">
            订单信息
        </div>
        <f-loading></f-loading>
    </div>
</template>

<script>
    import loading from "./loading";
    export default {
        name: "allorder",
        data(){
            return {
                AllorderInfo:"",
                number:0,
                flag:true,
            }
        },
        components:{
          "f-loading":loading
        },
        methods:{
            _initAllOrderInfo(){
                fetch('http://localhost:3000/order').then(res=>{
                    // console.log(res)
                    res.json().then(data => {
                        // console.log(data)
                        this.AllorderInfo = data;
                        // console.log(this.AllorderInfo)
                    })
                })
            },

        },
        created() {
            this._initAllOrderInfo();
        },
    }
</script>

<style scoped>
    /*无订单状态*/
    .f-noorder{
        width:100%;
        height:2.8rem;
        text-align: center;
        padding-top:1.33rem;
        box-sizing: border-box;
        background-color: #eaeaea;
        color:#999999;
        margin-bottom: 0.1rem;
    }
    .f-noorder img{
        width:0.3rem;
        height:0.3rem;
        margin-bottom: 0.55rem;
    }

</style>