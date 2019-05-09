<template>
  <div id="app">
    <nav-bar title="这是一个很屌的APP" left-text="返回" left-arrow>
      <icon name="weapp-nav" slot="right" />
    </nav-bar>
    <keep-alive>
      <router-view></router-view>
    </keep-alive>
    <tabbar v-model="active" @change="onChange">
      <tabbar-item icon="home-o">首页</tabbar-item>
      <tabbar-item icon="clock-o" dot>约课</tabbar-item>
      <tabbar-item icon="cart-o" info="5">周边</tabbar-item>
      <tabbar-item icon="friends-o" info="20">我的</tabbar-item>
    </tabbar>
  </div>
</template>

<script>
import { NavBar, Tabbar, TabbarItem, Icon } from 'vant'

export default {
  name: 'App',
  data () {
    return {
      active: 0
    }
  },
  components: {
    Icon,
    NavBar,
    Tabbar,
    TabbarItem
  },
  methods: {
    onChange (index) {
      console.log('当前TabBar索引', index)
    }
  }
}
</script>

<style lang="less">
@import '~vux/src/styles/reset.less';

body {
  background-color: #fbf9fe;
}
</style>
