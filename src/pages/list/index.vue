<template>
  <div>
    <i-card v-for="item in list" :key="item" i-class="split" :extra="item.name" :thumb="item.img">
      <view slot="content">{{item.remark}}</view>
      <view slot="footer">
        <span>地址:{{item.address}}</span>
        <i-icon type="share" size="20" style="float:right"/>
        <i-icon type="praise" size="20" style="float:right" />
        <i-icon type="collection" size="20" style="float:right" />
      </view>
    </i-card>
  </div>
</template>

<script>
export default {
  data () {
    return {
      list:[]
  }
},
onLoad (option){
  this.list = require('@/data/' + option.type + '.json')
  console.log(this.list)
},
methods: {
},
created () {
  }
}
</script>

<style scoped>
div >>> .split {
  margin-bottom: 10pt;
}
</style>
