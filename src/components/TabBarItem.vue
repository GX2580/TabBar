<script setup>
import { computed, defineProps } from 'vue'
import useParent from '../hooks/useParent'

// useParent 是一个函数，返回一个对象
// 对象中包含 parent 和 index
const { parent, index } = useParent()

const props = defineProps({
  icon: {
    type: String,
    required: true,
    default: 'user'
  }
})

const iconStyle = computed(() => `iconfont icon-${props.icon}`)
const isActive = computed(() => {
  // 父组件传给子组件的值
  return parent.props.modelValue === index.value
})

const handleClick = () => {
  console.log('index.value', index.value)
  parent.setActive(index.value)
}
</script>

<template>
  <div class="tab-bar-item" :class="{ active: isActive }" @click="handleClick">
    <i :class="iconStyle"></i>
    <slot></slot>
  </div>
</template>

<style scoped>
@import 'http://at.alicdn.com/t/c/font_3660333_clz5n3z0jtw.css';

.tab-bar-item {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-size: 12px;
  color: #666;
}

.tab-bar-item i {
  font-size: 18px;
}

.tab-bar-item.active {
  color: red;
}
</style>