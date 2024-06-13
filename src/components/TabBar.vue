<script setup>
import { defineProps, defineEmits } from 'vue'
import useChildren from '../hooks/useChildren'

// useChildren 是一个 hooks 函数
// 返回一个对象，对象中存在一个方法 linkChildren
// linkChildren 方法可以将当前组件的属性和方法传递给子组件
const { linkChildren } = useChildren()

const props = defineProps({
  modelValue: {
    type: Number,
    default: 0
  }
})

const emit = defineEmits(['update:modelValue'])

const setActive = (index) => {
  emit('update:modelValue', index)
}

// 向子组件传参
linkChildren({
  props,
  setActive
})
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