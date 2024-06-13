<template>
  <div class="tab-bar">
    <div class="tab-bar-item">首页</div>
    <div class="tab-bar-item">分类</div>
    <div class="tab-bar-item">购物车</div>
    <div class="tab-bar-item">我的</div>
  </div>
</template>

<script setup></script>

<style scoped>
.tab-bar {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  justify-content: space-around;
  height: 40px;
  background-color: skyblue;
  box-shadow: 0 -1px 3px rgba(0, 0, 0, 0.3);
}
.tab-bar-item {
  line-height: 40px;
  text-align: center;
  color: #666;
}
</style>
