<script setup>
import { defineProps, defineEmits } from 'vue'

// 定义组件的 props
const props = defineProps({
  modelValue: {
    type: Number,
    default: 0
  }
})

// 定义事件 emit
const emit = defineEmits(['update:modelValue'])

// 方法：设置当前选中的索引
const setActive = (index) => {
  emit('update:modelValue', index)
}
</script>

<template>
  <div class='tab-bar'>
    <slot></slot>
  </div>
</template>

<style scoped>
.tab-bar {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  height: 40px;
  display: flex;
  background-color: skyblue;
  box-shadow: 0 -1px 3px rgba(0, 0, 0, 0.3);
}
</style>