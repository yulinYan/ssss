<template>
    <home-banner  :banner='swiperInfo' v-if="swiperInfo"></home-banner>
</template>

<script>
    import homeBanner from '../../components/home/home_banner'
    export default {
        name: "home",
        components:{
            homeBanner
        },
        data (){
            return {
                swiperInfo : [],
            }
        },
        methods:{
            _initSwiperInfo(){
                fetch('http://119.3.133.207:5000/home/banner').then(res=>{
                    // console.log(res)
                    res.json().then(data => {
                        console.log(data)
                        this.swiperInfo = data;
                        // console.log(this.orderInfo)
                    })
                })
            }
        },
        created() {
            this._initSwiperInfo();
            // console.log(this.$route)
            // let a=this.$route.split("?")[1]
            // console.log(a)
        },
    }
</script>

<style scoped>

</style>