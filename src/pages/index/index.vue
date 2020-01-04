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
    <i-grid i-class="no-border">
    <i-grid-item @click="goList(grid.url)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.type}}</i-grid-label>
    </i-grid-item>
    </i-grid>
    <i-panel :title="title_name">
      <view style="padding: 15px;">
        <i-card @click="goType(item)" v-for="item in top" :key="item" i-class="split" :extra="item.name" :thumb="item.image">
           <view slot="content">{{item.remark}}</view>
           <view slot="footer">{{item.address}}</view>
        </i-card>
      </view>
    </i-panel>
  </div>
</template>

<script>

export default {
  data () {
    return {
      title_name: "热门",
      grids: [
        {type:"春",image:"/static/images/tent.png","url":'../spots/main?type=1'},
        {type:"夏",image:"/static/images/cocktail.png","url":'../spots/main?type=2'},
        {type:"秋",image:"/static/images/cruise-ship.png","url":'../spots/main?type=3'},
        {type:"冬",image:"/static/images/mountains.png","url":'../spots/main?type=4'},
      ],
      top: [],
      imgUrls: [
        'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
        'https://images.unsplash.com/photo-1551214012-84f95e060dee?w=640',
        'https://images.unsplash.com/photo-1551446591-142875a901a1?w=640',
      ],
      indicatorDots: false,
      autoplay: false,
      interval: 5000,
      duration: 1000
    }
  },

  methods: {
    goList (url) {
      mpvue.navigateTo({ url })
    },
    goType(type){
      console.log(type)
      let url = '../detail/main?type=' + type.remark
      mpvue.navigateTo({ url })
    }
  },

  created () {
    const db = wx.cloud.database({ env: 'pure-709fe2' })
    db.collection('top').get().then(
      res => {
        console.log(res.data)
        this.top = res.data
      }
    )

  }
}
</script>

<style scoped>
div >>> .no-border{
  border-width: 0pt;
}
div >>> .split{
  margin-bottom: 10pt;
}
</style>
