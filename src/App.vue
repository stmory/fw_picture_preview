<template>
  <div id="app">
    <input type="button" value="11111111111" @click="show"/>
    <fwPicturePerview ref="fwpp"/>
  </div>
</template>

<script>
import fwPicturePerview from './components/fw-picture-perview'

export default {
  name: 'App',
  components: {
    fwPicturePerview
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
