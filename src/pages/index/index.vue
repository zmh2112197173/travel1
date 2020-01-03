<template>
  <div>
    <swiper
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
      style="height:200px"
    >
    <block v-for="item in imgUrls" :key="item">
      <swiper-item>
        <image :src="item" style="width:100%;height:100%"/>
      </swiper-item>
    </block>
  </swiper>
  <i-grid i-class="no-border">
    <i-grid-item @click="goList(item.url)" i-class="no-border" v-for="item in grids" :key="item">
      <i-grid-icon>
        <image :src="item.img" />
      </i-grid-icon>
      <i-grid-label>{{item.type}}</i-grid-label>
    </i-grid-item>
  </i-grid>
  <i-panel>
    <i-notice-bar>强烈推荐</i-notice-bar>
    <view style="padding: 10px;">
      <i-card @click="goType(item.type)" i-class="split" v-for="item in recommand" :key="item" :extra="item.name" :thumb="item.img">
        <view slot="content">推荐理由：{{item.remark}}</view>
        <view slot="footer" >
          <span>地址：{{item.address}}</span>
          <i-icon type="share" size="20" style="float:right"/>
          <i-icon type="praise" size="20" style="float:right" />
          <i-icon type="collection" size="20" style="float:right" />
        </view>
      </i-card>
    </view>
  </i-panel>
  </div>
</template>

<script>
import card from '@/components/card'
import top from '@/data/top.json'

export default {
  data () {
    return {
      grids: [
        {type:"大理美食",img:"/static/images/1.png","url":'../list/main?type=1'},
        {type:"酒店客栈",img:"/static/images/2.png","url":'../list/main?type=2'},
        {type:"休闲娱乐",img:"/static/images/3.png","url":'../list/main?type=3'},
        {type:"旅游攻略",img:"/static/images/4.png","url":'../list/main?type=4'}
      ],
      imgUrls: [
        "cloud://soft-76d6a3.736f-soft-76d6a3/5.jpg",
        "cloud://soft-76d6a3.736f-soft-76d6a3/6.jpg",
        "cloud://soft-76d6a3.736f-soft-76d6a3/7.jpg"
      ],
      indicatorDots: true,
      autoplay: true,
      interval: 5000,
      duration: 1000,
      recommand: top,
    }
  },
  components: {
    card
  },

  methods: {
    goList (url) {
      mpvue.navigateTo({ url })
    },
    goType (type) {
      let url = '../list/main?type=' + type
      mpvue.navigateTo({ url })
    }
  },

  created () {
  }
}
</script>

<style scoped>
div >>> .no-border {
  border-width: 0pt;
}
div >>> .split {
  margin-bottom: 10pt;
}
</style>