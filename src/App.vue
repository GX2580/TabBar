<script setup>
import { ref, provide } from 'vue'
import TabBar from './components/TabBar.vue'
import TabBarItem from './components/TabBarItem.vue'

// 定义响应式变量 active 和 items
const active = ref(0)
const items = ref([
  { text: '首页', icon: 'home', index: 0 },
  { text: '分类', icon: 'category', index: 1 },
  { text: '购物车', icon: 'cart', index: 2 },
  { text: '我的', icon: 'user', index: 3 }
])

// 向子组件提供 active 变量
provide('active', active)
</script>

<template>
  <TabBar v-model="active">
    <!-- 使用 v-for 循环生成 TabBarItem 组件 -->
    <TabBarItem v-for="item in items" :key="item.index" :index="item.index" :icon="item.icon">
      {{ item.text }}
    </TabBarItem>
  </TabBar>
</template>

<style></style>