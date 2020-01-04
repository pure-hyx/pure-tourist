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
    <i-collapse v-for="item in detail" :key="item" :name="item.name">
        <i-collapse-item :title="item.title" name="name1">
            <view slot="content">{{item.remark}}</view>
        </i-collapse-item>
    </i-collapse>
    </i-panel>
    <i-panel title="行程安排" hide-border=true>
    <i-steps v-for="sub in route" :key="sub" >
     <i-step status="finish" icon="barrage">
        <view slot="title">{{sub.title}}</view>
        <view slot="content">{{sub.content}}</view>
     </i-step>
    </i-steps>
    </i-panel>
  </div>
</template>

<script>
export default {
  data () {
    return {
      route:[
        {title:"海拉尔",content:""},
        {title:"巴彦呼硕",content:""},
        {title:"根河",content:""},
        {title:"冷级村",content:""},
        {title:"草原牧场",content:""},
        {title:"海拉尔",content:""}
      ],
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
