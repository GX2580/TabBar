<template>
  <div class="tab-bar">
    <slot></slot>
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
  height: 50px; /* 增加高度以适应移动设备的触摸操作 */
  background-color: skyblue;
  box-shadow: 0 -1px 3px rgba(0, 0, 0, 0.3);
}
/* 媒体查询，针对不同屏幕宽度进行样式调整 */
@media (max-width: 600px) {
  .tab-bar-item {
    font-size: 12px; /* 在较小屏幕上进一步减小字体大小 */
  }
}
@media (max-width: 360px) {
  .tab-bar-item {
    padding: 0 5px; /* 在非常小的屏幕上增加内边距，保证文本不会溢出 */
  }
}
</style>
