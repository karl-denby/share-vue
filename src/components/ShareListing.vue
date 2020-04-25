<template>
  <div class="share">
    <h1>{{ share.company_name }}</h1>
    <h2>{{ share.market }}</h2>
    <h1>{{ share.share }} {{ share.price }} {{ share.price_change }}</h1>
  </div>
</template>

<script>
export default {
  name: 'ShareListing',
  props: {
    share: null
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  margin: 40px 0 0;
}
</style>
