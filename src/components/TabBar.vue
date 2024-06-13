<template>
    <div class="tab-bar">
      <slot></slot>
    </div>
  </template>
  
  <script setup></script>
  
  <style scoped>
  .tab-bar {
    position: fixed;
    left: 0px;
    right: 0px;
    bottom: 0px;
    display: flex;
    justify-content: space-between;
    background-color: skyblue;
    box-shadow: 0px -1px 3px rgba(0, 0, 0, 0.3);
  }
  </style>