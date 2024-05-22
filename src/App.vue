<template>
  <div class="flex">
    <div class="w-50">
      <div class="input">
        <el-input size="large" v-model="inputValue" style="width: 240px" placeholder="請輸入文字" />
      </div>
      <el-select v-model="selectValue" placeholder="請選擇字型" size="large" style="width: 240px">
        <el-option v-for="item in options" :key="item" :label="item" :value="item" />
      </el-select>
      <div class="colorPicker">
        <p>請選擇顏色</p>
        <el-color-picker v-model="colorValue" />
      </div>
    </div>
    <div class="w-50 resultBlock">
      <p>{{ inputValue }}</p>
    </div>
  </div>
</template>
<script setup>
import { ref } from 'vue'
const inputValue = ref('')
const selectValue = ref('')
const colorValue = ref('')
const options = ref([
  'Inter',
  'Helvetica Neue',
  'Helvetica',
  'PingFang SC',
  'Hiragino Sans GB',
  'Microsoft YaHei',
  '微软雅黑',
  'Arial',
  'sans - serif'
])
</script>
