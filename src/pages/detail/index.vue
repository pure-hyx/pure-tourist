<template>
  <div>
    <swiper
    :indicator-dots="indicatorDots"
    :autoplay="autoplay"
    :interval="interval"
    :duration="duration"
    >
    <block v-for="img in imgUrls" :key="img">
      <swiper-item>
        <image :src="img" style="width:100%" />
      </swiper-item>
    </block>
    </swiper>
    <i-card  v-for="item in detail" :key="item" i-class="split" :extra="item.name" :thumb="item.image">
      <view slot="content">{{item.remark}}</view>
    </i-card>
    
    
  </div>
</template>

<script>
export default {
  data () {
    return {
      showLeft1: false,
      detail:[],
      imgUrls: [
        'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
        'https://images.unsplash.com/photo-1551214012-84f95e060dee?w=640',
        'https://images.unsplash.com/photo-1551446591-142875a901a1?w=640',
      ],
    }
  },
  
  onLoad (option){
    this.detail = require('@/data/' + option.type + '.json')
    console.log(this.detail)
  },
  methods: {
  },
  created () {
  }
}
</script>

<style scoped>
div >>> .split{
  margin-bottom: 10pt;
}
</style>
