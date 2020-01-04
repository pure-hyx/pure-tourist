<template>
  <div>
  <i-card>
  <view slot="content"><video style="width: 100%;height=400px;margin:1px;" src="cloud://southafrica.736f-southafrica/video/dear basketball.mp4" binderror="videoErrorCallback"></video></view>
</i-card>
<i-card >
  <view slot="content"><img style="width:100%;height:200px" src="cloud://pure-709fe2.7075-pure-709fe2/top 图片/大兴安岭.jpeg"></view>
  <view slot="content">汤普森本周将与勇士会面 寻求顶薪合同</view>
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