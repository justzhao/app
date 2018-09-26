<template>
    <div>
        {{goodsMsg}}
    </div>
</template>
<script>
/* eslint-disable */
export default {
  name: 'vgoods',
  data(){
      return {
          goodsMsg:{}
      }
  },
  created(){
      this.$http.get('api/goodsInfo').then((response)=>{
        response=response.body;
        console.log(response);
        this.goodsMsg=response.msg;
      })
  }
}

</script>

<style>

</style>
