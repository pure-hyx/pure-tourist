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
        'cloud://pure-709fe2.7075-pure-709fe2/swiper 图片/11.jpeg',
        'cloud://pure-709fe2.7075-pure-709fe2/swiper 图片/12.jpeg',
        'cloud://pure-709fe2.7075-pure-709fe2/swiper 图片/13.jpeg',
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
