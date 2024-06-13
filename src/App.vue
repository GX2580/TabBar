<script setup>
import { ref } from 'vue'
import TabBar from './components/TabBar.vue'
import TabBarItem from './components/TabBarItem.vue'

const active = ref(0)
</script>

<template>
  <!-- v-model 是双向绑定 -->
  <!-- 1. 当 active（数据）的值改变时，视图会变化 -->
  <!-- 2. 当视图变化时，数据 active 会变化 -->
  <!-- 在 Vue 3 中，默认 v-model 就是如下两个绑定的简写 -->
  <!-- 1. 绑定一个属性 modelValue -->
  <!-- 2. 默认监听 update:modelValue -->
  <TabBar v-model="active">
    <TabBarItem icon="home">首页</TabBarItem>
    <TabBarItem icon="category">分类</TabBarItem>
    <TabBarItem icon="cart">购物车</TabBarItem>
    <TabBarItem icon="user">我的</TabBarItem>
  </TabBar>
</template>

<style></style>