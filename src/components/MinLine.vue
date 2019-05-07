<template>
  <div class="minline">
    <div class="item" v-for="item in count" :key="item"></div>
  </div>
</template>

<script>
export default {
  name: 'MinLine',
  props: {
    count: Number
  },
  data () {
    return {
    }
  },
  created () {
    console.log(this.count)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
.minline {
  .item {
    color: white;
    background: white;
    width: 1px;
    height: 6px;
    margin-left: 50%;
    margin-bottom: 1px;
  }
}
</style>
