<template>
  <div>
    <i-grid>
    <i-grid-item>
        <i-grid-icon>
            <image src="/static/images/user.png" />
        </i-grid-icon>
        <i-grid-label>Grid</i-grid-label>
    </i-grid-item>
  </i-grid>
  </div>
</template>

<script>
export default {
  data () {
    return {
      motto: 'Hello miniprograme',
      userInfo: {
        nickName: 'mpvue',
        avatarUrl: 'http://mpvue.com/assets/logo.png'
      }
    }
  },


  methods: {
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped>
</style>