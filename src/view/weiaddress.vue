<template>
    <div style="margin-top: -0.5rem">
        <van-nav-bar
                left-text="确认订单"
                left-arrow
                @click-left="onClickLeft"

        />
        <van-address-list
                v-model="chosenAddressId"
                :list="list"
                :add-button-text="addtext"
                @add="onAdd"
                @edit="onEdit"
        />
        <van-card
                :num="goods.num"
                :tag="goods.weibuy"
                :price="goods.price"
                :desc="goods.titlet"
                :title="goods.title"
                :thumb="goods.thumb"
                origin-price="10.00"
        />
        <p>留言备注：</p>
        <p style="text-align: center"><textarea rows="5" cols="50%" placeholder="可在此备注您需要的颜色尺码，颜色及其他需求，如不清楚可先联系商家咨询，避免误填"/></p>
        <div style="width:99%;height: 2.45rem;border: 0.005rem solid #ccc">
        <p class="weiyun" ><span>运费</span><span style="float: right">到付</span></p>
        <p class="weiyun" ><span>应付款</span><span style="float: right">￥{{goods.num*goods.price}}</span></p>
        <p class="weiyun" style="height: 0.4rem;line-height: 0.4rem;font-size: 0.16rem;border-bottom: 0.01rem solid black"><span>支付方式：</span></p>
        <p class="weiphotoyun" style="border-bottom: 0.01rem solid black"><span style="height:0.3rem;line-height: 0.3rem;"><img src="../../public/assets/weiimg/iconfont_zhifubao.png" style="height: 0.3rem;width: 0.4rem;margin-left: 0.1rem;float: left;margin-top: 0.04rem;"></span><span class="weiapply" >支付宝支付</span><span float="right"><input type="checkbox"  class="weiinput"></span></p>
<!--        <p class="weiyun"><span>支付方式</span><span style="float: right">微信支付</span></p>-->
        <p class="weiphotoyun" style="border-bottom: 0.01rem solid black"><span style="height:0.3rem;line-height: 0.3rem;"><img src="../../public/assets/weiimg/iconfont_weixin.png" style="height: 0.3rem;width: 0.4rem;margin-left: 0.1rem;float: left;margin-top: 0.04rem;"></span><span class="weiapply">微信支付</span><span float="right"><input type="checkbox"  class="weiinput"></span></p>
<!--        <p class="weiyun"><span>支付方式</span><span style="float: right">微博支付</span></p>-->
        <p class="weiphotoyun" style="border-bottom: 0.01rem solid black"><span style="height:0.3rem;line-height: 0.3rem;"><img src="../../public/assets/weiimg/iconfont_weibo.png" style="height: 0.3rem;width: 0.4rem;margin-left: 0.1rem;float: left;margin-top: 0.04rem;"></span><span class="weiapply">微博支付</span><span float="right"><input type="checkbox"  class="weiinput"></span></p>
            <p class="weiphotoyun" style="text-align: center"><input type="checkbox" style="width: 0.2rem;height: 0.2rem">我已阅读并同意全求购商品</p>
        </div>
    </div>

</template>

<script>
    import { AddressList,NavBar,Card  } from 'vant';
    export default {
        name: "weiaddress",
        components:{
            [AddressList.name]:AddressList,
            [NavBar.name]:NavBar,
            [Card.name]:Card
        },
        data() {
            return {
                weidATA:[],
                addtext:'提交订单',
                chosenAddressId: '1',
                list: [
                    {
                        id: '1',
                        name: '魏杰',
                        tel: '15771677386',
                        address: '陕西理工大学'
                    },
                    ],
                goods: {
                    "weibuy":'未付款',
                    "id": '1',
                    "title": 'VALENTINO',
                    "titlet":"Rose同款 黑色徽标针织套衫",
                    "good_type":"现货",
                    "desc": '约250g，2根',
                    "price": 6330,
                    "color":"红色",
                    "num": 6,
                    "thumb": 'https://img.ofashion.com.cn/public/goods/sale_quote/20191109/861342/41445dc5bb7e22b6d/5949324783666610_60585327.jpg?x-oss-process=image/resize,w_750/format,webp',
                }
            }
        },

        methods: {
            onAdd() {
                // eslint-disable-next-line no-undef
                // this.Toast('提交');

                fetch("http://10.35.167.96:5000/order/alipay/",{
                    method:"POST",
                    headers:{
                        "Content-Type": "application/json"
                    },
                    body:JSON.stringify({"token": "ZGVjNjNiMTk4MjllNDRjOGFhODhjYmIwNTMxOWM0OTg=","order_id":15}),
                }).then(res=>{
                    //res stream promise
                    res.json().then(data=>{
                        console.log(data)
                        console.log("9999")
                        window.location.replace(data)
                    })
                })
            },
            onClickLeft(){
                this.$router.go("-1")
            },


            // async _PageData() {
            //     let num=this.$route.weidATA.id;
            //     // let order = this.search_type
            //     let res = await fetch('http://119.3.133.207:5000/goods/get_goods_dtails?good_id='+num)
            //     // 119.3.133.207
            //     // 10.36.172.136
            //     let data = await res.json()
            //     this.weidATA.push(data.data.now_good);
            //     // this.info
            //     // this.infot=data.data.other_good;
            // },

            onEdit(item, index) {
                // eslint-disable-next-line no-undef
                Toast('编辑地址:' + index);
            }
        },

    }
</script>

<style scoped>
    .van-address-list{
        height: 0.88rem;
    }
    button .span{
        display: none;
    }
    .weiinput{
        width: 0.3rem;
        height: 0.3rem;
        content:"\2714";
        -webkit-appearance: radio;
        float: right;
        margin-top: 0.04rem;
    }
    .weiapply{
        float: left;
        margin-left: 0.2rem;
        font-size: 0.16rem;
        color:#898989
    }
    .weiyun{
        width: 100%;
        height: 0.25rem;
        background-color: white;
        line-height: 0.25rem
    }
    .weiphotoyun{
        width: 100%;
        height:0.4rem;
        line-height: 0.4rem;
        background-color: white;
    }

</style>
