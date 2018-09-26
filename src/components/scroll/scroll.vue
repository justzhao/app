<template>
<div>
  我是轮播图哦
  <div class="scroll" v-if="items.length > 0">
    <transition-group name="list" tag="div">
     <div class="scroll-item" v-for="(item,index) in items" :key="index"  v-show="index===currentIndex" >
      <img v-bind:src="item">
    </div>
    </transition-group>
  </div>
  <p v-else>Sorry, no items found.</p>
</div>
</template>
<script>
/* eslint-disable */ 
var items=['./static/img/1.jpg','./static/img/2.jpg','./static/img/3.jpg']
export default {
  name: 'vscroll',
  data: function(){
      return{
          items:items,
          currentIndex:0
      }
  },
  methods: {
      autoPlay() {
          this.currentIndex++
          if(this.currentIndex>items.length-1){
              this.currentIndex=0
          }
      }
  },
  created() {
      this.$nextTick(() => {
        this.timer = setInterval(() => {
            this.autoPlay()
        }, 4000)
    })
  }
}
</script>
<style>

.scroll{
    position: relative;
    height: 200px;
}

.scroll-item{
    position: absolute;
    height: 100%;
    width: 100%;
}

 img{
    height: 100%;
    width: 100%;
}


.list-enter-to {
  transition: all 1s ease;
  transform: translateX(0);
}

.list-leave-active {
  transition: all 1s ease;
  transform: translateX(-100%)
}

.list-enter {
  transform: translateX(100%)
}

.list-leave {
  transform: translateX(0)
}
</style>
