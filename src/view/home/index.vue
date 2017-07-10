<template>
  <div class="wrap box">
    <!-- <div class="box-flex"> -->
      <headerBar :color="'black'"></headerBar>
      <div class="content">
        <navList :navData="navData"></navList>
        <transition name="slide-fade">
          <router-view></router-view>
        </transition>
      </div>
    <!-- </div> -->
    <footerNav></footerNav>
  </div>
</template>

<script>
import headerBar from '@/components/headerbar'
import navList from '@/view/home/component/navlist'
import footerNav from '@/components/footerNav'

export default {
  name: 'homePage',
  components: {
    headerBar,
    navList,
    footerNav
  },
  data () {
    return {
      navData: ''
    }
  },
  created () {
    this.getData()
  },
  methods: {
    getData () {
      this.$http.jsonp('http://m.haimi.com/api/nav/list?platform=WAP',{
        Params:{
        },
         jsonp:'_callback'
      }).then(function(opt){
          this.navData = opt.data.data;
      })
      this.$http.jsonp('http://m.haimi.com/api/nav/list',{
        Params:{
          platform:'WAP'
        },
         jsonp:'_callback'
      }).then(function(opt){
        this.navData = opt.data.data
      })
      this.$http.jsonp('http://m.ibantang.com/getHomeTopicList?page=0&pagesize=40&type=topic_main&extend=""',{
        jsonp:'_callback'
      }).then(function(opt){
        console.log(opt)
      }).catch(function(err){
        console.log(err)
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
.box{
  position:absolute;
  top:0;
  left:0;
  right:0;
  bottom:0;
  display:flex;
  flex-direction:column;
}
.box-flex{
  flex:1;
  overflow-y:scroll;
}
.wrap{
  background:#F7F7F7;
}
.m-box{
  margin-top: .1rem;
  background:white;
}
.slide-fade-enter-active{
  transition: all .3s ease;
}
.slide-fade-leave-active{
  transition: all .3s cubic-bezier(1.0,0.5,0.8,1.0);
}
.slide-fade-enter,.slide-fade-leave-active{
  transform:translateX(-430px);
  /*opacity: 0;*/
}

/*好好说话，项目也做了不少，*/

</style>
