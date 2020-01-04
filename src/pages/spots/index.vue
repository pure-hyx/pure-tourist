<template>
  <div>
    <i-card img style="width:100%;height:200px" v-for="item in spots" :key="item" i-class="split" :extra="item.name" :thumb="item.image">
      <view slot="content">{{item.remark}}</view>
      <view slot="footer">{{item.address}}</view>
    </i-card>
  </div>
</template>

<script>
export default {
  data () {
    return {
      spots:[]
    }
  },
  onLoad (option){
    this.spots = require('@/data/' + option.type + '.json')
    console.log(this.spots)
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
