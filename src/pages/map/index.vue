<template>
  <div>
  <i-card>
  <view slot="content"><video style="width: 100%;height=400px;margin:1px;" src="cloud://pure-709fe2.7075-pure-709fe2/swiper 图片/vlog.mp4" binderror="videoErrorCallback"></video></view>
</i-card>
<i-card >
  <view slot="content"><img style="width:100%;height:200px" src="cloud://pure-709fe2.7075-pure-709fe2/top 图片/大兴安岭.jpeg"></view>
  <view slot="content">谁能想到，这趟没有观光行程的纯滑雪之旅，到最后vlog剪出来竟然是一场吃播……</view>
</i-card>

   
  </div>
</template>
<script>
import card from '@/components/card'
export default {
  data () {
    return {
      components: {
        card
      },
      methods: {
      },
      tap () {
        console.log('tap')
      }
    }
  }
}
</script>