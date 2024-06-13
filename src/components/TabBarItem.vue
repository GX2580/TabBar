<template>
    <div class="tab-bar-item">
      <slot></slot>
    </div>
  </template>
  
  <script setup></script>
  
  <style scoped>
  .tab-bar-item {
    flex: 1;
    line-height: 40px;
    text-align: center;
    color: white;
  }
  </style>