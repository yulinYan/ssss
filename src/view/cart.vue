<template>
    <div style="margin-top: -0.5rem">
        <van-nav-bar
                title="购物车"
                left-text="返回"
                left-arrow
                @click-left="onClickLeft"
        />
        <div class="edit">
            <div class="edit_clear">闪电清理</div>
            <div class="edit_r">
                <span class="move_collection">移入收藏夹</span>
                <span class="del">删除</span>
            </div>
        </div>
<!--        为空显示-->
        <div class="free" >
            <router-link to="/main/home">
                <span class="free-s">购物车还是空的</span>
                <span class="go_see">去逛逛</span>
            </router-link>
        </div>

<!--        购物车-->
        <div class="y_cart">
            <div class="y_shop">
<!--                店铺头部-->
                <div class="y_shop_title">
                    <div class="y_title">
                        <div class="one">
                            <input type="checkbox" @click="checkde">
                            <div v-show="flag" class="mask_inp"></div>
                        </div>
                        <div class="two">
                            <img src="../assets/images/cart1.png" alt="">
                            <div class="y_title_name">旗舰店</div>
                        </div>
                        <div class="three">领劵</div>
                    </div>
                </div>
<!--                商品-->
                <div class="y_goods">
                    <!--                        商品-->
                    <div class="y_goods_box">
                        <div class="p_one">
                            <input type="checkbox" @click="checkde">
                            <div v-show="flag" class="p_mask_inp"></div>
                        </div>
                        <div class="p_two">
                            <img src="../assets/images/cart1.png" alt="">
                        </div>
                        <div class="p_three">
                            <div class="descAdv">衣柜香薰包去异味芳香持久香包衣橱衣物固体清香熏蜡片香味神器</div>
                            <div class="taste">茉莉（醇厚鲜浓）</div>
                            <div class="p_three_bottom">
                                <div class="y_pri">￥<span>1.99</span></div>
<!--                                计算那块-->
                                <div class="add">
                                        <span class="y_add">-</span><span class="y_num">1</span><span class="y_min">+</span>

                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- 脚部-----------------------脚部-------------------------->

                    <!-- 脚部-----------------------脚部-------------------------->
                </div>
            </div>
        </div>
<!--        猜你喜欢-->
		<div class="your_love">
            <div class="your_love_title">
                <img src="../assets/images/cart/cart2.jpg" alt="">
            </div>
            <div class="love_product_boss">
                <a :href="'#/detail'+n.pid" class="love_product" :key="index" v-for="(n,index) in list" >
                    <div class="img">
                        <img :src="n.pic" alt="">
                    </div>
                    <div class="messiage">
                        <p class="desc">{{n.desc}}</p>
                        <p class="price">￥<span>{{n.price}}</span></p>
                    </div>
                </a>
            </div>
        </div>
    </div>
</template>

<script>
    import { mapGetters } from 'vuex';
    import { Checkbox, CheckboxGroup, Card, SubmitBar, Toast ,NavBar,Button} from 'vant';
    export default {
        name: "cart",
        components: {
            [Card.name]: Card,
            [Button.name]:Button,
            [NavBar.name]: NavBar,
            [Checkbox.name]: Checkbox,
            [SubmitBar.name]: SubmitBar,
            [CheckboxGroup.name]: CheckboxGroup
        },
        computed: {
            ...mapGetters({
                cartInfo: 'GETCART'
            }),
            submitBarText() {
                const count = this.checkedGoods.length;
                return '结算' + (count ? `(${count})` : '');
            },
            totalPrice() {
                // eslint-disable-next-line no-undef
                return this.weidATA.reduce((total, item) => total + (this.checkedGoods.indexOf(item.id) !== -1 ? item.price*item.audit*100 : 0), 0);
            },
        },
        data() {
            return {
                weidATA:[],
                checkedGoods: ['1', '2', '3'],
				list:[
                    {"pid":"001",
                        "pic":"assets/images/cart/cart5.webp",
                        "desc":"RedMi K20 Pro 尊享版 K20 Pro",
                        "price":"1669",
                        "detail_1":"「立即预约中，11月11日6GB+128GB闪降200元，到手价仅需1399元」",
                        "detail_2":"6400万旗舰级全场景四摄 / 前置2000万 AI美颜相机 / G90T专业游戏芯片，\n" +
                            "                    液冷散热 / 6.53英寸水滴全面屏 / 4500mAh大电量 / 标配18W快充 / 康宁\n" +
                            "                    大猩猩保护玻璃 / 多功能NFC / 红外遥控功能 / Game Turbo2.0游戏加速"
                    },{
                        "pid":"002",
                        "pic":"assets/images/cart/cart6.webp",
                        "desc":"RedMi K20 Pro 尊享版 K20 Pro",
                        "price":"2669",
                        "detail_1":"「立即预约中，11月11日6GB+128GB闪降200元，到手价仅需1399元」",
                        "detail_2":"6400万旗舰级全场景四摄 / 前置2000万 AI美颜相机 / G90T专业游戏芯片，\n" +
                            "                    液冷散热 / 6.53英寸水滴全面屏 / 4500mAh大电量 / 标配18W快充 / 康宁\n" +
                            "                    大猩猩保护玻璃 / 多功能NFC / 红外遥控功能 / Game Turbo2.0游戏加速"
                    },
                    {
                        "pid":"003",
                        "pic":"assets/images/cart/cart3.webp",
                        "desc":"RedMi K20 Pro 尊享版 K20 Pro",
                        "price":"3669",
                        "detail_1":"「立即预约中，11月11日6GB+128GB闪降200元，到手价仅需1399元」",
                        "detail_2":"6400万旗舰级全场景四摄 / 前置2000万 AI美颜相机 / G90T专业游戏芯片，\n" +
                            "                    液冷散热 / 6.53英寸水滴全面屏 / 4500mAh大电量 / 标配18W快充 / 康宁\n" +
                            "                    大猩猩保护玻璃 / 多功能NFC / 红外遥控功能 / Game Turbo2.0游戏加速"
                    },
                    {
                        "pid":"004",
                        "pic":"assets/images/cart/cart4.webp",
                        "desc":"RedMi K20 Pro 尊享版 K20 Pro",
                        "price":"4669",
                        "detail_1":"「立即预约中，11月11日6GB+128GB闪降200元，到手价仅需1399元」",
                        "detail_2":"6400万旗舰级全场景四摄 / 前置2000万 AI美颜相机 / G90T专业游戏芯片，\n" +
                            "                    液冷散热 / 6.53英寸水滴全面屏 / 4500mAh大电量 / 标配18W快充 / 康宁\n" +
                            "                    大猩猩保护玻璃 / 多功能NFC / 红外遥控功能 / Game Turbo2.0游戏加速"
                    },
                    {
                        "pid":"005",
                        "pic":"assets/images/cart/cart5.webp",
                        "desc":"RedMi K20 Pro 尊享版 K20 Pro",
                        "price":"5669",
                        "detail_1":"「立即预约中，11月11日6GB+128GB闪降200元，到手价仅需1399元」",
                        "detail_2":"6400万旗舰级全场景四摄 / 前置2000万 AI美颜相机 / G90T专业游戏芯片，\n" +
                            "                    液冷散热 / 6.53英寸水滴全面屏 / 4500mAh大电量 / 标配18W快充 / 康宁\n" +
                            "                    大猩猩保护玻璃 / 多功能NFC / 红外遥控功能 / Game Turbo2.0游戏加速"
                    },
                    {
                        "pid":"006",
                        "pic":"assets/images/cart/cart6.webp",
                        "desc":"RedMi K20 Pro 尊享版 K20 Pro",
                        "price":"6669",
                        "detail_1":"「立即预约中，11月11日6GB+128GB闪降200元，到手价仅需1399元」",
                        "detail_2":"6400万旗舰级全场景四摄 / 前置2000万 AI美颜相机 / G90T专业游戏芯片，\n" +
                            "                    液冷散热 / 6.53英寸水滴全面屏 / 4500mAh大电量 / 标配18W快充 / 康宁\n" +
                            "                    大猩猩保护玻璃 / 多功能NFC / 红外遥控功能 / Game Turbo2.0游戏加速"
                    }
                ],
                flag:false,
                // goods: [{
                //     id: '1',
                //     title: '进口香蕉',
                //     desc: '约250g，2根',
                //     price: 200,
                //     color:"红色",
                //     num: 0,
                //     thumb: 'https://img.yzcdn.cn/public_files/2017/10/24/2f9a36046449dafb8608e99990b3c205.jpeg'
                // }, {
                //     id: '2',
                //     title: 'VALENTINO',
                //     desc: 'Rose同款 黑色徽标针织套衫',
                //     price: 6330,
                //     color:"黄色",
                //     num: 0,
                //     thumb: 'https://img.ofashion.com.cn/public/goods/sale_quote/20191109/861342/41445dc5bb7e22b6d/5949324783666610_60585327.jpg?x-oss-process=image/resize,w_750/format,webp'
                //
                // }, {
                //     id: '3',
                //     title: '美国伽力果',
                //     desc: '约680g/3个',
                //     price: 2680,
                //     color:"黑色",
                //     num: 0,
                //     thumb: 'https://img.yzcdn.cn/public_files/2017/10/24/320454216bbe9e25c7651e1fa51b31fd.jpeg'
                // }]
            };
        },
        methods: {
            formatPrice(price) {
                return (price / 100).toFixed(2)*100;
            },
            onSubmit() {
                this.$router.replace("/weiaddress")
            },
            onClickLeft() {
                this.$router.go(-1)
            },
            onClickRight() {
                Toast('按钮');
            },
            // eslint-disable-next-line no-unused-vars
            add(i){
                // console.log(i)
                // console.log(this.weidATA[i].num)
                this.weidATA[i].audit++
            },
            // 渲染初始化页面
            // async weiforeach() {
            //
            //         let res = await fetch('http://119.3.133.207:5000/goods/get_goods_dtails?good_id='+item)
            //         // 119.3.133.207
            //         // 10.36.172.136
            //         let data = await res.json()
            //         this.weidATA.push(data.data.now_good);
            //
            // },
checkde(){
 let arr = document.getElementsByTagName("input")
 arr.forEach((oinput)=>{
     if(oinput.checked=="checked"){
            this.flag=true;
     }
 })
}
        },
        beforeMount() {
            // this.weiforeach()

        }
    }
</script>

<style lang="less">
    .edit{
        /*width: 100%;*/
        background-color: white;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 0.2rem;
        font-size: 0.14rem;
        height: 0.4rem;
    }
    .van-nav-bar{
        background-color: #D75C76;

    }
    
    .van-nav-bar__title{
        color: white;
    }
    .van-nav-bar .van-icon{
        color: white;
    }
    .van-nav-bar__text{
     color: white;
    }
    .card-goods {
        padding: 10px 0;

        &__item {
            position: relative;
            background-color: #fafafa;
            .van-checkbox__label {
                width: 100%;
                height: auto; // temp
                padding: 0 10px 0 15px;
                box-sizing: border-box;
            }
            .van-checkbox__icon {
                top: 50%;
                left: 10px;
                z-index: 1;
                position: absolute;
                margin-top: -10px;
            }
            .van-card__price {
                color: #f44;
            }
        }
    }
	/*猜你喜欢*/
    .your_love{
        margin-top: 4rem;
    }
	.your_love img{
        width: 100%;
        height: 0.625rem;
    }
    .img img{
        display: block;
        width: 1.85rem;
        height: 1.85rem;
        margin: 0;
        padding: 0;
    }
    .messiage{
        width: 1.85rem;
        /*height: ;*/
        /*padding: 0.09rem 0 0.13rem 0.11rem ;*/

    }
    .desc{
        width: 1.65rem;
        color: #3c3c3c;
        font-size: 0.14rem;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        padding-left: 0.1rem;
    }
    .price{
        font-size: 0.16rem;
        color: #ff6700;
        text-align: left;
        padding-left: 0.1rem;
    }
    .love_product_boss{
        display: flex;
        justify-content: space-between;
        flex-wrap:wrap ;
    }
    /*vant样式*/
    .card-goods {
        padding: 10px 0;
        background-color: #fff;
        &__item {
            position: relative;
            background-color: #fafafa;
            .van-checkbox__label {
                width: 100%;
                height: auto; // temp
                padding: 0 10px 0 15px;
                box-sizing: border-box;
            }
            .van-checkbox__icon {
                top: 50%;
                left: 10px;
                z-index: 1;
                position: absolute;
                margin-top: -10px;
            }
            .van-card__price {
                color: #f44;
            }
        }
    }
/*空显示*/
    .free{
        width: 100%;
        height: 0.62rem;
        background-color: #EBEBEB;
        padding: 0.1rem;
        line-height: 0.62rem;
    }
    .free-s{
        display: inline-block;
        padding: 0 0.08rem 0 0.6rem;
        font-size: 0.13rem;
        color: rgba(0,0,0,0.27);
        background-image: url("../assets/images/cart1.png");
        background-repeat: no-repeat;
        background-size: auto 100%;
    }
    .go_see{
        display: inline-block;
        border: 0.01rem solid #999;
        height: 0.2rem;
        line-height: 0.2rem;
        padding: 0 0.1rem;
        border-radius: 0.03rem;

    }

    /*购物车样式*/
    input{
        -webkit-appearance: radio;
        width: 0.17rem;
        height: 0.17rem;
        background: white;
        outline: none;
    }
    .mack_inp{

    }
    .mask_inp::before{
        display: block;
        content: "\2714";
        text-align: center;
        font-size: 16px;
        width: 0.16rem;
        height: 0.16rem;
        line-height: 0.17rem;
        border-radius: 50%;
        color: white;
        position: absolute;
        background-color: #ED7543;
        top: 0.084rem;
        left: 0.115rem;
    }
    .y_cart{
        width: 100%;

    }
    .y_shop{
        width: 95%;
        border-radius: 0.05rem;
        background-color: white;
        margin: 0 auto;
    }
    .y_shop_title{
        width: 100%;
        padding-top: 0.1rem;
    }
    .y_title{
        display: flex;
        align-items: center;
        justify-content: left;
        height: 0.35rem;
    }
    .one{
        width: 0.5rem;
        text-align: center;
        position: relative;
        /*background-color: #EE7F35;*/
        height: 0.35rem;
        display: flex;
        align-items: center;
        justify-content: center;

    }
    .two{
        width: 100%;
        display: flex;
        align-items: center;
        font-size: 0.12rem;
    }
    .two img{
        width: 0.25rem;
        height: 0.25rem;
        margin-right: 0.1rem;

    }
    .y_title_name{
    }
    .three{
        width: 0.5rem;
        font-size: 0.12rem;
    }
.y_goods{
    width: 100%;
}
    .y_goods_box{
        display: flex;
        justify-content: left;
        align-items: center;
        padding-bottom: 0.1rem;
        width: 100%;
        border: none;
        padding-top: 0.1rem;
    }
    .p_one{
        width: 0.4rem;
        text-align: center;
        position: relative;
    }
    .p_two{
        width: 0.7rem;
        height: 0.7rem;

    }
    .p_two img{
        width: 100%;

    }
    .p_three{
        width: 2.3rem;
        /*background-color: #EE7F35;*/
        font-size: 0.11rem;
        margin-left: 0.12rem;
    }
    .descAdv{
        font-size: 0.12rem;
        line-height: 0.16rem;
        width: 2rem;
        /*background-color: blueviolet;*/
        /*margin: 0 auto;*/
        height: 0.35rem;
        overflow: hidden;
        margin-top: 0.05rem;
        letter-spacing: 0.01rem!important;
    }
.p_three_bottom{
    display: flex;
    justify-content: space-between;
    width: 100%;
}
    .y_pri{
        color: #ED7543;
        font-size: 0.13rem;
    }
    .taste{
        color: #BBBBBB;
    }
    .add{
        margin-right: 0.1rem;
        color: #BBBBBB;
        height: 0.17rem;

    }
    .y_add{
        width: 0.18rem;
        height: 100%;
        text-align: center;
        display: inline-block;
        border: 0.01rem solid #EFEFEF;
        line-height: 0.17rem;
        border-radius: 0.04rem 0 0 0.04rem;
    }
    .y_num{
        width: 0.28rem;
        height: 100%;
        text-align: center;
        display: inline-block;
        line-height: 0.17rem;
        border: 0.01rem solid #EFEFEF;
        border-left: none;
        border-right: none;
    }
    .y_min{
        width: 0.18rem;
        height: 100%;
        text-align: center;
        display: inline-block;
        line-height: 0.17rem;
        border: 0.01rem solid #EFEFEF;
        border-radius: 0 0.04rem 0.04rem 0;
    }
    .p_mask_inp::before{
        display: block;
        content: "\2714";
        text-align: center;
        font-size: 16px;
        width: 0.16rem;
        height: 0.16rem;
        line-height: 0.17rem;
        border-radius: 50%;
        color: white;
        position: absolute;
        background-color: #ED7543;
        top: 0rem;
        left: 0.115rem;
    }
</style>
