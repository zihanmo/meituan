<template>
  <div class="header">
    <!-- 顶部通栏 -->
    <div class="top-wrapper">
      <div class="back-wrapper">
        <span class="icon-arrow_lift"></span>
      </div>
      <div class="search-wrapper">
        <span class="search-icon"></span>
        <input class="search-bar"
               type="text"
               placeholder="搜索店内商品">
      </div>
      <div class="more-wrapper">
        <a class="spelling-bt"
           href="#">拼单</a>
        <div class="more-bt">
          <i class="s-radius"></i>
          <i class="s-radius"></i>
          <i class="s-radius"></i>
        </div>
      </div>
    </div>
    <!--主体内容-->
    <div class="content-wrapper">
      <div class="icon"
           :style="head_bg">
      </div>
      <div class="name">
        <h3>{{poiInfo.name}}</h3>
      </div>
      <div class="collect">
        <img src="../../../resource/img/star.png" />
        <span>收藏</span>
      </div>
    </div>
    <!-- 公告内容 -->
    <div class="bulletin-wrapper">
      <img class="icon"
           v-if="poiInfo.discounts2"
           :src="poiInfo.discounts2[0].icon_url" />
      <span v-if="poiInfo.discounts2"
            class="text">{{poiInfo.discounts2[0].info}}</span>
      <div v-if="poiInfo.discounts2"
           class="detail">{{poiInfo.discounts2.length}}个活动
        <span class="icon-keyboard_arrow_right"></span>

      </div>
    </div>

    <div class="bg-wrapper"
         :style="content_bg">
    </div>

    <!--公共详情-->
    <div class="bulletin-detail">
      <div class="content-wrapper"></div>
      <div class="close-wrapper"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    poiInfo: {
      type: Object,
      default: {}
    }
  },
  computed: {
    content_bg () {
      return "background-image:url(" + this.poiInfo.head_pic_url + ")"
    },
    head_bg () {
      return "background-image:url(" + this.poiInfo.pic_url + ")"
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
@import url("../../common/styles/icon.css");
.header {
  height: 160px;
  padding-top: 20px;
}
.header .top-wrapper {
  position: relative;
}

.header .top-wrapper .back-wrapper {
  width: 50px;
  height: 31px;
  position: absolute;
  left: 0;
  top: 0;
  text-align: center;
  line-height: 31px;
}

.header .top-wrapper .back-wrapper span {
  display: inline-block;
  color: white;
}
.header .top-wrapper .search-wrapper {
  width: 100%;
  height: 31px;

  padding: 0 104px 0 50px;
  box-sizing: border-box;
}
.header .top-wrapper .search-wrapper .search-bar {
  width: 100%;
  height: 31px;
  box-sizing: border-box;
  background: #cdcdcc;
  border-radius: 25px;
  padding-left: 28px;
}

.header .top-wrapper .search-wrapper .search-icon {
  background: url(../../../resource/img/titans_h5_search@2x.png) no-repeat 11px
    center;
  position: absolute;
  height: 31px;
  width: 28px;
  background-size: 13px 13px;
}
.header .top-wrapper .more-wrapper {
  width: 65px;
  height: 24px;
  position: absolute;
  right: 0;
  top: 0;
  padding: 7px 15px 0 24px;
}

.header .top-wrapper .more-wrapper .spelling-bt {
  width: 30px;
  height: 17px;
  color: white;
  line-height: 17px;
  border: 1px solid white;
  text-align: center;
  float: left;
  text-decoration: none;
  font-size: 10px;
}

.header .top-wrapper .more-wrapper .more-bt {
  float: left;
  width: 20px;
  height: 31px;
  margin-left: 13px;
}

.header .top-wrapper .more-wrapper .more-bt .s-radius {
  width: 3px;
  height: 3px;
  border-radius: 50%;
  border: 1px solid white;
  display: block;
  float: left;
  margin-right: 1px;
  margin-top: 6px;
}

.header .bg-wrapper {
  width: 100%;
  height: 150px;
  position: absolute;
  left: 0;
  top: 0;
  z-index: -1;
  background-size: 100% 135%;
  background-position: center -12px;
}
.content-wrapper {
  padding: 17px 10px 11px;
  height: 50px;
}
.content-wrapper .icon {
  background-size: 135% 100%;
  background-position: center;
  height: 50px;
  width: 50px;
  border-radius: 5px;
  float: left;
}
.content-wrapper .name {
  float: left;
  padding: 18px 0 0 12px;
}
.content-wrapper .name h3 {
  font-size: 16px;
  font-weight: bold;
  color: white;
}

.content-wrapper .collect {
  width: 25px;
  height: 37px;
  float: right;
  text-align: center;
  padding-top: 6px;
}

.content-wrapper .collect img {
  width: 20px;
  height: 20px;
  float: right;
}
.content-wrapper .collect span {
  margin-top: 7px;
  color: white;
  font-size: 11px;
}
.bulletin-wrapper {
  height: 16px;
  padding: 0 10px;
}

.bulletin-wrapper .icon {
  height: 16px;
  width: 16px;
  float: left;
  margin-right: 6px;
}
.bulletin-wrapper .text {
  font-size: 11px;
  color: white;
  float: left;
  line-height: 16px;
}
.bulletin-wrapper .detail {
  float: right;
  color: white;
  font-size: 11px;
  line-height: 16px;
}
.bulletin-wrapper .detail span {
  font-size: 16px;
  line-height: 16px;
}
.bulletin-detail {
  width: 100%;
  height: 100%;
  position: absolute;
  left: 0;
  top: 0;
  background: rgba(98, 98, 98, 0.8);
}
</style>
