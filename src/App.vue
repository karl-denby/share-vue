<template>
  <div id="app">
    <ShareListing v-bind:share=share />
  </div>
</template>

<script>
import ShareListing from './components/ShareListing.vue'

export default {
  name: 'App',
  components: {
    ShareListing
  },
  data () {
    return {
      share: {}
    }
  },
  mounted () {
    this.getShareData()
  },
  methods: {
    async getShareData() {
      const api_url ="https://api.karldenby.com/shares/fake";
      console.log(`Using the url: ${api_url}`)
      const res = await fetch(api_url)
      const share = await res.json();
      console.log(`Data returned is ${share}`)
      this.share = share;
      setTimeout(this.getShareData, 60000)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
