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
    <i-panel title="线路亮点">
    <i-collapse v-for="item in detail" :key="item" :name="item.name" >
        <i-collapse-item :title="item.title" name="name1" >
            <view slot="content" >{{item.remark}}</view>
        </i-collapse-item>
    </i-collapse>
    <i-button @click="handleClick()" type="ghost">左边弹出1</i-button>
    <i-drawer mode="left" :visible="showLeft1" bind:close="toggleLeft1">
    <view class="demo-container">
        单击遮罩层关闭
    </view>
    </i-drawer>
    </i-panel>
    
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
    handleClick() {
        this.setData({
            showLeft1: !this.data.showLeft1
        });
      },
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
