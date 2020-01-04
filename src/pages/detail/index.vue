<template>
  <div>
    <text class="caption-title">路线亮点</text>
    <i-collapse v-for="item in detail" :key="item" :name="item.name">
        <i-collapse-item :title="item.title" name="name1">
            <view slot="content">{{item.remark}}</view>
        </i-collapse-item>
    </i-collapse>
  </div>
</template>

<script>
export default {
  data () {
    return {
      detail:[]
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
