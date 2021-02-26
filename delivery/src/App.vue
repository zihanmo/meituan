<template>
  <div id="app">
    <!--头部-->
    <Myheader :poiInfo='poiInfo'></Myheader>

    <!--导航-->
    <Mynav></Mynav>
    <!--内容-->
    <router-view></router-view>
  </div>
</template>


<script>
import Myheader from "./components/Header/Header"
import Mynav from "./components/Nav/Nav"
export default {
  name: 'App',
  components: {
    Myheader, Mynav
  },
  data () {
    return {
      //header组件需要的商家信息
      poiInfo: {}
    }
  },

  created () {
    var that = this;
    this.$axios.get('/api/goods')
      .then(function (response) {
        var dataSource = response.data
        if (dataSource.code == 0) {
          that.poiInfo = dataSource.data.poi_info
        }
        console.log(that.poiInfo)
      })
      .catch(function (error) {
        console.log(error)
      })
  }
}
</script>

<style>
</style>
