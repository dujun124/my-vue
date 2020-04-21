<template>
  <!-- 底部导航 -->
  <div class="nav-bottom">
    <router-link to="/home">
      <i class="iconfont icon-auto" ></i>
      <label>首页</label>
    </router-link>
    <router-link to="/find">
      <i class="iconfont icon-all-fill" ></i>
      <label>发现</label>
    </router-link>
    <router-link to="/order">
      <i class="iconfont icon-cart-full" ></i>
      <label>订单</label>
    </router-link>
    <router-link to="/my">
      <i class="iconfont icon-bussiness-man" ></i>
      <label>我的</label>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'NavBottom',
}
</script>

<style scoped>
  .active{
    color: #55a532;
  }
</style>
