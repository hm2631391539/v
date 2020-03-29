<template>
 <!-- 栏目 -->
<!-- <div class="Column">
   <Cell :data="{_id:1,title:'alex1',des:'ooo1'}" apiName="column"/>
   <Cell :data="{_id:1,title:'alex1',des:'ooo1'}" apiName="column"/>
   <Cell :data="{_id:1,title:'alex1',des:'ooo1'}" apiName="column"/>
  </div> -->
   <div class="Column">
	   <Cell
			v-for="item of column"
			:key="item._id"
			:data="item"
			api-name="column"
	   />
   </div>
</template>

<script>
	import Cell from '../components/Cell'
	
  export default {
    name:'Column',
    props:{},
    data(){
      return {
        column:[]
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
  .Column{
    margin-top: .6rem;
    margin-left: 0.4rem;
    margin-right: 0.4rem;
  }
</style>
