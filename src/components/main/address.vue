<template>
    <div class="f-user-address">
        <header class="f-user-address-header">
            <div class="f-user-address-goback" @click="toback"><img src="../../../public/assets/images/mine/mm_title_back.png"/></div>
            <div class="f-user-address-title">地址列表</div>
        </header>
        <van-address-list
                v-model="chosenAddressId"
                :list="list"
                @add="onAdd"
                @edit="onEdit"
        ></van-address-list>
    </div>

</template>

<script>
    import { AddressList ,Toast} from 'vant';
    export default {
        name: "faddress",
        data() {
            return {
                chosenAddressId: '1',
                list: [
                    {
                        id: '0',
                        name: 'lemon',
                        tel: '18578210000',
                        address: '陝西省西安市雁塔区科技四路'
                    },
                    {
                        id: '1',
                        name: 'somnr',
                        tel: '18578210000',
                        address: '陝西省西安市雁塔区科技四路'
                    }
                ]
            }
        },
        components:{
          [AddressList.name]:AddressList,
        },
        methods: {
            onAdd() {
                this.$router.push('/addressedit')
            },
            onEdit(item, index) {
                Toast('编辑地址:' + index);
            },
            toback(){
                this.$router.go(-1);
            },
        }
    }
</script>

<style scoped>
    .f-user-address-header{
        width:100%;
        height:0.5rem;
        line-height:0.5rem;
        display: flex;
        justify-content: space-around;
        text-align: center;
        position: fixed;
        top:0;
        z-index:1;
        background-color: #FBF8FC;
        border-bottom: 1px solid #DDDDDD;
        margin-bottom: 0.2rem;
    }
    .f-user-address-title{
        width:100%;
        font-size: 0.18rem;
    }
    .f-user-address-goback{
        height:0.5rem;
        position: absolute;
        left: 0;
        width:20%;
        display: flex;
        align-items: center;
    }
    .f-user-address-goback img{
        width:0.28rem;
        height:0.28rem;
        margin-left: 0.1rem;
    }
</style>