<template>
 <div class="Follow">
   <Cell :data="{_id:1,title:'alex1',des:'ooo1'}" apiName="follow"/>
   <Cell :data="{_id:1,title:'alex1',des:'ooo1'}" apiName="follow"/>
   <Cell :data="{_id:1,title:'alex1',des:'ooo1'}" apiName="follow"/>
 </div>
</template>

<script>
	import Cell from '../components/Cell.vue'
	
  export default {
    name:'Follow',
    props:{},
    data(){
      return {
        
      }
    },
    components:{
		Cell
	},
    mounted(){},
    updated(){},
    methods:{}
  }
</script>

<style scoped>
  .Follow{
    margin-top: .6rem;
    margin-left: 0.4rem;
    margin-right: 0.4rem;
  }
</style>
