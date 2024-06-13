<template>
    
  <div class="tab-bar-item">
    <i :class="iconStyle"></i>
    <slot></slot>
  </div>
</template>

<script setup>
import { computed } from 'vue';
  const props = defineProps({
    icon: {
      type: String,
      required: true,
      default: 'user',
    },
  })
  const iconStyle = computed (()=>`iconfont icon-${props.icon}`)
</script>


<style scoped>
/* iconfont的网站生成 */
@import 'http://at.alicdn.com/t/c/font_3660333_clz5n3z0jtw.css';

.tab-bar-item {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  font-size: 12px;
  color: gray;
}
.tab-bar-item i {
  font-size: 18px;
}
</style>
