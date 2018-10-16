<template>
  <section class="container">
    <div>
      <h1 class="title">
        responsive-design
      </h1>
      <h2 class="subtitle">
        Nuxt.js project
      </h2>
      <div class="">
        <load-image-size :src='src' :size='size'/>
      </div>
    </div>
  </section>
</template>

<script>
import LoadImageSize from '~/components/load-image-size'

export default {
  components: {
    LoadImageSize
  },
  data: () => ({
    src: [
      '/image/img-showcase-tshirt.png',
      '/image/img-showcase-tshirt@2x.png',
      '/image/img-showcase-tshirt@3x.png',
    ],
    size: [
      650, 900
    ],
    windowSize: null
  }),
  methods: {
  },
  mounted () {
    this.windowSize = window.outerWidth
  }
}
</script>

<style>
</style>

