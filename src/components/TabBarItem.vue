<script setup>
import { computed, inject, getCurrentInstance, defineProps } from 'vue'

const instance = getCurrentInstance()
console.log(instance)

const props = defineProps({
  icon: {
    type: String,
    required: true,
    default: 'user'
  },
  index: {
    type: Number,
    required: true
  }
})

const active = inject('active')

const iconStyle = computed(() => `iconfont icon-${props.icon}`)
const isActive = computed(() => props.index === active.value)

const handleClick = () => {
  // 触发父组件的事件
  instance.parent.ctx.$emit('update:modelValue', props.index)
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