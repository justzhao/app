<template>
  <div>
       <v-scroll></v-scroll>
       <v-header></v-header>
      <div class="tab">
        <div class="tab-item">
           <router-link to="/goods">商品</router-link>
        </div>
         <div class="tab-item">商家
        </div>
         <div class="tab-item">
               评论
        </div>
      </div>
      <div class="content">
       我是app
      </div>
        <router-view></router-view>
  </div>
</template>

<script>
/* eslint-disable */
import header from '@/components/header'
import scroll from '@/components/scroll/scroll'
export default {
  name: 'App',
  components: {
    'v-header': header,
    'v-scroll': scroll
  }
}
</script>

<style>
.tab{
  display: flex;
  width: 100%;
  height: 40px;
  line-height: 40px;
}
.tab-item{
  flex:2;
  text-align: center;
}
a{
  display: inline-table;
  width: 100%;
  height: 100%;
}
</style>
