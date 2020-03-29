<template>
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
  import axios from 'axios';
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
    mounted(){
      axios({
        url:'/api/goods/column',
        params:{_page:1,_limit:6},
        // headers:{
        //   token:'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6Imx4dyIsIl9pZCI6IjVlNjYxZGQxOTk5NGM2MzI1Y2MzZjNjNCIsImlhdCI6MTU4MzgzOTIyNiwiZXhwIjoxNTgzOTI1NjI2fQ.MCwYSlJMDvuX0ewee5R-e12Ty5GIymGeJzRisj9mQ4I'
        // }
      }).then(
        res=>this.column = res.data.data
      )
    },
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
