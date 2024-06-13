<script setup>
import {ref} from 'vue'
const count =ref(0)
</script>

<template>
  <h1>首页</h1><br>
  <button @click="count++">{{ count }}</button>
</template>

<style scoped>
</style>