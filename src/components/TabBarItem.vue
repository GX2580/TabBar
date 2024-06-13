<script setup>
import { computed, inject, getCurrentInstance, defineProps } from 'vue'

// 获取当前组件实例
const instance = getCurrentInstance()
console.log(instance)

// 定义组件的 props
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

// 从父组件注入 active 变量
const active = inject('active')

// 计算属性：根据 icon prop 动态生成图标的类名
const iconStyle = computed(() => `iconfont icon-${props.icon}`)

// 计算属性：判断当前项是否被选中
const isActive = computed(() => props.index === active.value)

// 点击事件处理函数：触发父组件的事件
const handleClick = () => {
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