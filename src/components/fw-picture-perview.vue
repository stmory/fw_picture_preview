<template>
  <div class="fw-picture-perview-main" v-if="show">
    <div class="fw-picture-perview-pic">
      <img ref="img" src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1533026617311&di=278192c065ef76c891deb1c6b0083507&imgtype=0&src=http%3A%2F%2Fimage.jijidown.com%2Fv1%2Fimage%3Fav%3D9240456%26url%3Dhttps%3A%2F%2Fi0.hdslb.com%2Fbfs%2Farchive%2F7c55e7e9bfa8001ec58d82c43fbfc64a3bc69942.jpg%26sign%3D20D238AA85644320BC4D83FCA3E9E894" />
    </div>
    <div class="fw-picture-perview-close" @click="close">
      <svg t="1533009304516" class="icon" style="" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="5830" xmlns:xlink="http://www.w3.org/1999/xlink" width="32" height="32"><path fill="#333" d="M563.8 512l262.5-312.9c4.4-5.2 0.7-13.1-6.1-13.1h-79.8c-4.7 0-9.2 2.1-12.3 5.7L511.6 449.8 295.1 191.7c-3-3.6-7.5-5.7-12.3-5.7H203c-6.8 0-10.5 7.9-6.1 13.1L459.4 512 196.9 824.9c-4.4 5.2-0.7 13.1 6.1 13.1h79.8c4.7 0 9.2-2.1 12.3-5.7l216.5-258.1 216.5 258.1c3 3.6 7.5 5.7 12.3 5.7h79.8c6.8 0 10.5-7.9 6.1-13.1L563.8 512z" p-id="5831"></path></svg>
    </div>
    <div class="fw-picture-perview-bottom">
      <fwTool @spin="spin" @zoomInOut="zoomInOut"></fwTool>
    </div>
  </div>
</template>

<script>
import fwTool from './fw-tool'

export default {
  data() {
    return {
      deg: 0,
      zoom: 1,
      show: false,
    }
  },
  props: {
    picList: {
      type: Array,
      default: () => []
    }
  },
  components: {
    fwTool
  },
  methods: {
    spin(n) {
      this.deg += n * 90
      this.$refs.img.style.transform = `rotate(${this.deg}deg) scale(${this.zoom},${this.zoom})`
    },
    zoomInOut(n) {
      this.zoom += n * 0.2
      this.$refs.img.style.transform = `rotate(${this.deg}deg) scale(${this.zoom},${this.zoom})`
    },
    close() {
      this.deg = 0
      this.zoom = 1
      this.show = false
    }
  }
}
</script>

<style scoped>
.fw-picture-perview-main{
  position: absolute;
  top:0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(80, 80, 80, 0.5);
}
.fw-picture-perview-bottom{
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 80px;
  background-color: #fff;
}
.fw-picture-perview-pic{
  position: absolute;
  top:0;
  bottom: 80px;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}
.fw-picture-perview-pic img{
  transition: all .3s;
  max-width: 80%;
  max-height: 80%;
}
.fw-picture-perview-close{
  position: absolute;
  height: 40px;
  width: 40px;
  right: 0;
  top: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
</style>
