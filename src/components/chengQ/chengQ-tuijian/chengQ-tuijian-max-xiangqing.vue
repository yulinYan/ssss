<template>
    <div>
        <div class="max-xiangqing-header">
            <a href="#/main/chengQ"><span class="xiangqing-header-left">&lt;</span></a>
            <p>详情</p>
            <a href="#"><img src="../../../assets/images/chengQ/maijiaxiu/fenxiang.png" alt=""></a>
        </div>
        <div class="max-xiangqing-div">
            <img class="max-xiangqing-img" src="../../../assets/images/chengQ/tuijian/img1.png" alt="">
        </div>
        <div class="maijiaxiu-user">
            <img src="../../../assets/images/chengQ/maijiaxiu/tuijainuser.png" alt="">
            <span>jsycyoma</span>
            <button>关注</button>
        </div>
        <div class="max-xiangqing-neirong">
            <h2>无瑕的命定邂逅，都蕴含在卡地亚红色珠宝盒中的经典美钻光彩里！</h2>
            <p>钻石是最能够彰显情人间坚定永恒诺言的信物，装载着情意誓言的珠宝盒更是不能忽略，而卡地亚更是以世人咏叹传承的美钻、加上以精心打造的红色珠宝盒珍藏属于情人之间坚贞又幸福的爱情宣言，展现一眼便悸动心跳加速的魅力。</p>
            <img class="max-xiangqing-neirong-img" src="../../../assets/images/chengQ/tuijian/img2.png" alt="">
            <p>卡地亚在拥有的众多经典美钻系列中，Destinée系列是M编最为钟爱的。为爱的火花打造出来自天堂的戒指，传递瞬间邂逅那一见钟情命运交会的代表，一抹星辰为未来烙上长相厮守的印记，充满浪漫诗意的由来。</p>
            <img class="max-xiangqing-neirong-img" src="../../../assets/images/chengQ/tuijian/img3.jpg" alt="">
            <p>Destinée钻石系列有着精巧微型铺镶工艺，将大小各异的美钻经由精细切割营造出有如反光镜面班的璀璨光芒。其中又以Destinée订婚钻戒轻盈的镶座构造精巧，加上并排爪镶设计而更显美妙，使得钻石更加光彩夺目，熠熠星光般的晶灿让人赞叹不已，完全无法将眼光移开。</p>
            <img class="max-xiangqing-neirong-img1" src="../../../assets/images/chengQ/tuijian/img4.png" alt="">
            <img class="max-xiangqing-neirong-img1" src="../../../assets/images/chengQ/tuijian/img5.png" alt="">
            <p>Destinée铂金与钻石戒指</p>
            <img class="max-xiangqing-neirong-img1" src="../../../assets/images/chengQ/tuijian/img6.png" alt="">
            <img class="max-xiangqing-neirong-img1" src="../../../assets/images/chengQ/tuijian/img6.png" alt="">
            <p>Destinée白K金与钻石镶嵌耳环</p>
            <img class="max-xiangqing-neirong-img" src="../../../assets/images/chengQ/tuijian/img7.png" alt="">
            <p>而以一抹无可忽视的红，深受到欧洲皇室与各界名人宠爱的卡地亚红色珠宝盒，是最能收藏装载着属于情人间最坚贞又幸福的爱的誓言，以及珍贵独一无二的卡地亚美钻。红色皮革以金色滚边，镶铸精巧的按扣，盒内纯白的衬垫及礼盒斜角造型，根据不同品项的珠宝钻饰都有所属的珠宝盒，藏在盒中的华美珠宝除了是众人心中的梦幻逸品之外，更是一份令人咏叹的不朽浪漫爱情宣言。</p>
            <img class="max-xiangqing-img2" src="../../../assets/images/chengQ/tuijian/img1.png" alt="">
        </div>
        <div class="max-xiangqing-pinglun">
            <p>最新评论<span>0</span></p>
            <h3></h3>
        </div>
        <div class="max-xiangqing-bottom">
            <input type="text" placeholder="请输入评论...">
            <button>发送</button>
            <img class="max-xiangqing-bottom-img1" src="../../../assets/images/chengQ/tuijian/xihuan.png" alt="">
            <img class="max-xiangqing-bottom-img2" src="../../../assets/images/chengQ/tuijian/dianzan2.png" alt="">
        </div>
    </div>
</template>

<script>
    export default {
        name: "chengQ-tuijian-max-xiangqing",
        data () {
            return{
                //头部
                maxxiangqingheader:[
                    {
                        img:"assets/images/chengQ/maijiaxiu/fenxiang.png"
                    },
                ],
                //大图片
                maxxiangqingdiv:[
                    {
                        img:"assets/images/chengQ/tuijian/img1.png"
                    },
                ],
                //用户信息
                maijiaxiuuser:[
                    {

                    },
                ],
                //推荐详情
                maxxiangqingneirong:[
                    {

                    },
                ],
                //评论
                maxxiangqingpinglun:[
                    {

                    },
                ],
                //底部
                maxxiangqingbottom:[
                    {

                    },
                ]
            }
        }
    }
</script>

<style scoped>
    .max-xiangqing-header{
        width: 100%;
        position: fixed;
        top: 0;
        padding: 0.1rem 0;
        background-color: white;
    }
    .max-xiangqing-header span{
        padding-left: 0.1rem;
        font-size: 0.2rem;
    }
    .max-xiangqing-header p{
        display: inline-block;
        margin-left: 1.5rem;
        font-size: 0.2rem;
    }
    .max-xiangqing-header img{
        float: right;
        padding-right: 0.1rem;
    }
    .max-xiangqing-img{
        width: 100%;
        display: block;
    }
    .maijiaxiu-user{
        text-align: left;
        margin: 0 auto;
        height: 0.5rem;
        position: relative;
        background-color: white;
    }
    .maijiaxiu-user img{
        width: 10%;
        border-radius: 50%;
        position: absolute;
        left: 0.1rem;
        top: 0.1rem;
    }
    .maijiaxiu-user span{
        font-size: 0.16rem;
        position: absolute;
        left: 0.5rem;
        top: 0.17rem;
    }
    .maijiaxiu-user button{
        font-size: 0.16rem;
        float: right;
        margin-right: 0.1rem;
        padding: 0.03rem 0.05rem;
        margin-top: 0.1rem;
        background-color: rgb(225 132 17);
        border-radius: 0.8rem;
    }
    .max-xiangqing-neirong{
        background-color: white;
    }
    .max-xiangqing-neirong h2{
        padding: 0.2rem 0.1rem;
        font-size: 0.2rem;
    }
    .max-xiangqing-neirong p{
        padding: 0 0.1rem;
        font-size: 0.16rem;
    }
    .max-xiangqing-neirong-img1{
        width: 50%;
        padding: 0.2rem 0;
    }
    .max-xiangqing-neirong-img{
        width: 60%;
        display: block;
        margin: 0 auto;
        padding: 0.2rem 0;
    }
    .max-xiangqing-img2{
        width: 100%;
        display: block;
        padding-top: 0.2rem;
    }
    .max-xiangqing-pinglun{
        padding-bottom: 0.5rem;
    }
/*最新评论*/
    .max-xiangqing-bottom{
        position: fixed;
        bottom: 0;
        width: 100%;
        background-color: white;
    }
    .max-xiangqing-bottom input{
        width: 60%;
        height: 0.25rem;
        margin: 0.1rem 0;
        border: 0;
        border-radius: 0.1rem;
        padding-left: 20px;
        background-color: rgb(235 235 235);
    }
    .max-xiangqing-bottom button{
        height: 0.25rem;
        margin: 0.1rem 0;
        border: 0;
        border-radius: 0.05rem;
        padding: 0 0.1rem;
        background-color: rgb(225 132 17);
        color: white;
        font-weight: 100;
    }
    .max-xiangqing-bottom-img1{
        position: absolute;
        top: 0.1rem;
        right: 0.4rem;
        height: 60%;
    }
    .max-xiangqing-bottom-img2{
        position: absolute;
        top: 0.1rem;
        right: 0.05rem;
        height: 60%;
    }
</style>