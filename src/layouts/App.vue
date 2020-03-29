<template>
  <div id="app">
	  <!--  $root 也可以是this.$root集中式管理-->
    <loading v-if="$root.bLoading"/>
    <Header v-if="$root.bNav"/>
	
	<!-- 动画transition -->
<!-- 	<transition
	  enter-active-class = "animated bounceInLeft"
	  leave-active-class = "animated bounceOutRight"
	> -->
	   <!-- 缓存组件keep-alive -->
	  <keep-alive>
	    <router-view ></router-view>
	  </keep-alive>
	<!-- </transition> -->
	
	
	
    <!-- <router-view></router-view> -->
    <Footer v-show="$root.bFoot"/>
  </div>
</template>

<script>
  
import Header from './Header.vue';
import Footer from './Footer.vue';
import loading from '../components/loading.vue';

export default {
  name: 'App',
  components: {
    Header,Footer,loading
  },
  watch:{  //监听页眉页脚需要在哪个页面显示
  	$route:{//路由监听，属性检测
      handler(nextValue,PrevValue){
        console.log('路由变化了',nextValue);
        
        let path = nextValue.path;
        
        if(/home|follow|column/.test(path)){//home follow column
          this.$root.bNav=this.$root.bFoot=true;
        }
        
        if(/detail|login|reg/.test(path)){//detial login reg
          this.$root.bNav=this.$root.bFoot=false;
        }
        
        if(path.includes('/user')){//user
          this.$root.bNav=false;
          this.$root.bFoot=true;
        }
        
      },
      immediate:true
    }
  }
}
</script>

<style>

</style>
