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
        <image :src="img" style="width:100%;"/>
      </swiper-item>
    </block>
    </swiper>
    <i-grid i-class="no-border">
      <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
          <i-grid-icon>
              <image :src="grid.image" />
          </i-grid-icon>
          <i-grid-label>{{grid.title}}</i-grid-label>
      </i-grid-item>
    </i-grid>
    <i-panel :title="title_name">
    <view style="padding: 15px;">
      <i-card v-for="item in top" :key="item" i-class="split" :extra="item.name" :thumb="item.image">
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
      title_name: "强烈推荐",
      grids: [
        {title:"酒店客栈",image:"cloud://soft-76d6a3.736f-soft-76d6a3/1.png"},
        {title:"大理美食",image:"cloud://soft-76d6a3.736f-soft-76d6a3/2.png"},
        {title:"休闲娱乐",image:"cloud://soft-76d6a3.736f-soft-76d6a3/3.png"},
        {title:"旅游攻略",image:"cloud://soft-76d6a3.736f-soft-76d6a3/4.png"}
      ],
      top: [
        {name:"大理喜洲油粑粑",address:"大理爱情海喜洲店",image:"/static/images/8.jpg",remark:"大理的风味小吃，有甜咸两种口味，外皮香酥，内在松软，物美价廉"},
        {name:"舒适大床房",address:"大理古城东门",image:"/static/images/10.jpg",remark:"环境十分好！房子整体以白族框架为主，装修带有简约欧式味道"},
        {name:"大理苍山",address:"大理白族自治州云岭山脉南端",image:"/static/images/5.jpg",remark:"山色苍翠，国家级风景名胜区，是大理风花雪四大名景之最"},
        {name:"大理清真乳扇",address:"大理清真伊味轩",image:"/static/images/9.jpg",remark:"牛奶做成扇子卖，它是一种奶酪，美味可口"}
      ],
       imgUrls: [
        "cloud://soft-76d6a3.736f-soft-76d6a3/5.jpg",
        "cloud://soft-76d6a3.736f-soft-76d6a3/6.jpg",
        "cloud://soft-76d6a3.736f-soft-76d6a3/7.jpg"
      ],
      indicatorDots: false,
      autoplay: false,
      interval: 5000,
      duration: 1000
    }
  },


  methods: {
    goType(type){
      console.log(type)
      let url = '../list/main?type=' + type.title
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