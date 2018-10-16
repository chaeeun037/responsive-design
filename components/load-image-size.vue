<template>
  <div>
    <img
      v-for='(item, index) in src' :key='index'
      :src='item'
      v-if='getWindowSize(size.length) === size[index]'
      />
  </div>
</template>

<script>
export default {
  props: {
    src: Array,
    size: Array,
  },
  data: () => ({
    windowSize: null
  }),
  methods: {
    getWindowSize (count) {
      if (this.windowSize) {
        if (this.windowSize <= this.size[0]) {
          return this.size[0]
        }
        for (let i = 0; i < count - 1; i++) {
          if (this.size[i + 1] && this.windowSize > this.size[i] && this.windowSize <= this.size[i + 1]) {
            console.log(this.size[i + 1])
            return this.size[i + 1]
          }
        }
        if (this.windowSize > this.size[count]) {
          console.log(this.size[count])
          return this.size[count]
        }
      }
    }
  },
  mounted () {
    this.windowSize = window.outerWidth
  }
}
</script>