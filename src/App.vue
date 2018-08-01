<template>
  <div id="app">
    <input type="button" value="11111111111" @click="show"/>
    <fwPicturePerview ref="fwpp" :picList="list" :nowPic="0"/>
  </div>
</template>

<script>
import fwPicturePerview from './components/fw-picture-perview'

export default {
  name: 'App',
  components: {
    fwPicturePerview
  },
  data() {
    return {
      list: [
        {
          src: 'https://i0.hdslb.com/bfs/article/68375b01cabb34a9a2f45dbf1b585f99847cc242.jpg@1320w_2504h.webp'
        },
        {
          src: 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1533026617311&di=278192c065ef76c891deb1c6b0083507&imgtype=0&src=http%3A%2F%2Fimage.jijidown.com%2Fv1%2Fimage%3Fav%3D9240456%26url%3Dhttps%3A%2F%2Fi0.hdslb.com%2Fbfs%2Farchive%2F7c55e7e9bfa8001ec58d82c43fbfc64a3bc69942.jpg%26sign%3D20D238AA85644320BC4D83FCA3E9E894'
        }
      ]
    }
  },
  methods: {
    show() {
      this.$refs.fwpp.show = true
    }
  }
}
</script>

<style>
</style>
