<template>
  <div class="Follow">
    <Cell
      v-for="(item,index) of follow"
      :key="item._id"
      :data="item"
      :index="index"
      api-name="follow"
    />
  </div>
</template>

<script>
  import Cell from '../components/Cell.vue'
  import axios from 'axios';
  export default {
    name:'Follow',
    props:{},
    data(){
      return {
        follow:[]
      }
    },
    components:{
      Cell
    },
    mounted(){
      axios({
        url:'/api/goods/follow',
        params:{_page:1,_limit:4},
        // headers:{
        //   token:'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6Imx4dyIsIl9pZCI6IjVlNjYxZGQxOTk5NGM2MzI1Y2MzZjNjNCIsImlhdCI6MTU4MzgzOTIyNiwiZXhwIjoxNTgzOTI1NjI2fQ.MCwYSlJMDvuX0ewee5R-e12Ty5GIymGeJzRisj9mQ4I'
        // }
      }).then(
        res=>this.follow = res.data.data
      )
    },
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
