<template>
  <div class="flex">
    <div class="w-50">
      <el-button-group>
        <el-button type="primary" @click="resetValue('effect1')">效果一</el-button>
        <el-button type="warning" @click="resetValue('effect2')">效果二</el-button>
      </el-button-group>
      <div class="input">
        <p class="description">請輸入文字</p>
        <el-input size="large" v-model="inputValue" style="width: 240px" placeholder="請輸入文字" />
      </div>
      <p class="description">請選擇字體</p>
      <el-select v-model="fontFamilyValue" placeholder="請選擇字型" size="large" style="width: 240px" clearable>
        <el-option v-for="item in options" :key="item" :label="item" :value="item" />
      </el-select>
      <div class="colorPicker">
        <p>請選擇顏色</p>
        <el-color-picker v-model="colorValue" />
      </div>
    </div>
    <div class="w-50 resultBlock" :class="{ 'effect1Block': effectValue === 'effect1', 'effect2Block': effectValue === 'effect2' }">
      <p 
        class="resultString str1" 
        :style="{ color: colorValue, fontFamily: fontFamilyValue }"
        :class="{ 'effect1': effectValue === 'effect1', 'effect2': effectValue === 'effect2' }"
      >
        {{ inputValue }}
      </p>
      <p class="resultString str2" :style="{ color: colorValue, fontFamily: fontFamilyValue }" :class="{ 'effect1': effectValue === 'effect1', 'effect2': effectValue === 'effect2' }">{{ inputValue }}</p>
      <p class="resultString str3" :style="{ color: colorValue, fontFamily: fontFamilyValue }" :class="{ 'effect1': effectValue === 'effect1', 'effect2': effectValue === 'effect2' }">{{ inputValue }}</p>
    </div>
  </div>
</template>
<script setup>
import { ref } from 'vue'
const effectValue = ref('effect1')
const inputValue = ref('')
const fontFamilyValue = ref('')
const colorValue = ref()
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
const resetValue = (effect) => {
  effectValue.value = effect
  colorValue.value = ''
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Overlock:ital,wght@0,400;0,700;0,900;1,400;1,700;1,900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400..900&display=swap');
</style>
