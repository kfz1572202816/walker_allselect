<template>
  <div class="hello">
    <input type="button" name="all" value="全选" @click="allSelect"/>
    <input type="button" name="fan" value="全不选" @click="noSelect" />
    <input type="button" name="fan" value="反选" @click="fanSelect" />
    <ul v-for="(list,index) in dataCheck" :key="index">
      <li>
        <input type="checkbox" :value="list.text" v-model="list.check"/>
        {{list.text}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      dataCheck: [
        { text: '苹果', check: false },
        { text: '芒果', check: false },
        { text: '百香果', check: false },
        { text: '果栋', check: false }
      ]
    }
  },
  methods: {
    allSelect () {
      console.log(1258)

      var datache = this.dataCheck
      for (var i = 0; i < datache.length; i++) {
        datache[i].check = true
      }
      this.dataCheck = datache
    },
    noSelect () {
      var datache = this.dataCheck
      for (var i = 0; i < datache.length; i++) {
        datache[i].check = false
      }
      this.dataCheck = datache
    },
    fanSelect () {
      var datache = this.dataCheck
      for (var i = 0; i < datache.length; i++) {
        datache[i].check = !datache[i].check
      }
      this.dataCheck = datache
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
